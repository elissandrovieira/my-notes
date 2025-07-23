## 🗺️Overview

UiPath Integration Service is a component of the UiPath Platform, designed to simplify and enhance the automation of third-party applications. As automation continues to play a pivotal role in transforming businesses, it's crucial to establish seamless connections between different systems, providing data exchange and streamlined processes.

In this course we'll explore the integration Service's key features, benefits, and functionalities that make it an essential tool for automating processes involving various third-party applications.

---
## 🚪Access the Integration Service

|                                      |                                                                                                  |
| ------------------------------------ | ------------------------------------------------------------------------------------------------ |
| ![[Pasted image 20250505103655.png]] | You can access **Integration Service** from the ribbon on the left side of **Automation Cloud.** |

---

## 🗝️The main key features of UiPath Integration Service

- **Large and Growing Catalog of Pre-built Connectors:**
	The Integration Service offers a wide range of popular, pre-built connectors, making it easier to integrate with various third-party applications. This saves time and effort in setting up connections and simplifies the integration process. 
	
- **Simplified Integration**
	By deploying these connectors, automation processes that involve third-party applications become much simpler. The connectors streamline the integration, allowing robots to interact with the apps automatically and respond to events seamlessly. 
	
- **API and UI Automation Combination**
	Each third-party app connector comes with a dedicated set of activities that enable developers to combine automation at the API level with regular UI automation. This expands the scope of processes that can be automated and provides enhanced design flexibility. 
	
- **Simplified Security**
	The service simplifies the security of automations by allowing connectors to share authentication and authorization usage across different security protocols like OAuth. This makes sure that the automation processes are secure and compliant with the necessary protocols. 
	
- **Enhanced Data Exchange**
	Through seamless third-party app integration, the service enables efficient data exchange between UiPath and external systems, promoting data-driven decision-making and improved insights.
	
- **Event-based Triggers**
	Automations can be triggered based on events occurring in connected systems. This feature allows the UiPath Platform to launch automation workflows in response to specific actions or changes in the third-party applications.

---

## ⚙️The three main components of Integration Service

| CONNECTORS                                                                                                                                                                                                                                                                                                                                                | CONNECTIONS                                                                                                                                                                                                                                                                                                                                                                                                                  | TRIGGERS                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Integration Service comes with a large and growing catalog of popular, pre-built connectors. Any third-party application can be coupled with the specific connector and server-side triggers, so that robots react and respond automatically. Once set up, these connectors can be used in UiPath Studio and other products as well, such as UiPath Apps. | Connections allow you to establish tasks and exchanges between single users and external applications using the authentication process of the API provider. In the Connections tab, you can see a list of all defined connections for all connectors. If the connection status indicates Success, it means that the connections are functional, and you can start using them in UiPath Studio to create automation projects. | Triggers provide a mechanism for subscribing to specific events from the third-party applications, giving you the flexibility to automatically start processes in Orchestrator. Automations can be kicked off based on events in connected systems by using triggers. Before using triggers, you need to have an automation project created, published and a trigger configured for that specific context. |
| ![[Pasted image 20250505104225.png]]                                                                                                                                                                                                                                                                                                                      | ![[Pasted image 20250505104236.png]]                                                                                                                                                                                                                                                                                                                                                                                         | ![[Pasted image 20250505104320.png]]                                                                                                                                                                                                                                                                                                                                                                       |
