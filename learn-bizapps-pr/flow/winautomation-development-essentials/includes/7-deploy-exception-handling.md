Runtime errors may occur as a result of unforeseen circumstances during Process execution, resulting in it stopping due to an error. To avoid errors, users may configure Exception Handling rules, so that the Process may recover and continue running.

In the Process Designer, Exception Handling may be applied to both individual Actions, and blocks of Actions.

## Individual Actions
Exceptions may occur from virtually any Action. For this reason, most Actions’ Properties contain a dedicated **Exception Handling** tab.

In our example Process, for example, the Excel file to be processed may not exist in the path specified because it may not have been moved from its initial path to the working one we have entered in the Process. If we know the initial path, we could configure the Launch Excel Action so that, if it fails to open the file, it will attempt to open it from its initial path.

To achieve this, we will double-click on the Action to edit it:

![launch excel action properties 2](..\media\launch-excel-action-properties-2.png)

And open the Exception Handling tab:

![launch excel action properties exception handling](..\media\launch-excel-action-properties-exception-handling.png)

The selected options will take effect when this Action encounters an Exception. To open a file in a different path, we will have to create a new Function that does exactly that:

![alternative path function](..\media\alternative-path-function.png)
 
Then configure the previous Action’s Exception Handling accordingly:

![launch excel action properties exception handling continued](..\media\launch-excel-action-properties-exception-handling-continued.png)
 
Configured as above, if the Excel file cannot be opened in its usual path, the Alternative Path Function will run, opening the file in its alternative path; then, the Process will resume running.
## Blocks of Actions
In some cases, multiple Actions should exhibit the same behavior when encountered with an exception; the Exception Block is designed to deal with such occurrences.

In our scenario, we will assume that Excel may crash at any point during the Process. If that happens, we will have to close and restart it.

We will start by adding a **Begin Exception Block** action:

![begin exception block action properties](..\media\begin-exception-block-action-properties.png)
 
Configuring an Exception Block is similar to configuring an Action’s Exception Handling.
Again, we will create a Function to perform the necessary tasks:

![excel restart function](..\media\excel-restart-function.png)
 
Then, we will configure the Exception Block so that it run the function, thus saving the file and restarting Excel, and then resuming from the Action where the exception occurred:

![begin exception block action properties continued](..\media\begin-exception-block-action-properties-continued.png)
 
Finally, we will set up the Exception Block’s starting and ending points accordingly:

![main function exception block](..\media\main-function-exception-block.png)

> [!NOTE] 
> Individual Exception Handling takes precedence over Block level Exception Handling; this means that an Action’s individual Exception Handling rules will apply first, and the Exception Block will only apply if the issue is still not contained.
 