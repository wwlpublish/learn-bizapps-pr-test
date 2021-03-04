If your organization uses an Exchange server, Power Automate Desktop enables email handling through the Exchange actions. You can use these actions to connect to an Exchange server and retrieve, send, or process emails from it.

## Connect to an Exchange server

Before deploying any Exchange actions, you have to use the **Connect to Exchange server** action to establish a connection with a specified Exchange server.

In the action properties, you can set the Exchange server's version and select whether the server will be detected automatically through the email address.

Regarding the server credentials, you can choose between setting them to the Exchange default or specifying them manually. The action stores the established connection to a variable for late use in other Exchange actions.

![Properties of the Connect to Exchange server action dialog.](..\media\connect-exchange-action.png)

## Retrieve Exchange email messages

If you want to retrieve emails that meet specific criteria from an Exchange folder, you can use the **Retrieve Exchange email messages** action.

To limit the retrieved emails, you can filter them according to their parent folder, state, or keywords included in various fields. In case the retrieved emails contain attachments, the action allows you to save the files locally on your desktop.

![Properties of the Retrieve Exchange email message action dialog.](..\media\retrieve-exchange-action.png)

## Send an Exchange email message

To send an email message, you can deploy the **Send Exchange email message** action that creates and sends new email messages through a previously established Exchange server connection.

In the action's properties, you can specify the following entities:

- Sender
- Sender's displayed name
- Recipient
- CC and BCC recipients
- Subject and body of the new email

Optionally, you can write the email body in HTML or include attachments in the message. To attach a file, enter the file's path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

![Properties of the Send Exchange email message action dialog.](..\media\send-exchange-action.png)

## Process Exchange email messages

After retrieving messages from an Exchange folder, Power Automate Desktop enables you to manipulate them through the **Process Exchange email messages** action.

This action runs a series of essential operations in the previously retrieved emails, like deleting, marking as unread, and moving messages to other folders.

To deploy the actions, you have to use as input a list of emails specified in the **Retrieve Exchange email messages** action.

![Properties of the Process Exchange email messages action dialog.](..\media\process-exchange-action.png)
