## 🗺️Overview

In this lesson, you will learn how Orchestrator can be used to  store items in queues that will enable them to be distributed individually to robots for processing. They will also monitor the progress of the items based on process outcomes and the progress of the process itself. When the queue items enter processing, they become transactions. These items are designed to be indivisible units of work: a customer contract, an invoice, a complaint, etc. 

Queues are extremely important for large-scale automation projects. They allow the storage and processing of basically unlimited amounts of data. The only condition is for the data to be organized in transactions.

---

## 🤔What are queues?

Queues are containers that can hold an unlimited number of items. Items can store multiple types of data, by default in free form. If a specific data schema is needed, it can be uploaded at queue creation in the form of a JSON file.

---

## 🤔Why do you need queues?

Working with queues is very useful in large-scale automation scenarios underlined by complex logic. Such scenarios pose many challenges—bringing items from multiple sources together, processing them according to a unique logic, efficient use of resources, or reporting capabilities at individual item and queue level, including the use of SLAs. 

Consider the customer enrollment process through forms for a retail company: customers may come from different sources (online, partners, own shops, call center), thus having a smooth process of adding them to the processing line is crucial. Further on, working with queues will ensure that these are processed within the SLA time constraints.

---

## ⚒️Working with queues

### Creating queues

Queues are easily created in Orchestrator from the entry in the menu with the same name. They are folder entities, which allow setting up fine-grained permissions.

When creating a queue, you set the maximum number of retries (the number of times you want a queue item to be retried) and the Unique Reference field (select Yes, if you want the transaction references to be unique). You can update existing queue settings, such as:

- The queue name.

- The Auto Retry option.

- The maximum number of retries.

In Orchestrator, newly created queues are empty by default. To populate them with items you can either use the upload functionality in Orchestrator, or Studio activities. Bulk upload is supported directly in Orchestrator, from .csv files.

### Populating and consuming queues

To ensure an optimal use of the robots, queues are typically used with the Dispatcher-Performer model of running automations. In this model, the two main stages of a process involving queues are separated:

- The stage in which data is taken and fed into a queue in Orchestrator, from where it can be taken and processed by the robots is called **Dispatcher**.

- The stage in which the data is processed is called **Performer**.

Working with queues and queue items is done using the specific activities from the UiPath. System. Activities official package, under Orchestrator. These are:

- **Add Transaction Item**
	The robot adds an item in the queue and starts the transaction with the status 'In progress'. The queue item cannot be sent for processing until the robot finalizes this activity and updates the status.
	
- **Get Transaction Item**
	Gets an item from the queue to process it, setting the status to 'In progress'.
	
- **Postpone Transaction Item**
	Adds time parameters between which a transaction must be processed.
	
- **Set Transaction Progress**
	Enables the creation of custom progress statuses for In Progress transactions. This can be useful for transactions that have a longer processing duration, and breaking down the workload will give valuable information.
	
- **Set Transaction Status**
	Changes the status of the transaction item to Failed (with an Application or Business Exception) or Successful. As a general approach, a transaction failed due to Application Exceptions will be retried, and a transactions failed due to Business Exceptions will not be retried.
	
- **Add Queue Item**
	When encountering this activity in a workflow, the robot will send an item to the specified queue and will configure the timeframe and the other parameters.
	
	Two of the properties that are worth highlighting are: 
		- Deadline—add a date until which the items must be processed. 
	- Priority—select Low, Normal, or High, depending on the importance of the items that are added by this activity and how fast you want them to be processed. 

Within any given queue the transactions are processed in a hierarchical manner, according to this order: 

1. Items that **have a Deadline**, as follows: 
    
    1. In order of **Priority****—and**
    2. According to the set **Deadline** for items with the **same Priority.**
    
2. Items with **no Deadline**, in order of **Priority****—and**
    
    1. According to the rule **First In**, **First Out** for items with the **same Priority.**
    

For example, a **queue item** that's **due today at** **7:00 pm** and has a **Medium priority** is **processed first**, **before another item that has no due date and a High priority.**

### Queue item statuses

A queue item can have one of the statuses below. These will be set automatically following human user and robot actions, and/or using the Set Transaction Status activity. Custom sub-statuses can be set for queue items which are 'In Progress', using the Set Transaction Progress activity.

- **New**
	- The item was just added to the queue with Add Queue Item, or
	- the item was postponed, or
	- a deadline was added to it, or
	- the item was added after an attempt and failure of a previous queue item with auto-retry enabled. 
	
- **In Progress**
	The item was processed with the Get Transaction Item or the Add Transaction Item activity. When an item has this status, the custom progress status is also displayed, in the Progress column.
	
- **Failed**
	The item did not meet a business or application requirement within the project.
	
	It was therefore sent to a Set Transaction Status activity, which changed its status to Failed 
	
- **Successful**
	The item was processed and sent to a Set Transaction Status activity, which changed its status to Successful.
	
- **Abandoned**
	The item remained in the In Progress status for a long period of time (approx. 24 hours) without being processed.
	
- Retried
	The item failed with an application exception and was retried (at the end of the process retried, the status will be updated to a final one - Successful or Failed.
	
- Deleted
	The item has been manually deleted from the Transactions page.
	
	Apart from these above, queue items which have been abandoned or failed can enter a revision phase. In such a case, there are specific revision statuses, set by the reviewers. Check out the diagram below where both types of statuses are illustrated.

![[Queue_Statuses.pdf]]

---

## 🛑The Stop mechanism

Each running process in Orchestrator has a running state associated with it. You have the option to stop or kill the process. Kill will halt the process immediately, which may cause unwanted errors. Stop allows you to create a safe closing path for the process. 

After the Stop signal is sent, the process ends when it is safe to do so. This requires using the Should-Stop activity and a Stop mechanism in a workflow. It registers if the Stop button has been pressed in Orchestrator before the execution flow reaches the Should Stop activity. This is like saving a computer game before exiting as opposed to shutting down the computer.

In other words, it allows you to configure the workflow so that it performs various routines after the stop is triggered. You can, for example, perform a "clean up" routine to close windows and applications which have been targeted within the workflow.

---

## 🤖Queue robots

- ### Dispatcher
	Queue items can be added by a robot, typically called dispatcher.
- ### Performer
	The status of a queue item is typically updated by a robot called performer. 