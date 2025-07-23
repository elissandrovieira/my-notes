## 🗺️Overview

Robot provisioning refers to the process of setting up and configuring robots within Orchestrator.

You can connect your attended and unattended robots to Orchestrator in different ways. 

On a high level it involves adding robots to Orchestrator, establishing the necessary connections, and configuring their properties to enable effective management and execution of automation processes.

---

## 🤖User and Robot accounts

In Orchestrator, both human users with attended licenses (Robot or Studio) and unattended robots need to have a corresponding Orchestrator user.

Depending on the deployment type and the organizational setup, users are added and managed in different ways:

- Users can be added locally in on-premises, standalone Orchestrator.
- Users have to be added in Automation Cloud, then in cloud Orchestrator to grant them a license.
- Users can be added from Active Directory for both on-premises and cloud Orchestrator if the integration was configured beforehand.

Robot accounts have to be created in Automation Cloud, and they behave like user accounts regarding permissions. The only differences compared to user accounts are: 

- Robot accounts aren't allowed to have any interactive-related process configuration.
- No email address is required to create a robot account.

---

## 🤖Automatic robot creation

To simplify the attended and unattended robot creation, as well as the license provisioning, the automation robot creation can be enabled at user level, for both attended and unattended robots, and at group level for attended robots.

Basically, you enable the Attended Robot or Unattended Robot toggle at the account or group level, configure the various settings (robot execution settings, machine login credentials, if applicable), and a floating robot with those attributes is created.

**Note:** You can only enable attended robot auto-provisioning for user groups, unattended robot auto-provisioning is not possible. 

---

## 💻Machine templates

Robots run on physical or virtual workstations. These are mirrored in Orchestrator by entities called machines. The machines in Orchestrator work as API key generators, authorizing the connection between the robots and Orchestrator.

There are two types of machines in Orchestrator:

- Machine templates: this allows the connection to multiple workstations with a single API key.
- Standard machines: this allows the connection between Orchestrator and a single machine. This is suitable for scenarios in which robots need to run on specific machines.

---

## 🪪License distribution

In Orchestrator, licenses are also called runtimes. They're allocated at machine template level, under Machines in the Tenant menu.

The number of runtimes allocated there should be matched with the maximum number of users which can run on a single machine connected using that machine template. On a regular Windows machine, only one user can run. But on a Windows server machine, multiple users can run simultaneously.

Licenses are consumed as soon as a machine is connected to Orchestrator, no matter the number of users running on it.