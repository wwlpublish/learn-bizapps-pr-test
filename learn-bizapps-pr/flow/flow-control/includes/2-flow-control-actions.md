By default, a process moves from one action to the next in the order that these actions appear in the workspace. 

Certain actions, such as the **Go To** action or the **Exit Function** action, interrupt the default process flow and direct it to another point in the same function or another function. 

Labels are used to create points of reference for the **Go To** action to direct the flow to. 

The **Run Function** action interrupts the function that it is placed in and runs another function. When the second function completes, the flow reverts to the original function to continue running. These functions are often used in conjunction with conditionals.

## Flow control actions

The **Label** action creates a label at a specific location in the process. The required input is a name for the label.

![label action properties](..\media\label-action-properties.png)

The **Go To** action directs the flow to the specified label. It requires the name of the label, which can be selected from the drop-down list of available labels. 

![go to action properties](..\media\go-to-action-properties.png)

**Run Function** runs another function at the point that it is placed. The function must be specified by name and can be selected from the drop-down list of existing functions. 

When the function that is run by this action completes, the flow will be redirected to the action that follows the **Run Function** action in the process. 

![run function action properties](..\media\run-function-action-properties.png)

**Exit Function** does not have properties. It directs the process flow back to the function that contained the **Run Function** action. 

The **Stop Process** action stops running the process. The process can be set to end successfully or with an error message. An exit code can be specified as well. 

![stop process action properties](..\media\stop-process-action-properties.png)

The **Begin Exception Block** and **End Exception Block** actions are placed around actions that are likely to fail or produce an erroneous result. Placing the actions in a block prevents the entire block from attempting to complete in the event that at least one of the actions within it fails. 

Configure the properties to do any combination of the described actions in the following table.

|Property            |Option                   |Description     |
|--------------------|---------------------------|--------------|
|Set Variable        |                           |Specify a variable and a value to set to it. Use the variable elsewhere in the process to determine if the actions within the exception block have failed. |
|Run Function        |                           |Specify a function to run if the exception block produces an error.   |
|Continue Execution  |Continue with next action  |Continue running the flow from the action that immediately follows the exception block. |
|Continue Execution  |Repeat failed action       |Retry the action that produced an error. |
|Continue Execution  |Go to beginning of block   |Direct the flow to retry the actions inside the exception block from the start. |
|Continue Execution  |Go to end of block         |Direct the flow to the end of the block. |

![begin exception block action properties](..\media\begin-exception-block-action-properties.png)
