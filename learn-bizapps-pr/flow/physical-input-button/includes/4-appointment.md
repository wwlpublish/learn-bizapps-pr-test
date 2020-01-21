Let's build a flow triggered by the Flic button that looks up your next
appointment and sends the attendees an email letting them know you are
running a little late.

1.  [Sign in](https://flow.microsoft.com/?azure-portal=true).

1.  Click on **+ Create** available on the left vertical navigation.

1.  In the Start from blank section click on **Automated flow**.

1.  Name the flow as **Running Late**. Under Choose your flow's triggers search for **Flic**. Select **When a Flic is pressed** and then click **Create**.

	![Running late Flic trigger](../media/running-late-flic-trigger.jpg)

1.  In the Flic button trigger click on the drop-down arrow at the right and select the Flic button you added above. For Events select **click.**

1.  Click on **+ New step**.

1.  In Choose an action, search for Get calendar events and select the **Get calendar view of events (V2)** action.

1.  For Calendar ID select **Calendar**.

9.  Click in **Start Time**. Select **Expression** and type in utc. You should see a **utcNow** option, click on it.

    ![Add utcNow](../media/add-utcnow.jpg)

1. Click **OK**.

1. Click in **End time**. Select Expression and add the formula ```addHours(utcNow(),1)```.

1. Click **OK**.

	The action should look like this.

    ![Get calendar view events](../media/get-calendar-view-events.jpg)

1. Click on **+ New step**.

1. In Choose an action, search for send email. Select the **Send an email (V2)** action.

1. Click in the **To** field and then click on the advanced icon and select **Required attendees** from Dynamic content.

    ![send email sent field](../media/send-email-sent-field.jpg)

    The Send an email (V2) will automatically be added inside the Apply to each loop.

    ![apply each loop](../media/apply-each-loop.jpg)

1. Click on **Send an email (V2)** to expand it.

    ![send email sent field](../media/send-email-sent-field.jpg)

1. In subject type ```Running late for our```.

1. Then click on **Dynamic content** and select **Subject**.

1. After Subject type ```meeting```.

    ![send email subject](../media/send-email-subject.jpg)

1. In Body type
    ```
	Hi there,

    I'm running a little late for our meeting.
	```

	Here is what the full flow looks like.

    ![full running late flow](../media/full-running-late-flow.jpg)

1. Finally, click on **Flow checker** which is available on the top-right of the screen and if there are no errors then click on Save.

Congratulations! You have now successfully built a flow which triggers using a physical button. To test, you need to have the Flic app open in your phone and then click the Flic button once. The flow will check to see if there are any meetings either currently running or coming up between now and the next hour and will send out a notification to all the attendees.
