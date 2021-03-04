Exception handling is often added to an already developed flow, when risks have been identified by testing.

In this exercise, you'll add exception handling rules to a flow that has already been developed and tested.

## Set up exception handling for an individual action

This flow downloads an Excel file to the user’s desktop, and proceeds to modify its data into a new worksheet.

The **Download from Web** action has been identified as a potential risk, because internet connectivity isn't always stable.

Edit the action and select **On error**. Then, activate the following options:

- Retry the action
- Run the **Check Web Access** subflow
- Continue flow run, by repeating the action.

The result should look like this:

![Exception Handling in the Download from Web action's properties.](..\media\download-from-web-action-properties.png)

If this action fails, it will first retry after 2 seconds.
If the retry fails, the **Check Web Access** subflow will run. This subflow has been designed to ping [https://www.microsoft.com](https://www.microsoft.com), to check whether there are issues with web connectivity - if the ping action produces a **Failed** result, a log entry is created in a text file on the user’s desktop, and the flow is stopped.

![Screenshot of the created flow in the Workspace.](..\media\workspace.png)

If this computer's internet connectivity is at fault, the flow will end. If not, the action’s exception handling will continue, so the action will be repeated.

## Set up exception handling for a block of actions

Having ensured that the **Download from Web** action will run as intended, let’s proceed to the part of the flow that utilizes Excel to modify the file’s data.

After the file is opened, a series of actions are performed on its contents. Due to hardware limitations and the size of the data, the performance of the computer where this task is run is sometimes reduced, which causes Excel to become unresponsive. For this reason, you will have to add exception handling to all the Excel-related actions, because there is no single action that poses the risk.

To achieve this, add a **On block error** action after the file is opened, and configure it so that it runs the **Restart Excel** subflow, and then repeats the failed action:

![Screenshot of the On block error action's properties.](..\media\on-block-error-action-properties-b.png)

Press **OK**, and move the **End** action after the file is closed.

The **Restart Excel** subflow saves the file in its current state, closes it, and then reopens it. Therefore, if any of the Excel-related actions fails, the flow will save and close the file, reopen it, and attempt to resume running.
