In this exercise, you'll develop a process that will retrieve emails that are related to new support tickets and then send confirmations.

>[!NOTE]
> To run the exercise successfully, use the credentials of a valid webmail account. If the account or server's information is false, the process will fail.

1. Launch WinAutomation and create a new process named **Ticket confirmation**.

    ![Screenshot of the Create New Process window with the name set to Ticket confirmation and under Choose a Tool, the Process Designer is highlighted.](..\media\create-process.png)

1. Deploy a **Retrieve Emails** action and configure it to retrieve all the unread emails that contain the word **Ticket** in their subject line. The **Mail Folder** field will be populated automatically with the main inbox folder of your account.

    ![A Retrieve Emails action with populated fields.](..\media\exercise-retrieve.png)

1. Go to the **IMAP Server** tab of the action and populate the IMAP server's information.

    ![The IMAP Server tab of the Retrieve Emails action.](..\media\exercise-retrieve-imap.png)

1. Add a **For Each** loop to the workspace and then set it to iterate through the list that contains the retrieved emails.

    ![A For Each loop with the retrieved email as input.](..\media\exercise-loop.png)

1. Inside the loop, add a **Send Email** action to send an email to each ticket owner. Set the email subject to contain the subject of the received email with a confirmation notation. The body can contain a confirmation text.

     ![A Send Email action with populated fields.](..\media\exercise-send.png)

1. Go to the **SMTP Server** tab of the action and populate the chosen SMTP server's information.

    ![The SMTP Server tab of the Send Email action.](..\media\exercise-send-smtp.png)

1. Beneath the **Send Email** action, add a **Process Emails** action. Set the action to move each retrieved email to a folder named **Confirmed Tickets**.

    ![A Process Emails action with populated fields.](..\media\exercise-process.png)

1. Go to the **IMAP Settings** tab of the action and populate the chosen IMAP server's information.

    ![The IMAP Settings tab of the Process Emails action.](..\media\exercise-process-imap.png)

1. Save the process and then run it to test that every action runs as expected.

     ![Ticket confirmation - Process Designer with the Save and Run buttons highlighted.](..\media\exercise-save.png)
