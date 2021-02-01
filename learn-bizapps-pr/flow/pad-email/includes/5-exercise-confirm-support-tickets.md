In this exercise, you'll develop a flow that sends confirmation emails to received support tickets from customers. 

To execute the flow of the exercise successfully, use the credentials of a valid webmail account. If the account or server information is false, the flow will fail.

1. Launch Power Automate Desktop console and create a new flow named **Ticket confirmation**.

    ![The Build a flow dialog.](..\media\exercise-new-flow.png)

1. Deploy a **Retrieve emails** action and configure it to retrieve all the unread emails that contain the word **Ticket** in their subject line. Populate the **Mail folder** with the main inbox folder of your account.

    ![The Retrieve emails action.](..\media\exercise-retrieve-emails-action.png)

1. To configure the IMAP server, expand the **IMAP server** section of the action and populate the appropriate server information.

    ![The IMAP server section of the Retrieve emails action.](..\media\exercise-retrieve-emails-action-imap.png)

1. Add a **For each** loop to the workspace and set it to iterate through the list with the retrieved emails.

    ![The For each action.](..\media\exercise-for-each-action.png)

1. Inside the loop, add a **Send email** action to send an email to each ticket owner. Set the email subject to contain the subject of the received email with a confirmation notation. The body can optionally include a confirmation text.

    ![The Send email action.](..\media\exercise-send-email-action.png)

1. Expand the **SMTP server** section of the action and populate the SMTP server's appropriate information. 

    ![The SMTP server section of the Send email action.](..\media\exercise-send-email-action-smtp.png)

1. Beneath the **Send email** action, add a **Process emails** action. Set it to move each retrieved email to a folder named **Confirmed tickets**.

    ![The Process emails action.](..\media\exercise-process-emails-action.png)

1. Expand the **IMAP server** section of the action and populate the IMAP server's appropriate information. 

    ![The IMAP server section of the Process emails action.](..\media\exercise-process-emails-action-imap.png)

1. Save the flow and run it to test that every action runs as expected.

    ![The final flow and the save and run buttons.](..\media\exercise-final-flow.png)


