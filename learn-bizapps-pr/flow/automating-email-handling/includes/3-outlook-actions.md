In case the Microsoft Outlook is installed on the desktop, WinAutomation supports the automation of it through the **Outlook** actions. These actions can launch or close Outlook, and retrieve, send, process, or save emails. 

## Launch and Close Outlook

The **Launch Outlook** action launches Outlook and creates an instance variable of it. The **Launch Outlook** action doesn't accept any inputs, while the created instance is used as input in other **Outlook** actions.

![The Launch Outlook action.](..\media\launch-outlook.png)

When Outlook is no longer required in the process, deploy the **Close Outlook** action to close its instance.

![The Close Outlook action.](..\media\close-outlook.png)

## Retrieve Email Messages From Outlook

The **Retrieve Email Messages From Outlook** action retrieves emails that meet specific criteria from Outlook and optionally saves the included attachments on the desktop.

To limit the retrieved emails, filter them according to their parent folder, state, or keywords included in various fields. 

![The Retrieve Email Messages From Outlook action.](..\media\retrieve-outlook.png)

In the upper part of the actions' properties, specify the Outlook instance previously created with the **Launch Outlook** action, and the wished Outlook account.

![The Outloook Instance and Account fields of the Retrieve Email Messages From Outlook action.](..\media\retrieve-outlook-account.png)

## Send Email Through Outlook

The **Send Email Through Outlook** action creates and sends a new email message through Outlook. In the action's properties, you can specify:

- The sender
- The sender's displayed name
- The recipient
- The CC and BCC recipients
- The subject and the body of the new email

![The Send Email Through Outlook action.](..\media\send-outlook.png)

Optionally, the email body can be written in HTML, and the email can contain attachments. In the **Attachment(s)** field, enter the files' path or a variable containing a file or a list of files.

![The Body is HTML checkbox and the Attachments field in the Send Email Through Outlook action.](..\media\send-outlook-html.png)

In the upper part of the actions' properties, specify the Outlook instance previously created with the **Launch Outlook** action, and the wished Outlook account.

![The Outloook Instance and Account fields of the Send Email Through Outlook action.](..\media\send-outlook-account.png)

## Process Email Messages in Outlook

The **Process Email Messages in Outlook** action executes a series of essential operations in the previously retrieved emails. More precisely, there are options to delete, mark as unread and move messages to other folders. 

![The Process Email Messages in Outlook action.](..\media\process-outlook.png)

This action accepts as input a list of emails, which is specified in the **Retrieve Email Messages From Outlook** action.

![The output variable of the Retrieve Email Messages From Outlook action.](..\media\retrieve-outlook-output.png)

In the upper part of the actions' properties, specify the Outlook instance previously created with the Launch Outlook action, and the wished Outlook account.

![The Outloook Instance and Account fields of the Process Email Messages in Outlook action.](..\media\process-outlook-account.png)

## Save Outlook Email Messages

The **Save Outlook Email Messages** action accepts a list of retrieved emails and saves them locally on the desktop. The list of emails is specified in the **Retrieve Email Messages From Outlook** action.

![The Save Outlook Email Messages action.](..\media\save-outlook.png)

The extracted emails can be saved into various file types, such as Outlook Message, HTML, and text. To set the file's name manually, select **Custom** in the **File Name** and populate the name field. 

![The Save Format, File Name and Save As fields in the ave Outlook Email Messages action.](..\media\save-outlook-file-types.png)

In the upper part of the actions' properties, specify the Outlook instance previously created with the **Launch Outlook** action, and the wished Outlook account.

![The Outloook Instance and Account fields of the Save Outlook Email Messages action.](..\media\save-outlook-account.png)

## Respond To Outlook Mail Message

The **Respond To Outlook Mail Message** action responds to an Outlook message by replying, replying to all, or forwarding. This action accepts as input an email specified in the **Retrieve Email Messages From Outlook** action.

![The Respond To Outlook Mail Message action.](..\media\respond-outlook.png)

The actions contains fields to specify the email body and the attachments. In the **Attachment(s)** field, enter the files' path or a variable containing a file or a list of files.

In case you selected to forward the email, also populate the primary recipient of the email, and the CC and BCC recipients. 

![The Respond To Outlook Mail Message with the Forward option selected in the Response action dropbox.](..\media\respond-outlook-forward.png)