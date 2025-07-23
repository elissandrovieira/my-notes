## 🗺️Overview 

Triggers are essential for automating processes based on specific events, such as new file creation, email receipt, or database updates. By setting up triggers, we can streamline processes, save time, and reduce errors. 

We'll see step-by-step instructions for configuring triggers and understand their significance in creating dynamic automation solutions.

Triggers provide a mechanism for subscribing to specific events from third-party apps, which are passed through the connections. For example, a trigger can initiate an automation such as:

- **Email Received**: an automation can be triggered when a user receives a new email in their inbox. 

- **Form Submission**: an automation can be triggered when a user submits a form on a website. 

- **New File Uploaded**: an automation can be triggered when a new file is uploaded to a cloud storage service.

- **Payment Received** : an automation can be triggered when the inventory level of a product falls below a certain quantity.

These are just a few examples, and there are countless other possibilities depending on the integrations and events supported by the third-party apps and automation platforms you are using.

---

## ⚙️Configuring Triggers****** 

In this demo, we are using Studio version 2022.10 and are logged into the Automation Cloud. 

>[!WARNING]
>**Make sure you already** **have** **an Unattended or Non-production Robot in the Orchestrator tenant. Make sure that the Orchestrator instance is on the same tenant on which the Integration Service has been enabled.**

[![](https://embed-ssl.wistia.com/deliveries/44df61521072f45494fa4c9fddfa4f166afde630.jpg?image_play_button_size=2x&image_crop_resized=960x540&image_play_button_rounded=1&image_play_button_color=595959e0)](https://cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Ffast.wistia.net%2Fembed%2Fiframe%2Fghda5u2c11%3Fseo%3Dtrue%26videoFoam%3Dtrue&display_name=Wistia%2C%2BInc.&url=https%3A%2F%2Fuipathvideos.wistia.com%2Fmedias%2Fghda5u2c11%3FembedType%3Diframe%26amp%3Bseo%3Dtrue%26amp%3BvideoFoam%3Dtrue%26amp%3BvideoWidth%3D640&image=https%3A%2F%2Fembed-ssl.wistia.com%2Fdeliveries%2F44df61521072f45494fa4c9fddfa4f166afde630.jpg%3Fimage_crop_resized%3D640x360&key=40cb30655a7f4a46adaaf18efb05db21&type=text%2Fhtml&schema=wistia&wvideo=ghda5u2c11)

---

## 🤔Wondering how we use these input arguments ?

When we set up a process designed to respond to specific events or actions, we use these input arguments  to identify and process the events accordingly. Here's a brief explanation of how each input arguments can be used:

1. **UiPathEventConnector:** this allows us to determine which connector initiated the process. By knowing the specific connector that triggered the automation, we can customize the workflow to handle the event accordingly. For instance, different actions might be required for events coming from Salesforce compared to events from OneDrive.
2. **UiPathEvent:** this helps us understand the type of event that occurred, whether it is a creation, update, or deletion event. Depending on the event type, different actions or processes can be executed to respond appropriately.
3. **UiPathEventObjectType:** this defines the specific record type resulting from the event. It enables us to identify the nature of the event and the corresponding data involved. This information is vital for determining the subsequent steps in the automation process.
4. **UiPathEventObjectId:** this provides the unique identifier for the object involved in the event. With this ID, we can access the relevant data or resources related to the event and perform the required tasks accordingly.

---

## 🤔How can we manage triggers already created?

- **View Trigger Details**
	To view the details of a trigger, simply click on the specific trigger from the list, and its configuration details will be displayed. 
	
- **Activate/Deactivate a Trigger**
	To activate or deactivate a trigger, follow these steps:
	
	1. Click on the trigger to view its details.
	2. Locate the switch in the upper-left corner of the window.
	3. Toggle the switch to activate (ON) or deactivate (OFF) the trigger as needed.
	
- **Automatic Disabling of Triggers Upon Failure**
	Triggers are subject to a retry mechanism with an exponential back-off strategy in case of failure. The retry attempts are as follows:
	
	- Each subsequent retry is delayed twice as long as the previous attempt.
	- If the Integration Service fails to start the job after 11 attempts (approximately 34 hours) for a single event, the trigger is automatically disabled and set to an error state.
	- Additionally, if the job fails to start for the last 100 events, the trigger is also disabled and set to an error state.
	
- **Delete a Trigger**
	To delete a trigger, follow these steps:
	
	1. Navigate to the Triggers tab in the integrations window.
	2. Locate the trigger you want to delete from the list.
	3. Click the "More Actions" button corresponding to the trigger.
	4. Select the "Delete" option from the menu to remove the trigger from the system.
	

>[!WARNING]
>**Always exercise caution when deleting triggers, as it may impact the functionality of your automation processes. Make sure to confirm the action before proceeding with the deletion.** 

>[!INFO]
>**Important**: event monitoring is set to poll the status every 5 minutes. As such, it could take up to 5 minutes before an associated process starts. We can see a job's details under the Jobs tab in your Orchestrator folder. A job started from the Integration Service will show its source as integration Trigger.

