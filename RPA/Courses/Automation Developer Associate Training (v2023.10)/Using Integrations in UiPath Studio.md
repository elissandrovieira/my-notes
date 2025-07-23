## 🗺️Overview  
In this lesson, we'll guide you through building an automation solution using connectors from UiPath Integration Service. Our use case is to streamline the onboarding process for new hires by integrating HR and IT systems.

We'll demonstrate how to leverage connectors for Microsoft OneDrive, SharePoint, Salesforce, ServiceNow, and Slack. Get ready to learn how to create an efficient onboarding automation process with UiPath Integration Service!

---

## 📺Using Integrations in UiPath Studio

[![](https://embed-ssl.wistia.com/deliveries/354292626d28eceed2d87c28fd39b64950c305d1.jpg?image_play_button_size=2x&image_crop_resized=960x540&image_play_button_rounded=1&image_play_button_color=595959e0)](https://cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Ffast.wistia.net%2Fembed%2Fiframe%2Fljdknzbn29%3Fseo%3Dtrue%26videoFoam%3Dtrue&display_name=Wistia%2C%2BInc.&url=https%3A%2F%2Fuipathvideos.wistia.com%2Fmedias%2Fljdknzbn29%3FembedType%3Diframe%26amp%3Bseo%3Dtrue%26amp%3BvideoFoam%3Dtrue%26amp%3BvideoWidth%3D640&image=https%3A%2F%2Fembed-ssl.wistia.com%2Fdeliveries%2F354292626d28eceed2d87c28fd39b64950c305d1.jpg%3Fimage_crop_resized%3D640x360&key=40cb30655a7f4a46adaaf18efb05db21&type=text%2Fhtml&schema=wistia&wvideo=ljdknzbn29)
### Video steps summary

- **Identify Required Activity Packages:**
    - Identify the activity packages needed for integration tasks (e.g., Microsoft Office 365, Salesforce, servicenow, Slack).
    
- **Install Activity Packages:**
    - Ensure you have the latest activity packages installed in UiPath Studio to leverage the most up-to-date features and integrations available.
    
- **Enable "Use Integration Service " Option:** 
    - After adding a connector to the workflow, checkmark the "Use Connection" box from the properties panel. This will automatically establish the default connection. 
    
- **Access integration Activities:** 
    - Go to the "Integrations" section in UiPath Studio and select the relevant category (e.g., "Microsoft office 365 Activities") for your integration needs. 
    
- **Define Input Arguments:** 
    - Define the necessary input arguments (e.g., UiPath Event, Event connector, Event Object id, Event Object type) to receive information from the Integration Service. 
    
- **Utilize Switch Activity:**
    - Implement the Switch activity in your workflow to route the process flow based on the triggering connector (e.g., OneDrive, Salesforce, ServiceNow).
    
- **Set Up Switch Cases:** 
    - Set up individual cases in the Switch activity for each connector to execute specific actions based on the triggering connector. 
    
- **Use Connector-Specific Activities:** 
    - Inside each Switch case, employ activities specific to the triggering connector (e.g., Office 365 activities for OneDrive, Salesforce activities for Salesforce). 
    
- **Handle Errors and Notifications:** 
    - Include error handling mechanisms to identify issues during the process and take corrective actions, such as logging warning messages or creating incidents in ServiceNow. 
    
- **Send Stakeholder Notifications:** 
    - Use appropriate notification activities (e.g., Slack's "Send Message" activity) to keep stakeholders informed about progress or exceptional scenarios. 
    
- **Save and Publish:** 
    - After successfully implementing the integration and completing the process, save and publish the automation project in UiPath Studio.

### Publish the process

- Once the automation project in Studio is completed, you need to publish it to the Orchestrator instance on the same tenant where the Integration Service is enabled and the trigger will be used.

- The publishing process remains the same as usual, where you can publish the automation project either to a specific folder or to your personal workspace within the Orchestrator. This allows the Integration Service to access and utilize the published project to respond to the specified triggers and events.