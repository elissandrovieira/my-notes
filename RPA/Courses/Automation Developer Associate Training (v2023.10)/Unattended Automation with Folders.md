## 🗺️Overview

Functionally, the purpose of attended automation is to have the robots ready to take over the undesirable tasks when the human users need it, in their cycle of work and during work hours.

When it comes to unattended automation, the purpose is quite different: the robot needs to be busy as much as possible, with as little human input as possible. 

---

## 💻Background and Foreground processes

| ![[Pasted image 20250504231401.png]] | A background process, also called a headless process, refers to a job that runs without interacting with any sort of UI. When built in UiPath Studio, a process needs to be set to start in the background.<br><br>On the other hand, foreground processes use a graphical UI.<br><br>Based on this differentiation, a foreground process can run in parallel with one or more background processes in attended automation, for example. |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

---

## ⚙️Unattended Automation Setup

| ![[Pasted image 20250504231601.png]] | The first thing to keep in mind is that unattended robots don't exist as independent entities. As we saw in the previous lesson, they are a combination between a user or robot account and a machine. From this perspective, a better name for a robot is execution slot. But this doesn’t sound too exciting, so let’s stick to robot.<br><br>To make the setup simple, one setting is enough: enable unattended robot for the account. This allows that user to use runtimes to execute unattended jobs on a machine. In Orchestrator, we need to define at least one machine template, which we can then use to connect physical or virtual machines to Orchestrator. |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |


## 🤔What makes unattended automation with folders truly effective?

- **The use of folders and job priorities**
	By accurately reflecting the business hierarchies with the help of folders, roles and permissions, we can control the access to automation processes and make sure the effort is spent where it brings the most return. Job priorities can ensure that business priorities are well reflected in the automation process. 
	
- **The separation of processes based on UI interaction**
	Processes in Orchestrator are now differentiated between those that interact with the user interface (known as foreground processes) and those that don't, called background or headless processes.
	 
	This has a significant impact on the way automation jobs are executed. An unattended robot can simultaneously run a foreground job and as many headless jobs as available runtimes on a machine.
	
- **The license allocation per machine**
	Allocating licenses (runtimes) per machine makes sure that their consumption is optimized. For example, on a Windows Server machine, multiple robots can open sessions and run unattended jobs up to the maximum number of runtimes. 
	
- **Custom job allocation strategies**
	Unattended automation was designed in Orchestrator to ensure resource optimization and effectiveness. But there are cases in which business logic is more important. Orchestrator offers a couple of features and options to allow the customization of the job allocation process so that certain jobs or resources are available only to certain users.