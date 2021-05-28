Power Automate Desktop enables the automation of webmail services through email actions. You can use these actions to retrieve email messages from IMAP servers or send messages through SMTP servers.

Virtually all major webmail services support IMAP and SMTP and usually require their activation through the settings.

> [!NOTE]
> In case you are using multi-factor authentication on your account, you have to create an application password to use the email actions.

## Configure IMAP and SMTP servers

Before deploying any email action, you have to configure the server that will handle the respective request. The **Retrieve email message** and **Process email message**  actions require an IMAP server, while the **Send email** action requires an SMTP server.

To configure an IMAP server, launch the respective action's properties and expand the  **IMAP server** section.

In this section, populate the address, the server port, and your account credentials. If untrusted certificates are permitted, or the server uses TLS/SSL, select the **Accept Untrusted Certificates** or the **Enable SSL** option, respectively.

![Screenshot of the IMAP server section in the Retrieve email messages action.](..\media\imap-server-config.png)

To configure an SMTP server, launch the properties of the **Send email**  action and expand the **SMTP server** section.

In the **SMTP server** section, populate the address, the server port, and your account credentials. You can also enable SSL/TLS and untrusted certificates if they are applicable.

![Screenshot of the SMTP server section in the Send email action.](..\media\smtp-server-config.png)

## Retrieve email messages

If you want to retrieve emails that meet specific criteria from your mailbox, you can use the **Retrieve email messages** action.

To limit the retrieved emails, you can filter them according to their parent folder, state, or keywords included in various fields. All the available filters are located in the **Email filters** section of the action's properties.

In case the retrieved emails contain attachments, the action allows you to save the files locally on your desktop.

![Screenshot of the Retrieve email messages action.](..\media\retrieve-emails-action.png)

## Process email messages

After retrieving messages from your mailbox, Power Automate Desktop enables you to manipulate them through the **Process email messages** action.

This action runs a series of essential operations in the previously retrieved emails, like deleting, marking as unread, and moving messages to other folders.

To deploy the action, you have to use as input a list of emails specified in the **Retrieve email messages** action.

![Screenshot of the Process email messages action.](..\media\process-emails-action.png)

## Send email

The last action of the email actions is the **Send email** action that creates and sends new email messages. To use the actions, you have to specify the following elements:

- Sender
- Sender's displayed name
- Recipient
- CC and BCC recipients
- Subject and body of the new email

Optionally, you can write the email body in HTML or include attachments in the message. To attach a file, enter the file's path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

![Screenshot of the Send email action dialog.](..\media\send-email-action.png)
