Sometimes, you are hit with last minute meetings and it would be nice to
quickly mark your calendar as busy. This exercise will walk you through
using the Flic button to block your Outlook calendar for an hour.

Here are the steps.

1.  [Sign in to Power Automate](https://flow.microsoft.com/?azure-portal=true).

1.  Select **+ Create** from the left vertical navigation.

1.  In the Start from blank section click on **Automated flow**.

1.  Name the flow **Block my calendar**. Under **Choose your flow's triggers**, search for Flic. Select **When a Flic is pressed** and then click **Create**.

1.  In the Flic button trigger, select your configured button. For Events, select **hold**.

1.  Click on **+ New step**.

1.  In Choose an action, search for and select **Create event (V4)**.

1.  For Calendar ID, select **Calendar**.

1.  For Subject enter **'Out of office'**.

1. Click in the **Start Time** field. Select **Expression** and type **'utc'**. You should see the **utcNow** option, click on it, then click **OK**.

1. Click in the **End time** field. Select Expression and type the formula **addHours(utcNow(),1)**.  Click **OK**.

1. Select your **Time zone**.

1. Finally, click the **Flow checker** icon which is available at the top-right of the screen, and if there are no errors, click **Save**.

Congratulations! You have now successfully built a flow which will trigger using 
your physical button. Simply holding the button will automatically block your 
Outlook calendar for an hour.
