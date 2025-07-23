## 🗺️Overview

**Tenants** are **isolated environments within a single Orchestrator instance**. Think of them as **separate containers or workspaces** that can host their own:

- Users and roles
- Robots and machines
- Assets and queues
- Processes and triggers
- Audit logs and settings

A single Orchestrator instance can be split into multiple Tenants. Each tenant in an organization can be further subdivided and organized into Folders. Tenants are designed for the purpose of complete isolation of all Orchestrator entities (i.e., Robots, Assets, Queues, etc.) between these segregated instances of your deployment, all without having to maintain multiple Orchestrators. Modern folders provide multiple features such as automatic robot management, hierarchical structures, and fine-grained role assignment for users. 

Consider a typical large company, in which both the data and the business processes are typically separated between divisions like Sales and Finance. But then, the subdivisions would have some of the data or some of the processes separated, at the same time, sharing others.

---

## 💻Orchestrator concepts

- **Robot (Orchestrator)**
	By now you're familiar with UiPath Robot, the component of the UiPath Platform. This is an execution host that runs automation processes published in Orchestrator, as jobs.
	
	In Orchestrator, a robot entity represents an image or the Robot component, controlling its connection and capabilities. The robot entity exists only if it is defined in relation to a user/ robot account in Orchestrator. 
	
- **Folder**
	Folders enable the separation and hierarchical organization of automation entities (processes, queues, assets) and the fine-grained configuration of roles and permissions.
	
	You can create as many sibling folders as you want on a given level. The maximum hierarchy depth is 7, meaning you can have a maximum number of 6 nested subfolders under a first-level folder.
	
	Folders help replicate the organizational hierarchies, with the separation of automated processes between teams, segregation of process data, and access control for users. At the same time, when it makes sense, they allow sharing of the resources and assets.
	
- **Package**
	A project developed in UiPath Studio that is published to Orchestrator as a NuGet package. Multiple versions of the same project can be stored and used.
	
	Packages can also be manually uploaded to Orchestrator.
	
	Additionally, by viewing the versions for a package you can download it from Orchestrator. 
	
- **Process**
	It is a version of a package that's been allocated to a certain folder.
	
	Given that most processes use a queue, asset, or storage bucket, the Package Requirements tab, for when adding a new process, makes it easy to identify which entities your package is using and if they are missing from your folder.
	
- **Job**
	A job represents the execution of a process on a UiPath Robot. You can launch the execution of a job in either attended or unattended mode. You cannot launch a job from Orchestrator on attended robots, unless for debugging purposes using personal workspaces, and they cannot run under a locked screen.
	
- **Heartbeat**
	Attended and unattended robots send a heartbeat to Orchestrator every 30 seconds. This signals to Orchestrator that the connection is working.

---

## 🔠Tenant entities

From the entities defined above, **robots are tenant entities**. This means that they can be allocated to multiple folders in that tenant. Using roles and permissions, the way robots work with each of the folders can be customized. We'll see that a bit later.

**Packages are published to Orchestrator using feeds. The feeds can be configured to be at tenant level, or at folder level**.A package published to the tenant feed can then be used in a process in any of the folders. If it is published using a folder feed, it can't be used for processes in other folders.

There are a couple of other Orchestrator entities which exist at the tenant level:

- **User**
	Both human users and robots are uniquely identified with users in Orchestrator.
	
	On the Accounts & Groups page, in Automation Cloud, you can define local user accounts, robot accounts, and local groups for your organization.
	
	The level of access and the actions that your users can perform is controlled using two elements:
		- accounts, which establish the identity of a user and are used to log in to your UiPath applications
		- roles, which are assigned to accounts in order to grant them certain permissions within the UiPath ecosystem.
	
	Accounts are not created or managed in Orchestrator, only roles and their assignments are.
	
- **Machine (Orchestrator)**
	These are Orchestrator entities corresponding to the workstations where human users and robots work. Using API keys, they enable the connection between the physical or virtual machines and Orchestrator.
	
- **License**
	The right to use Studio and/or Robots, both attended and unattended, is done through licenses. Licenses exist at tenant level, from where they get distributed to users, and consumed when the machines connect to Orchestrator.
	
- **Webhook**
	Webhooks facilitate the communication between Orchestrator and other applications at API level. These are mapped at tenant level, which means they cannot be differentiated between folders and will provide information for the entire tenant.

---

## 📂Folder entities

A folder is a storage area that helps keep your projects separate. From the entities defined at the beginning of the lesson, **processes and jobs are folder entities.** **Packages depend on feed configuration.**

- **Asset**
	An asset is a piece of data stored in Orchestrator for the use of robots. There are four types of assets:
	
	- **Text** - stores only strings (it isn't required to add quotation marks).
	- **Bool** - supports true or false values.
	- **Integer** - stores only whole numbers.
	- **Credential** - contains usernames and passwords that the Robot requires to execute particular processes, such as login details.
	
	Assets can have a global value or a value per user. This means that only the specified user will access a certain value stored in that asset.
	
- **Storage Bucket**
	Storage buckets are entities used for storing files which can be used in automation projects.
	
- **Queue**
	Queues are containers that can hold an unlimited number of items, storing different types of data.
	
	The process of feeding items to a queue is typically different from the process of processing the queue items, and is handled by different robots.
	
- **Trigger**
	Triggers enable the execution of jobs in a preplanned manner:
	
	- Time triggers—they instruct the automation to start at regular intervals.
	- Queue triggers—they instruct the automation to be activated whenever new items are added to your queues. 
	- Event triggers—they instruct the automation to start whenever a specified event occurs.
	

---

## 🔐Personal Workspaces

A personal workspace is a modern folder available for the dedicated use of a particular attended user. Personal Workspaces make it easy to deploy automations to your own robot, for easy regular execution, with the organizational benefits of logging, visibility, and potential reuse. 

They come with the following entities: package feed, machine template, and resources (jobs, assets, logs, queues, etc.).

---

## 👨‍👩‍👧‍👦Roles

Roles are sets of permissions used to control the access of human users and robots to tenant and folder entities.

Each permission is defined from the combination of at least an action type (view, edit, create, and delete) and an entity, be it at the tenant or folder level. For example, you can set up the right to view only the queues in a certain folder, but not the queues from other folders.

---

## 📄Logs in Orchestrator

Logs are time-stamped files that contain informational events, errors, and warning messages relevant to the application. The UiPath Platform has logging capabilities for all of its main components. Logs are created locally of every robot and automation action, then sent to Orchestrator from where they can be filtered, viewed, and analyzed.

There are two types of Orchestrator logs:

- Diagnostic logs generated by UiPath Orchestrator regarding its behavior. 
- Execution logs are logs generated by process execution. The Logs page displays logs generated by Robots in all folders you have access to, including logs generated for jobs started through remote debugging sessions. To access it, navigate to the Automations tab from a folder context, and select Logs tab.