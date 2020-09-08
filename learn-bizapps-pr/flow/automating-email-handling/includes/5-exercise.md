In this exercise, you'll develop a process that retrieves emails related to new support tickets and sends confirmations. 

>[!NOTE]
>To run the process of the exercise successfully, you have to use the credentials of a valid webmail account. If the account's or server's information is false, the process will fail.

1. Launch WinAutomation and create a new process named **Ticket confirmation**.

    ![New Process window.](..\media\create-process.png)

1. Deploy a **Retrieve Emails** action and configure it to retrieve all the unread emails that contain the word **Ticket** in their subject. 

    The **Mail Folder** field is populated automatically with the main inbox folder of your account. 

    ![A Retrieve Emails action with populated fields.](..\media\exercise-retrieve.png)

1. Move to the **IMAP Server** tab of the action and populate the IMAP server's information.

    ![The IMAP Server tab of the Retrieve Emails action.](..\media\exercise-retrieve-imap.png)

1. Add a **For Each** loop to the workspace and set it to iterate through the list containing the retrieved emails.

    ![A For Each loop with the retrieved email as input.](..\media\exercise-loop.png)

1. Inside the loop, add a **Send Email** action to send an email to each ticket owner. Set the email subject to contain the subject of the received email with a confirmation notation. The body can contain a confirmation text.

     ![A Send Email action with populated fields.](..\media\exercise-send.png)

1. Move to the **STMP Server** tab of the action and populate the wished SMTP server's information.

    ![The SMTP Server tab of the Send Email action.](..\media\exercise-send-smtp.png)

1. Below the **Send Email** action, add a **Process Emails** action.  Set the action to move each retrieved email to a folder named **Confirmed Tickets**.

    ![A Process Emails action with populated fields.](..\media\exercise-process.png)

1. Move to the **IMAP Settings** tab of the action and populate the wished IMAP server's information.

    ![The IMAP Settings tab of the Process Emails action.](..\media\exercise-process-imap.png)

1. Lastly, save the process and run it to test that every action runs as expected. 

     ![The final process.](..\media\exercise-save.png)