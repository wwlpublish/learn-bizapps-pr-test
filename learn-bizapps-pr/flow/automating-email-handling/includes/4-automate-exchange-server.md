If your organization uses an Exchange server, WinAutomation will enable the email handling through the **Exchange** actions. These actions connect to an Exchange server and can also retrieve, send, or process emails from it.

## Connect to an Exchange server

The **Connect to Exchange Server** action establishes a connection with a specified Exchange server. In its properties, you can specify the Exchange server's version and select whether the server will be detected automatically through the email address.

![The Connect to Exchange Server action.](..\media\connect-exchange.png)

The server credentials can be set to the Exchange default or specified manually. The established connection is saved to a variable for late use in other Exchange actions.

![The credential options in the Connect to Exchange Server action.](..\media\connect-exchange-credentials.png)

## Retrieve Exchange email messages 

The **Retrieve Exchange Email Messages** action retrieves emails that meet specific criteria from an Exchange server and optionally saves the included attachments on the desktop.

To limit the retrieved emails, filter them according to their parent folder, state, or keywords that are included in various fields. 

![The Retrieve Exchange Email Messages action.](..\media\retrieve-exchange.png)

## Send an Exchange email message

The **Send Exchange Email Message** action creates and sends a new email message through a previously established Exchange server connection. In the action's properties, you can specify the following entities:

- Sender
- Sender's displayed name
- Recipient
- CC and BCC recipients
- Subject and the body of the new email

![The Send Exchange Email Message action.](..\media\send-exchange.png)

Optionally, the email body can be written in HTML, and the email can contain attachments. In the **Attachment(s)** field, enter the file's path or a variable that contains a file or a list of files.

![The Body is HTML checkbox and the Attachments files in the Send Exchange Email Message action.](..\media\send-exchange-html.png)

## Process Exchange email messages

The **Process Exchange Email Messages** action runs a series of essential operations in the previously established Exchange server connection. More precisely, options to delete, mark as unread, and move messages to other folders are available. 

![The Process Exchange Email Messages action.](..\media\process-exchange.png)

This action accepts as input a list of emails, which is specified in the **Retrieve Email Messages From Outlook** action.

![Tne output variable of the Retrieve Exchange Email Messages action.](..\media\retrieve-exchange-output.png)
