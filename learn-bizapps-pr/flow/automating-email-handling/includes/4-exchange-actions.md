If your organization uses an Exchange server, WinAutomation enables the email handling through the **Exchange** actions. These actions connect to an Exchange server, and retrieve, send, or process emails from it.

## Connect to Exchange Server

The **Connect to Exchange Server** action establishes a connection with a specified Exchange server. In its properties, you can specify the Exchange server's version and select whether the server will be detected automatically through the email address.

![The Connect to Exchange Server action.](..\media\connect-exchange.png)

The credentials of the server can be set to the Exchange default or specified manually. The established connection is saved to a variable for late use in other Exchange actions.

![The credential options in the Connect to Exchange Server action.](..\media\connect-exchange-credentials.png)

## Retrieve Exchange Email Messages 

The **Retrieve Exchange Email Messages** action retrieves emails that meet specific criteria from an Exchange server and optionally saves the included attachments on the desktop.

To limit the retrieved emails, filter them according to their parent folder, state, or keywords included in various fields. 

![The Retrieve Exchange Email Messages action.](..\media\retrieve-exchange.png)

## Send Exchange Email Message

The **Send Exchange Email Message** action creates and sends a new email message through a previously established Exchange server connection. In the action's properties, you can specify:

- The sender
- The sender's displayed name
- The recipient
- The CC and BCC recipients
- The subject and the body of the new email

![The Send Exchange Email Message action.](..\media\send-exchange.png)

Optionally, the email body can be written in HTML, and the email can contain attachments. In the **Attachment(s)** field, enter the files' path or a variable that contains a file or a list of files.

![The Body is HTML checkbox and the Attachments files in the Send Exchange Email Message action.](..\media\send-exchange-html.png)

## Process Exchange Email Messages

The **Process Exchange Email Messages** action executes a series of essential operations in the previously established Exchange server connection. More precisely, there are options to delete, mark as unread and move messages to other folders. 

![The Process Exchange Email Messages action.](..\media\process-exchange.png)

This action accepts as input a list of emails, which are specified in the **Retrieve Email Messages From Outlook** action.

![Tne output variable of the Retrieve Exchange Email Messages action.](..\media\retrieve-exchange-output.png)