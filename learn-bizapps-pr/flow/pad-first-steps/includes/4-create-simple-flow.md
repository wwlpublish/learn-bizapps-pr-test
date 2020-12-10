In this unit, we'll develop a flow that converts dates in the European format (d/m/yyyy) to the American format (m/d/yyyy). The flow will retrieve the date from the clipboard when the **Alt + 1** keys are pressed, and it will return the converted date. 

To create the flow:

1. Launch Power Automate Desktop and select the **New flow** button in the console.

    ![The New flow button in the console.](..\media\console-new-flow.png)

1. Populate a name for the  flow and select the **Create** button. In this example, we named our flow **Date conversion**

    ![The Build a flow dialog.](..\media\console-build-new-flow.png)

1. When the flow designer is launched, add a **Wait for hotkey** action in the workspace and set it to wait for the **Alt + 1** keys.

    ![The Wait for hotkey action.](..\media\wait-for-hotkey-action.png)

1. Add a **Get clipboard text** action to retrieve the current content of the clipboard.

    ![The Get clipboard text action.](..\media\get-clipboard-text.png)

1. Now, deploy a **Convert text to datetime** action to convert the retrieved text to a datetime variable. The text represents the European date format, so configure the respective custom format in the action's properties. 

    ![The Convert text to datetime action.](..\media\convert-text-to-datetime.png)

1. To convert the datetime variable to the American date format, use the **Convert datetime to text** action with the appropriate custom format in its properties.

    ![The Convert datetime to text action.](..\media\convert-datetime-to-text.png)

1. Use the **Set clipboard text** action to set the final date as the current content of the clipboard. 

    ![The Set clipboard text action.](..\media\set-clipboard-text.png)

1. To test the flow, copy a date in the European format and select the **Run** button to verify that the flow returns the respective American date.

    ![The run button in the flow designer.](..\media\run-flow-icon.png)

1. In case you want to check how every single action is executed, you can run the flow step by step using the **Run next action** button.

    ![The run button next action in the flow designer.](..\media\run-next-action-icon.png)

1. If the flow runs as expected, select **Save** and close the flow designer.

    ![The save button in the flow designer.](..\media\save-icon.png)

1. Now, you can run your flow manually through the **Run** button in the console. If you want to cancel the execution of the flow, you can press the **Stop** button.

    ![The run button in the console.](..\media\run-date-conversion-flow.png)