Sometimes, you are hit with last minute meetings and it would be nice to
quickly mark your calendar as busy. This exercise will walk you through
using the Flic button to block your Outlook calendar for an hour.

Here are the steps.

1.  [Sign in](https://flow.microsoft.com/?azure-portal=true).

1.  Click on **+ Create** available on the left vertical navigation.

1.  In the Start from blank section click on **Automated flow**.

1.  Name the flow as Block my calendar. Under Choose your flow's triggers search for Flic. Select **When a Flic is pressed** and then click **Create**.

1.  In Flic button select your configured button. For Events select **hold**.

1.  Click on **+ New step**.

1.  In Choose an action, search create event. Select **Create event (V4)**.

1.  For Calendar ID select **Calendar**.

1.  For Subject type ```Out of office```.

1. Click in Start Time. Select **Expression** and type ```utc```. You should see **utcNow** option, click on it then click **OK**.

1. Click in End time. Select Expression and add the formula ```addHours(utcNow(),1)```.  Click **OK**.

1. Select your **Time zone**.

1. Finally, click on **Flow checker** which is available on the top-right of the screen and if there are no errors then click on Save.

Congratulations! You have now successfully built a flow which will trigger using your physical button. Simply holding the button will automatically block your Outlook calendar for an hour.
