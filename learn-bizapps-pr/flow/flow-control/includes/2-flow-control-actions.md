By default, a process moves from one Action to the next in the order that these Actions appear in the Workspace. 

Certain Actions, such as the **Go To** Action or the **Exit Function** Action, to name a few, interrupt the default process flow, and direct it to another point in the same function, or another function respectively. 

Labels are used to create points of reference for the Go To Action to direct the flow to. 

The **Run Function** Action interrupts the function it is placed in and runs another function. When the second function completes, the flow reverts to the original function to continue running. These functions are often used in conjunction with Conditionals.

## Flow Control Actions

The **Label** Action creates a label at a specific location in the process. The required input is a name for the label.

![label action properties](..\media\label-action-properties.png)

The **Go To** Action directs the flow to the specified label. It requires the name of the label, which can be selected from the drop-down list of available labels. 

![go to action properties](..\media\go-to-action-properties.png)

**Run Function** runs another function at the point it is placed. The function must be specified by name and can be selected from the drop-down list of existing functions. 

When the function run by this action completes, the flow will be redirected to the Action that follows the Run Function Action in the process. 

![run function action properties](..\media\run-function-action-properties.png)

**Exit Function** does not have any properties. It directs the process flow back to the function that contained the Run Function Action. 

The **Stop Process** Action stops running the process. The process can be set to end successfully, or with an error message. An exit code can be specified as well. 

![stop process action properties](..\media\stop-process-action-properties.png)

**Begin Exception Block** and **End Exception Block** are placed around Actions that are likely to fail or produce an erroneous result. Placing the Actions in a block prevents the entire block of attempting to complete, should at least one of the Actions within it fail. 

Configure the properties to do any combination of the below:

* Set variable—Specify a variable, and a value to set to it. Use the variable elsewhere in the process to determine if the actions within the exception block have failed.

* Run function—Specify a function to run if the exception block produces an error.

* Continue execution contains four options: 

	* Continue with next action—Continue running the flow from the action that immediately follows the exception block

	* Repeat failed action—Retries the action that produced an error

	* Go to beginning of block—Directs the flow to retry the actions inside the exception block from the start
	
	* Go to end of block—Directs the flow to the end of the block

![begin exception block action properties](..\media\begin-exception-block-action-properties.png)
