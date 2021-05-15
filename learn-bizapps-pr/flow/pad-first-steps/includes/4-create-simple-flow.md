In this unit, you'll develop a flow that converts dates in the European format (DD/MM/YYYY) to the American format (MM/DD/YYYY). The flow will retrieve the date from the clipboard when the **Alt + 1** keys are pressed, and it will return the converted date. 

To create the flow:

1. Launch Power Automate Desktop and select the **New flow** button in the console.

    ![Screenshot of the New flow button in the console.](..\media\console-new-flow.png)

1. Populate a name for the flow and then select the **Create** button. In this example, the flow is named **Date conversion**.

    ![Screenshot of the Build a flow dialog box.](..\media\console-build-new-flow.png)

1. When the flow designer is launched, use the **Actions** pane to search for and select the **Wait for shortcut key** action.

    ![Screenshot of the actions pane.](..\media\actions-pane.png)

1. Set the action to wait for the **Alt + 1** keys.

    ![Screenshot of the Wait for shortcut key action.](..\media\wait-for-shortcut-key-action.png)

1. Add a **Get clipboard text** action to retrieve the current content of the clipboard.

    ![Screenshot of the Get clipboard text action.](..\media\get-clipboard-text.png)

1. Deploy a **Convert text to datetime** action to convert the retrieved text to a datetime variable. The text represents the European date format, so configure the custom format in the action's properties.

    ![Screenshot of the Convert text to datetime action.](..\media\convert-text-to-datetime.png)

1. To convert the datetime variable to the American date format, use the **Convert datetime to text** action with the appropriate custom format in its properties.

    ![Screenshot of the Convert datetime to text action.](..\media\convert-datetime-to-text.png)

1. Use the **Set clipboard text** action to set the final date as the current content of the clipboard.

    ![Screenshot of the Set clipboard text action.](..\media\set-clipboard-text.png)

1. To test the flow, copy a date in the European format and select the **Run** button to verify that the flow returns the American date format.

    ![Screenshot of the run button in the flow designer.](..\media\run-flow-icon.png)

1. If you want to check how every single action is implemented, you can run the flow step-by-step by using the **Run next action** button.

    ![Screenshot of the Run next action button in the flow designer.](..\media\run-next-action-icon.png)

1. If the flow runs as expected, select **Save** and then close the flow designer.

    ![Screenshot of the Save button in the flow designer.](..\media\save-icon.png)

1. Run your flow manually through the **Run** button in the console. Use the date **14/03/2021** as an example and check that the flow returns **03/14/2021**. If you want to stop running the flow, select the **Stop** button.

    ![Screenshot of the run button in the console.](..\media\run-date-conversion-flow.png)
