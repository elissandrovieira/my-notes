## 🗺️Overview

Orchestrator is the component of the UiPath Platform for managing automations, robots, and the related entities. Although it comes with different cloud and on-premises delivery options, including persistence, high availability, and disaster recovery, users can access it through a simple web interface.

Orchestrator offers role-based access control and a structure of tenants and folders to replicate organizational structures. Users can run the automation workflows developed in Studio and published to Orchestrator using the unattended robot workforce. Furthermore, Orchestrator is used to manage and distribute licenses, as well as to store automation resources.

___

## 💻Getting to know Orchestrator and its main capabilities

### The Automation Wheel

| ![[Pasted image 20250504220126.png]] | automations must be thoroughly Discovered, solidly Built, effectively Managed, reliably Run, and flexibly Engaged with. Not to mention, we want to accurately Measure and Govern them in all stages of the lifecycle. <br><br>Now it’s time to focus on the Manage and Run phases. |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |


### The Objective of Orchestrator

| ![[Pasted image 20250504220328.png]] | With UiPath Orchestrator it's easy to provision, deploy, trigger, monitor, measure, and track the work of attended and unattended robots—this way our entire digital workforce is secure and productive. |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### What really is the UiPath Orchestrator?

UiPath Orchestrator is a web application that enables us to orchestrate robots in executing automated processes in an organized way.

| ![[Pasted image 20250504221048.png]] | We can look at it this way. Once an automation project is built and tested, we publish it to Orchestrator as Nuget packages, and from there we can deploy it to users’ machines or to robot machines, real or virtual.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![[Pasted image 20250504221215.png]] | - The automation projects published to Orchestrator are stored as packages, along with their versions.  <br><br>- Published packages need to be associated with folders to run automation projects. The pairing of a folder and a published package becomes a process. The robots, with access to that folder, can then run this process.   <br><br>- Through UiPath Assistant, human users can trigger robots to execute processes on their machines. These robots are known as Attended Robots. <br><br>- The robots deployed on separate machines, working without direct human intervention, are called Unattended Robots. Process execution for this type of robot is launched and managed by the Orchestrator. <br><br>- In both cases, process execution is done through jobs. More specifically, each execution of a process by a robot is called an individual job. |
| ![[Pasted image 20250504221516.png]] | - Be it attended or unattended, communication between the Robots and Orchestrator is always initiated by the Robot.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

### The main capabilities of Orchestrator

| ![[Pasted image 20250504221845.png]]                                         | - **Provisioning:** <br><br>Orchestrator creates and maintains the connection with robots and attended users.                                                                                                                   |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![[Pasted image 20250504222229.png]]                                         | - **Control and license distribution:**<br><br>Orchestrator also enables the creation, assignment, and maintenance of licenses, roles, permissions, groups, and folder hierarchies.                                             |
| ![[Pasted image 20250504222314.png]]                                         | - **Running automation jobs in unattended mode:**<br><br>as presented earlier, it enables the creation and distribution of automation jobs in various ways, including through queues and triggers.                              |
| ![[Pasted image 20250504222401.png]]                                         | - **Automation storage and distribution:**<br><br>Orchestrator is the environment enabling the controlled storage and distribution of automation projects, assets, and credentials, as well as large files used in automations. |
| ![[Pasted image 20250504222630.png]]<br>![[Pasted image 20250504222637.png]] | - **Monitoring:**<br><br>with Orchestrator, admins are able to monitor jobs and robots. It also stores logs for auditing and analytics.                                                                                         |
| ![[Pasted image 20250504222709.png]]                                         | - **Inter-connectivity:**<br>finally, Orchestrator acts as the centralized point of communication for third-party solutions or applications.                                                                                    |

### Why we need Orchestrator?

-    It allows us to use large deployments of unattended robots. 

-    Unattended Robots can do their work in executing automation jobs without the need for a human user to sign in at the start of the day.  

-    We get a full view of all the robots and what they are doing at any given time. 

-    We have the possibility to catch the logs and use additional software to analyze them and build reporting capabilities. 

-    We can develop automation processes in such a way that robots get variable values, like passwords, and even files and assets from Orchestrator. This way our data is secure.