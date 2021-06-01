If you've installed Microsoft Outlook on your desktop, Power Automate Desktop enables you to automate its operation through the Outlook actions.

You can use these actions to launch or close Outlook and retrieve, send, process, or save emails from all your connected accounts.The ability to handle multiple accounts in the same flow allows you to handle emails from multiple sources and manage all your accounts simultaneously.

## Launch and close Outlook

Before deploying any Outlook actions, you have to use the **Launch Outlook** action to launch Outlook and create an instance variable. This action doesn't accept any parameters, while the Outlook actions require the created instance as an input parameter.

![Screenshot of the Launch Outlook action dialog.](..\media\launch-outlook-action.png)

When you no longer need the created instance in the flow, you can deploy the **Close Outlook** action to close it.

![Screenshot of the Close Outlook action dialog.](..\media\close-outlook-action.png)

## Retrieve email messages from Outlook

If you want to retrieve emails that meet specific criteria from an Outlook folder, you can use the **Retrieve email messages from Outlook** action.

To limit the retrieved emails, you can filter them according to their parent folder, state, or keywords included in various fields. In case the retrieved emails contain attachments, the action allows you to save the files locally on your desktop.

![Screenshot of the Retrieve email messages from Outlook action dialog.](..\media\retrieve-emails-outlook.png)

## Send email message through Outlook

To send an email message through Outlook, you can deploy the **Send email message through Outlook** action that creates and sends new email messages. In the action's properties, you can specify the following entities:

- Sender
- Sender's displayed name
- Recipient
- CC and BCC recipients
- Subject and body of the new email

Optionally, you can write the email body in HTML or include attachments in the message. To attach a file, enter the file's path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

![Screenshot of the Send email message through Outlook action dialog.](..\media\send-email-outlook.png)

## Process email messages in Outlook

After retrieving messages from your mailbox, Power Automate Desktop enables you to manipulate them through the **Process email messages in Outlook** action.

This action runs a series of essential operations in the previously retrieved emails, like deleting, marking as unread, and moving messages to other folders.

To deploy the actions, you have to use as input a list of emails specified in the **Retrieve email messages from Outlook** action.

![Screenshot of the Process email messages in Outlook action dialog.](..\media\process-emails-outlook.png)

## Save Outlook email messages

Except for processing, Power Automate Desktop enables you to save retrieved emails through the **Save Outlook email messages** action.

This action accepts a list of retrieved emails specified in the **Retrieve email messages from Outlook** action and saves them locally on the desktop.

You can save the extracted emails into various file types, such as Outlook Message, HTML, and text. If you want to name the files manually, select **Custom** in the **File name** dropdown menu and populate the **Save as** field.

![Screenshot of the Save Outlook email messages action dialog.](..\media\save-emails-outlook.png)

## Respond to Outlook message

If you want to reply to or forward an email, you can use the **Respond to Outlook message** action. This action responds to an Outlook message by replying, replying to all, or forwarding.

In the action properties, you have to enter an email variable specified in the **Retrieve email messages from Outlook** action.

Besides the email body, the action allows you to attach files in your replying message. To attach a file, enter the file's path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

If you select to forward an email, you should also populate the primary recipient and the CC and BCC recipients.

![Screenshot of the Respond to Outlook message action dialog.](..\media\respond-email-outlook.png)
