Runtime errors may occur as a result of unforeseen circumstances while a flow is running, resulting in it stopping due to an error. To avoid errors, users may configure exception handling rules, so that the flow can recover and continue running.

In the flow designer, exception handling may be applied to individual actions.

## Exception handling

Exceptions may occur from virtually any action. For this reason, most actions’ properties contain an **On error** button.

In our example flow, for instance, the Excel file to be processed may not exist in the path specified because it may not have been moved from its initial path to the working one we have entered in the flow. If we know the initial path, we could configure the **Launch Excel** action so that, if it fails to open the file, it will attempt to open it from its initial path.

To achieve this, we will double-click on the action to edit it:

![Screenshot of the Launch Excel action properties dialog.](..\media\launch-excel-action-properties-2.png)

And press the **On error** button:

![Screenshot of the Launch Excel action properties exception handling.](..\media\launch-excel-action-properties-exception-handling.png)

The selected options will take effect when this action encounters an exception. To open a file in a different path, we will have to create a new subflow that does exactly that:

![Screenshot of the alternative path subflow.](..\media\alternative-path-subflow.png)

Then configure the previous action’s exception handling accordingly, by pressing **New rule** and selecting **Run subflow**:

![Screenshot of the Launch Excel action properties exception handling with alternative path added.](..\media\launch-excel-action-properties-exception-handling-continued.png)

Configured as above, if the Excel file cannot be opened in its usual path, the Alternative Path subflow will run, opening the file in its alternative path; then, the flow will resume running.
