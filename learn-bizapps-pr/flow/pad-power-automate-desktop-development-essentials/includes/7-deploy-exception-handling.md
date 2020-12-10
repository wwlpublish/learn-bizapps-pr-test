Runtime errors may occur as a result of unforeseen circumstances while a flow is running, resulting in it stopping due to an error. To avoid errors, users may configure exception handling rules, so that the flow may recover and continue running.

In the flow designer, exception handling may be applied toindividual actions.

## Exception handling
Exceptions may occur from virtually any action. For this reason, most actions’ properties contain an **On error** button.

In our example flow, for instance, the Excel file to be processed may not exist in the path specified because it may not have been moved from its initial path to the working one we have entered in the flow. If we know the initial path, we could configure the **Launch Excel** action so that, if it fails to open the file, it will attempt to open it from its initial path.

To achieve this, we will double-click on the action to edit it:

![launch excel action properties 2](..\media\launch-excel-action-properties-2.png)

And press the **On error** button:

![launch excel action properties exception handling](..\media\launch-excel-action-properties-exception-handling.png)

The selected options will take effect when this action encounters an exception. To open a file in a different path, we will have to create a new subflow that does exactly that:

![alternative path subflow](..\media\alternative-path-subflow.png)
 
Then configure the previous action’s exception handling accordingly, by pressing **New Rule** and selecting **Run subflow**:

![launch excel action properties exception handling continued](..\media\launch-excel-action-properties-exception-handling-continued.png)
 
Configured as above, if the Excel file cannot be opened in its usual path, the Alternative Path subflow will run, opening the file in its alternative path; then, the flow will resume running.