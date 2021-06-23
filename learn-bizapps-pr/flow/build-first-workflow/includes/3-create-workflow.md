In this exercise, you will create your first flow by using Dataverse for Teams. For this example, you'll create an automated workflow that will create a Planner task each time that a message with the word "task" in the subject line is posted to a Teams channel. The flow will need a Planner to create the tasks in. You can identify an existing Planner plan or create a new one.

## Step 1: Create a new flow

To create a new flow, follow these steps:

1. From Teams, open the Power Apps application.

1. From the **Build** tab, select the team on the left for the flow.
   
   Only teams that have a Dataverse for Teams environment will appear.

1. Under the **Built by this team** tab, select **See all**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Microsoft Teams Built by this team tab with See all highlighted.](../media/image-1.png)](../media/image-1.png#lightbox)

1. Select **Cloud flows** on the left to view existing flows. To create a new automated flow, select **+ New > Cloud flow > Automated**.

1. Enter a name for the flow under **Flow name**.

1. Under **Choose your flow's trigger**, scroll or search for **When a new channel message is added**. Select the trigger and then select **Create** to continue.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Build an automated cloud flow dialog box.](../media/image-2.png)](../media/image-2.png#lightbox)

At this point, you have created a new flow, gave it a name, and defined the automated trigger that will start the workflow. The flow is now open in the Power Automate editor and ready to build.

## Step 2: Build the flow in Power Automate editor

To have the flow monitor the correct Teams channel for new messages, select the **Team** and then the **Channel** from the drop-down menu selections. Select **+ New step** to continue.

> [!div class="mx-imgBorder"]
> [![Screenshot of the When a new channel message is added dialog box.](../media/image-3.png)](../media/image-3.png#lightbox)

Search the subject of the messages to see if they have the word "task" in them. In the search bar, enter **Condition** and then select it from the search results. Select **Choose a value** to view the available dynamic content. Dynamic content is the information that the flow has available based on the triggers and previous steps that have taken place.

1. From the list of dynamic content, select **Message subject**.

1. In the middle drop-down menu, select **contains**.

1. Enter **task** in the box on the right.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Condition action with Message contains task.](../media/image-4.png)](../media/image-4.png#lightbox)

Now, when the **Message subject** contains the word "task," it will perform actions in the **If yes** area. The conditions in Power Automate are case-sensitive, so you'll need to add a few more conditions to detect common variations such as "Task" and "TASK." Select **+ Add** and then select **+ Add Row**.

A new selection will appear at the top of the **Condition** window to switch between the following statements:

- **And** - All conditions must be true.

- **Or** - Only one of the conditions must be true.

Change the selection to **Or** and then fill out the other conditions for detecting **"Task"** and **"Tasks"**. For each new row, use **Message subject** from dynamic content and set the condition to **contains**. Select **+ Add** to add more rows.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Condition action with three Or rows.](../media/image-5.png)](../media/image-5.png#lightbox)

The condition action provides two other areas. If the condition is true, then you will want a new Planner task created. No actions are needed if the condition is false, so nothing more is needed in the **If no** condition.

For the **If yes** condition box, select **Add an action**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow with the Add an action button highlighted in the If yes condition box.](../media/image-6.png)](../media/image-6.png#lightbox)

Enter **planner** and then select **Create a task** from the results.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Choose an operation dialog box with search results for planner.](../media/image-7.png)](../media/image-7.png#lightbox)

It might take up to a minute for Power Automate to authenticate into Planner. When Planner comes up, fill out the needed information for the Planner task.

| Field | Value |
|-------|-------|
| Group ID | Select the group that has your Planner |
| Plan ID | Select the Planner for the new task |
| Title | Select dynamic content **Message body content** |
| Start Date Time | Select dynamic content **Message created DateTime** |

When you have completed the task, select **Save** at the bottom of the editing window or in the toolbar to complete the flow.

You can now review the flow and see how it works. The flow is triggered when a new message is posted in a specific Teams channel. Next, you should check for the word "task" in the message subject. If yes, the system creates a new Planner task. If no, the system won't take action.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow. The flow triggers when a new message posts. If the subject contains "task," create a new Planner task.](../media/image-8.png)](../media/image-8.png#lightbox)

## Step 3: Test the flow

Send a message to the Teams channel that the flow is monitoring. In the subject line, enter **task**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the message with the subject New task.](../media/image-9.png)](../media/image-9.png#lightbox)

The Teams connector checks for a new message in three-minute intervals. Next, open Planner and watch for the new task to be created. The message body should be the task title. Select the task to check the start date and see if it was set to the same date as the message.

> [!div class="mx-imgBorder"]
> [![Screenshot of Planner showing the new task.](../media/image-10.png)](../media/image-10.png#lightbox)

You can view the flow's run history for the last 28 days to see how long it takes the flow to run and if it was successful:

1. Open Power Apps for Teams.

1. From the **Build** tab, select the team that has the flow and then select **See all**.

1. Select **Cloud flows** and then select the flow to view more information and the run history.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Create Planner Task from Teams with the 28-day run history highlighted.](../media/image-11.png)](../media/image-11.png#lightbox)

Select the run to see more information and troubleshoot each step of the flow.
