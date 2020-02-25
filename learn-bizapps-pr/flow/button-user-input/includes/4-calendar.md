Let's build a flow triggered by a button that will set up automatic
replies to your Office 365 Outlook, which will add separate reply
messages for internal and external emails.

1.  [Sign in to Power Automate](https://flow.microsoft.com/?azure-portal=true). 

1.  On the left vertical menu click **+ Create**.

1.  On the top of the page, you will see **Three ways to make a flow**. Select **Start from blank**, 
    and then select **Instant flow**.

1.  Add **Set Out Of Office** as your flow **Name** and select the **Manually trigger a flow** option.

1.  Click **Create** to start building the flow.

1.  You are now in the flow studio with the title **Set Out of Office** and the 
    **Manually trigger a flow** trigger already added.

1.  Click on **+ Add an input** and select **Date**. Rename **Trigger date** to Start time. 

1.  Click on **+ Add an input** again and select **Date**. Rename **Trigger date** to End time. 
    This is what the trigger action should look like:

    ![Set out-of-office trigger](../media/set-trigger.jpg)

1. Click on **+ New step** and search for automatic replies. 

1. Select **Setup automatic replies (V2)**.

1. Click in **Start Time DateTime** and from the Dynamic content select **Start time**.

1. Click in **End Time DateTime** and from Dynamic content select **End time**.

1. For the Internal Reply Message:

    1.  First, type the following: ```Currently out of office and will return on. If this is an emergency, 
    then you can contact my assistant Jane Doe.```

    1.  Set your cursor after the word **on** in your text, and then select **End time** 
    from Dynamic content.

1. For the External Reply Message:

    1.  First, type ```Currently out of office and will return on```.

    1.  Set your cursor after the word **on** in your text, and then select 
    **End time** from Dynamic content.

1. Here is a screenshot of what the Setup automatic replies (V2) looks like.

    ![Set automatic replies action](../media/set-automatic-replies-action.jpg)

1. Click on the Flow checker, which is available on the top right. If you have 0 errors and warnings, then click on the **X**, then click on **Save**.

1. You can now test the button using your smart phone. Open the app and click on the **Buttons** option on the bottom horizontal menu. You should see the Set Out Of Office button. Select it.

1. Add the Start time and End time as shown below and click **Done** which is available 
on the top right of the screen as shown below.

    ![Test using mobile app](../media/test-using-mobile-app.jpg)

1. To confirm the flow has run successfully, go to Outlook on your local machine, click on **File**, which is on the top left of the top horizontal menu. In Info, click on **Automatic Replies**.

1. You should see the setting you just added using flow.

    ![Automatic replies setting](../media/automatic-replies-setting.jpg)