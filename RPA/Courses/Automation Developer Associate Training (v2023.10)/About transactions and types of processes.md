## 🗺️Overview

In the Queues lesson, you've seen the most complex model of transaction processing. If this is your first course covering UiPath Studio, don't worry! You will easily grasp the other two models of transaction processing.

Okay! So, business processes can be very different from one another. But it is usually possible to classify them based on how they repeat certain steps when processing data. When considering these steps and how they are repeated, we can divide business processes into three categories: linear, iterative, and transactional.

---
### 🤔What it is?

The Transactional Process is a project template based on a Flowchart, optimized for basic automation processes.

The three categories of processes can be seen as the maturity stages of an automation project. Starting with simple linear tasks, which go through multiple repetitions, and finally, evolve into a transactional approach.

However, this is not a rule for all cases, and the category should be chosen according to the characteristics of the process (e.g., data being processed and frequency of repetitions) and other relevant requirements (e.g., ease of use and robustness).

| Type              | Explanation                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Example                              |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| **Linear**        | The process steps are performed only once. If the need is to process different data, the automation needs to be executed again. For example, an email request coming in triggers an automation which gathers data and provides a reply to the sender. The process is executed for each individual email.  <br><br>Linear processes are usually simple and easy to implement, but not very suitable to situations that require repetitions of steps using different data.                  | ![[Pasted image 20250505004200.png]] |
| **Iterative**     | The steps of the process are performed multiple times, but each time different data items are used. For example, instead of reading a single email on each execution, the automation can retrieve multiple emails and iterate through them doing the same steps. <br><br>This process implementation is done with a simple loop. But it has a disadvantage—if a problem happens while processing one item, the whole process is interrupted and the rest of the items remain unprocessed. | ![[Pasted image 20250505004210.png]] |
| **Transactional** | Similar to iterative processes, the steps of transactional processes repeat multiple times over different data items. However, the automation design is such that each repeatable part processes independently.<br><br>These repeatable parts are then called transactions. Transactions are independent from each other because they do not share any data or have any particular order to be processed.                                                                                 | ![[Pasted image 20250505004305.png]] |

---

## 🤔What is a transaction?

A transaction represents the minimum (atomic) amount of data and the necessary steps required to process the data, by fulfilling a section of a business process. A typical example would be a process that reads a single email from a mailbox and extracts data from it.

We call the data atomic because once it is processed, the assumption is that we no longer need it as we advance with the business process.

---

## 🤔What are some business scenarios in which I will use transaction processing?

- **Business Scenarios 1**
	You need to read data from several invoices that are in a folder, and input that data into another system. Each invoice can be seen as a transaction, because there is a repetitive process for each of them (i.e. extract the data and input it somewhere else). 
	
- **Business Scenarios 2**
	There is a list of people and their email addresses in a spreadsheet, and an email needs to be sent to each of them along with a personalized message. The steps in this process (i.e., get data from spreadsheet, create personalized message, and send email) are the same for each person, so each row in the spreadsheet can be considered a transaction. 
	
- **Business Scenarios 3**
	When looking for a new apartment, a robot can be used to make a search according to some criteria. For each result of the search, the robot extracts the information about the property and inserts the data into a spreadsheet. In this case, the details page for each property constitutes a transaction.