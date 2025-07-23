## 🗺️Overview 

In this lesson, we'll thoroughly examine a straightforward automation project that uses all the components of the Integration Service.

Our main goal is to present an overview of the use case for this automation project, with a primary focus on streamlining the new hire onboarding process through the Integration Service.

By the end of the lesson, you'll have a clear understanding of how the Integration Service is practically applied in real-world scenarios.

---

## 🏊Let's dive into a business process

![[Pasted image 20250505105824.png]]

1. **To be onboarded users**
	The users that need to be onboarded are managed in SAP SuccessFactors.
	
2. **File containing user list**
	HR Admin exports the users that need to be onboarded from SuccessFactors to an Excel file.
	
3. **User list upload location**
	HR Admin proceeds to manually upload the Excel file containing the list for the users to be onboarded to OneDrive.
	
4. **User onboarding and provisioning**
	Once the list is uploaded to OneDrive, the Support Admin picks it up, and manually provisions in Salesforce the users found in the list.
	
5. **Provisioned users**
	Once the users are successfully provisioned, they are notified via Outlook 365 and Slack.
	
6. **Unprovisioned users**
	Users that present any errors at provisioning time will be included in a ServiceNow ticket.