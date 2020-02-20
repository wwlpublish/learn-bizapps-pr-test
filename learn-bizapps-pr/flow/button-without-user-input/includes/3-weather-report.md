This lesson shows how to build a flow that is triggered by a button that
will notify you of the weather forecast for today and tomorrow. This example uses
the **MSN Weather** connector.

1.  [Sign in to Power Automate](https://flow.microsoft.com/?azure-portal=true). 

1.  On the left navigation pane, select **+ Create**.

1.  This page shows the ways that you can make a flow. The first way
    is **Start from blank**, where you will select **Instant flow**.
    
1.  Add **Weather Information** as the flow name and select the **Manually trigger a flow** option
    to trigger this flow.

1.  Select **Create** to start building the flow.

    The **Manually trigger a flow** trigger should already be added.
    On the upper left of the page, **Weather Information** will be shown as your
    flow name.

1.  Select the **+ New step** button.

1.  In **Choose an action**, if you don't already see the **MSN Weather** connector, then search for **MSN** and select **MSN Weather**.

	![MSN weather connector icon](../media/msn-weather-connector-icon.png)

1. Select **Get forecast for today**. Wait until it creates its connection.

1. Click the **Location** field, and then select the **Full address** option from the **Dynamic content** dialog box.

1. Leave the **Units** field as **Imperial** or you can change it to **Metric**.

1. Select the **+ New step** button again.

1. In **Choose an action**, if you don't already see the **MSN Weather** connector, then search for **MSN** and select **MSN Weather**.
	
	![MSN weather connector icon](../media/msn-weather-connector-icon.png)

1. Select **Get the forecast for tomorrow**.

1. Click the **Location field**, and then select **Full address** from the **Dynamic content** dialog box. This time, you might need to scroll to the bottom of the dialog box to find **City**.

1. Leave the **Units** field as **Imperial** or change it to **Metric**.

1. Select the **+ New step** button again.

1. In **Choose an action**, select the **Notifications** option. If you don't already see the **Notifications**        option, search for **Notifications** and then select it.

	![Notifications connector icon](../media/notifications-connector-icon.png)

1. Select **Send me a mobile notification**.

1. In the **Text** field, enter **Today's forecast calls for:** and then,
    by using a combination of manually entered text and option selections, you can create a personalized list of actions. You can select options such as Day Conditions, Day Rain Chance, Day Summary,
    Night Conditions, Night Rain Chance, Night Summary, and so on. Make sure that 
    the dynamic content comes from **Get forecast for today**.

1. In the same **Text** field, enter **Tomorrow's forecast is:** and then, by
    using a combination of manually entered text and option selections, you can create a personalized list of actions. You can select options such as Day Conditions, Day Rain Chance, Day Summary, Night
    Conditions, Night Rain Chance, Night Summary, and so on. Make sure that the
    dynamic content comes from **Get the forecast for tomorrow**.

1. Select **Flow check**, which is available on the upper right of the page, and confirm that you have zero errors and warnings. Select **Save**.

    The following screenshot shows an example of the flow.

    ![complete flow](../media/complete-flow.png)

    The following screenshots show examples of the flow actions.
    
    ![Notification action today's forecast](../media/notification-action-todays-forecast.png)

    ![Notification action tomorrow's forecast](../media/notification-action-tomorrows-forecast.png)

    The following screenshot shows what the Microsoft Power Automate app
    notification looks like.

    If the location service hasn’t already been allowed for the app, then you will be 
    prompted to accept that when this button flow is run. If you don’t allow it, then 
    the flow will fail. You will have to go into your browser settings (which varies between 
    browsers) and grant Power Automate flow access to your location if you’ve denied it once before.

	![Weather information notification](../media/weather-information-notification.png)
