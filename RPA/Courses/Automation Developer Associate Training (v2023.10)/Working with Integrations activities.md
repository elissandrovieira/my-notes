## 🗺️Overview

The activities grouped under **Integrations** > **Gmail and Outlook** category in Studio, are newer mail activities that were initially designed for the StudioX profile. These activities can automate the Outlook desktop application, Outlook 365 online, and Gmail accounts.

- These activities can be used only with Use Outlook 365, Use Gmail, or Use Desktop Outlook App scope activities.

- These activities cannot be used with other scope activities like Microsoft Office 365 Scope, GSuite Application Scope, or Exchange Scope.

- Email activities from **UiPath.MicrosoftOffice365.Activities** and **UiPath.GSuite.Activities** packages can't be used with **Use Outlook 365**, **Use Gmail**, or **Use Desktop Outlook App** scope activities.

---

## 🔍How to use the activities

To start using the activities in this package, you must click **Manage Packages** option on the **Design** tab in Studio. Select **All Packages** and search for **Mail**. The package that you must install from the list is called **UiPath.Mail.Activities**.  
Once installed, the activities will become visible in the **Activities** panel under **Integrations** > **Gmail and Outlook**.

---

## 🤔What are the available activities? 

Let's go through all the available activities under the **Integrations** category in Studio:

- Archive Email
	Archives a specified email or email invite. Should be used for the email or invite currently selected in the Outlook desktop app, or in a For Each Email activity when iterating through Gmail or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity. 
	
- Delete Email
	Deletes a specified email or invite. Should be used for the email or invite currently selected in the Outlook desktop app, or in a For Each Email activity when iterating through Gmail or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity. 
	
- For Each Email
	Executes one or more activities for each email or email invite in a specified Outlook folder or with a specified Gmail label. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.
	
	Use this activity when you are working with multiple messages and you want to repeat one or more activities for each individual message:
	
	- For the Outlook desktop app, indicate a folder whose emails to iterate through, or iterate through the folder or the emails that are selected in Outlook when the project is executed.
	- For Outlook 365, indicate a folder whose emails to iterate through.
	- For Gmail, indicate a label whose emails to iterate through. You can select a custom label or one of the following default labels: Inbox, Sent, and Spam.
	
	Add the activities to repeat inside For Each Email and, when you configure the activities, select CurrentMail from the Plus  menu to indicate that you want to repeat the actions for each message in the iteration. For some activities, you must select a specific message field to use from each email: Subject, Body (message body in plain text), Body as HTML (message body formatted in HTML), Date (as text), Bcc, Cc, To, From (sender and recipient fields return a list of email addresses separated by semicolon), or Priority (High, Low, Normal).
	
	  
	
	To learn how to use this activity, see:
	
	- [Tutorial: Iterating through Outlook Mails and Saving Attachments.(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-iterating-through-outlook-mails-and-saving-attachments)
	- [Tutorial: Saving, Renaming, and Moving Attachments.(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-saving-renaming-and-moving-attachments)
	
- Forward Email
	Forwards the specified email or invite. Should be used for the email or invite currently selected in the Outlook desktop app, or in a For Each Email activity when iterating through Gmail or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.  
	  
	**Note:** HTML emails may not look as expected when using the Use Desktop Outlook App activity. Using a Word document for the Body is recommended.
	
- Get Email By Id
	Retrieves the email with the specified ID. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.
	
- Mark Email as Read/Unread
	Marks the specified mail message or invite as Read or Unread. Should be used for the currently selected Outlook email or invite, or in a For Each Email activity when iterating through Gmail, or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.
	
	To learn how to use this activity, see [Tutorial: Extracting Data from Automated Emails and Moving it to a Desktop Application(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-extracting-data-from-automated-emails-moving-it-to-a-desktop-application).
	
- Move Email
	Moves an email to the specified Outlook or Exchange folder, or adds a specified Gmail label to the email. Should be used for the currently selected Outlook email, or in a For Each Email activity when iterating through Gmail, or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.
	
	To learn how to use this activity, see [Tutorial: Extracting Data from Automated Emails and Moving it to a Desktop Application(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-extracting-data-from-automated-emails-moving-it-to-a-desktop-application).
	
- Reply To Email
	Replies to the specified email. Should be used for the currently selected Outlook email, or in a For Each Email activity when iterating through Gmail or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.  
	  
	**Note:** HTML emails may not look as expected when using the Use Desktop Outlook App activity. Using a Word document for the **Body** is recommended.
	
- Save Email
	Saves a specified email or invite to a folder on your computer as a .msg file (for the Outlook desktop app) or .eml file (for Outlook 365 and Gmail). Should be used for the email or invite currently selected in the Outlook desktop app, or in a For Each Email activity when iterating through Gmail or Outlook emails. 
	
	This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.
	
- Save Email Attachments
	Saves the attachments of a mail message or invite to a specified folder on your computer. Should be used for the email currently selected in the Outlook desktop app, or in a For Each Email activity when iterating through Gmail or Outlook emails. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.  
	  
	To learn how to use this activity, see:
	
	- [Tutorial: Iterating through Outlook Mails and Saving Attachments(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-iterating-through-outlook-mails-and-saving-attachments).
	- [Tutorial: Saving, Renaming, and Moving Attachments(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-saving-renaming-and-moving-attachments).
	
- Send Calendar Invite
	Creates and sends a calendar invite. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.
	
- Send Email
	Sends an email from the specified email account. This activity must be added inside a Use Outlook 365, Use Gmail, or Use Desktop Outlook App activity.  
	  
	
	To learn how to use this activity, see:
	
	- [Tutorial: Copying from CSV to Excel and Emailing the File(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-copying-from-csv-to-excel-and-emailing-the-file).
	- [Tutorial: Comparing Files and Emailing Reconciliation Errors(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-comparing-excel-files-and-emailing-reconciliation-errors).
	
	**Note:** HTML emails may not look as expected when using the Use Desktop Outlook App activity. Using a Word document for the **Body** is recommended. 
	
- Use Desktop Outlook App
	Selects an account from the desktop Outlook application to use in your automation and enables StudioX to integrate with Outlook. After you add this activity, add the activities that work with data from the account inside Use Desktop Outlook App. When you configure the activities added inside it, you can select data from the account directly from StudioX.
	
	You can add UI Automation activities directly in the Use Desktop Outlook App activity to quickly automate the interface of Outlook. For this to work, you need to have only one Outlook window open on your machine.
	
	  
	
	To learn how to use this activity, see:
	
	- [Tutorial: Iterating through Outlook Mails and Saving Attachments(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-iterating-through-outlook-mails-and-saving-attachments).
	- [Tutorial: Saving, Renaming, and Moving Attachments(opens in a new tab)](https://docs.uipath.com/studiox/docs/tutorial-saving-renaming-and-moving-attachments).
	
- Use Gmail
	Selects a Gmail account to use in your automation and enables Studio to integrate with Gmail and Google Calendar. After you add this activity, add the activities that work with data from the account inside Use Gmail. When you configure the activities added inside it, you can select data from the account directly from Studio.
	
- Use Outlook 365
	Selects an online Outlook 365 account to use in your automation and enables Studio to integrate with Outlook 365. After you add this activity, add the activities that work with data from the account inside Use Outlook 365. When you configure the activities added inside it, you can select data from the account directly from Studio. 
	
	**Note:** Due to the change to the Graph API, there may exist undocumented differences in behavior between .NET 461 and .NET 5 projects.