WinAutomation enables the automation of webmail services through the **Email** actions. These actions can retrieve email messages from an IMAP server and process them, or send messages through an SMTP server. 

## Configure IMAP and SMTP server

Before using **Email** actions, you have to configure the server that handles the wished email account.

To configure the IMAP server to retrieve and process emails, navigate to the **IMAP Server** tab in the respective action's properties. 

![The IMAP Server tab of the Retrieve Emails Action.](..\media\retrieve-emails-imap-tab.png)

> [!NOTE]
> In the **Retrieve Emails** action, this tab is called **IMAP Server**, while in the **Process Emails** action is called **IMAP Settings**. 

In the tab, populate the address and the port of the server, and the credentials of your account. In case untrusted certificates are permitted or the server uses TLS/SSL, enable the respective options. 

![The IMAP Server tab populated.](..\media\retrieve-emails-imap-tab-populated.png)

To configure the SMPT server to send emails, navigate to the **SMTP Server** tab in the **Send Email** action's properties. The fields are almost the same as in the **IMAP Server** tab.

![The SMTP Server tab of the Send Email Action.](..\media\send-email-smtp-tab.png)

As previously described, populate the address and the port of the server, and the credentials for your account. There also options to enable SSL/TLS and accept untrusted certificates.

![The SMTP Server tab populated.](..\media\send-email-smtp-tab-populated.png)

## Retrieve Emails

The **Retrieve Emails** action retrieves emails that meet specific criteria from the server and optionally saves the included attachments on the desktop.

To limit the retrieved emails, filter them according to their parent folder, state, or keywords included in various fields. 

![The Retrieve Emails Action.](..\media\retrieve-emails.png)

## Process Emails

The **Process Emails** action executes a series of essential operations in the previously retrieved emails. More precisely, there are options to delete, mark as unread and move messages to other folders. 

![The Process Emails Action.](..\media\process-emails.png)

This action accepts as input a list of emails specified in the **Retrieve Emails** action.

![The output variable of the Retrieve Emails Action.](..\media\retrieve-emails-output.png)

## Send Email

The **Send Email** action creates and sends a new email message. In the action's properties, you can specify:

- The sender
- The sender's displayed name
- The recipient
- The CC and BCC recipients
- The subject and the body of the new email

![The Send Email Action.](..\media\send-email.png)

Optionally, the email body can be written in HTML, and the email can contain attachments. In the **Attachment(s)** field, enter the files' path or a variable containing a file or a list of files.

![The Body is HTML checkbox and the Attachments field in the Send Email Action.](..\media\send-email-html.png)

