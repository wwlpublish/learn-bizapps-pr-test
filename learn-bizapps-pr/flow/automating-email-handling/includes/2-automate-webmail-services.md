WinAutomation enables the automation of webmail services through the **Email** actions. These actions can retrieve email messages from an Internet Message Access Protocol (IMAP) server and process them, or they can send messages through a Simple Mail Transfer Protocol (SMTP) server. 

## Configure IMAP and SMTP servers

Before using **Email** actions, you need to configure the server that handles the chosen email account.

To configure the IMAP server to retrieve and process emails, go to the **IMAP Server** tab in the **Retrieve Emails** action properties. 

![The IMAP Server tab of the Retrieve Emails action.](..\media\retrieve-emails-imap-tab.png)

> [!NOTE]
> In the **Retrieve Emails** action, this tab is called **IMAP Server**, whereas in the **Process Emails** action, the tab is called **IMAP Settings**. 

In the **IMAP Server** tab, populate the address, port of the server, and your account credentials. If untrusted certificates are permitted, or if the server uses TLS/SSL, select the **Accept Untrusted Certificates** or the **Enable SSL** options, respectively. 

![The IMAP Server tab populated.](..\media\retrieve-emails-imap-tab-populated.png)

To configure the SMTP server to send emails, go to the **SMTP Server** tab in the **Send Email** action properties. The fields are nearly similar to the ones that are found in the **IMAP Server** tab.

![The SMTP Server tab of the Send Email action.](..\media\send-email-smtp-tab.png)

Populate the address, port of the server, and your account credentials. Options to enable SSL/TLS and accept untrusted certificates are also available.

![The SMTP Server tab populated.](..\media\send-email-smtp-tab-populated.png)

## Retrieve emails

The **Retrieve Emails** action retrieves emails that meet specific criteria from the server and optionally saves the included attachments on the desktop.

To limit the retrieved emails, filter them according to their parent folder, state, or keywords that are included in various fields. 

![The Retrieve Emails action.](..\media\retrieve-emails.png)

## Process emails

The **Process Emails** action runs a series of essential operations in the previously retrieved emails. More precisely, options to delete, mark as unread, and move messages to other folders are included. 

![The Process Emails action.](..\media\process-emails.png)

This action accepts as input a list of emails that are specified in the **Retrieve Emails** action.

![The output variable of the Retrieve Emails action.](..\media\retrieve-emails-output.png)

## Send email

The **Send Email** action creates and sends a new email message. In the action's properties, you can specify the following elements:

- Sender
- Sender's displayed name
- Recipient
- CC and BCC recipients
- Subject and body of the new email

![The Send Email action.](..\media\send-email.png)

Optionally, the email body can be written in HTML, and the email can contain attachments. In the **Attachment(s)** field, enter the file's path or a variable that contains a file or a list of files.

![The Body is HTML check box and the Attachments field in the Send Email action.](..\media\send-email-html.png)

