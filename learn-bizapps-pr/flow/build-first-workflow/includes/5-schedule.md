Some business processes and tasks are done on a schedule. This could be a weekly reminder for the team to turn in expense reports, checking for overdue tasks each day, or sending out a daily report. With Dataverse for Teams scheduled flows, create scheduled workflows to automate these actions making them more consistent and less time consuming.

To create a new schedule flow:

1. Open Teams and select the Power Apps for Teams app.

1. From the **Build** tab, select the Team on the left to store the flow.

1. Under the **Built by this team** tab, select **Select all**.

1. Select **+ New** > **Cloud Flow** > **Scheduled**.

1. Provide a **Name** and select a **Starting** date and time for the flow. This will set the first time the flow will run.

1. For the **Repeat every** section, set the amount of time until the flow runs again by setting the number of seconds, minutes, hours, days, weeks, or months between each flow run.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Build a scheduled cloud flow dialog.](../media/image-24.png)](../media/image-24.png#lightbox)

   Selecting **Week** will bring up more options to define which days of the week to run the flow. For example, you can run the flow on Tuesday and Thursday each week.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the dialog with repeat set to every one week on Tuesdays and Thursdays.](../media/image-25.png)](../media/image-25.png#lightbox)

1. Select **Create** to open the Power Automate editor and start building the rest of the flow.

Once a schedule flow is triggered, it will process the tasks that are defined in the flow just like any other flow. For example, here's a simple flow to send out a reminder to submit expense reports as a Teams message every Friday. Use the text editing controls in the message window to create hyperlinks to make it easy for your end users to find important resources.

> [!div class="mx-imgBorder"]
> [![Screenshot of the completed flow for Friday expense reminders.](../media/image-26.png)](../media/image-26.png#lightbox)
