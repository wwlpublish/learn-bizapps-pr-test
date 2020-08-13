The first step in Process development is to create a new Process. The creation of a Process takes place in the **Processes** tab of the WinAutomation Console. On the top-left, press the **New Process** button to create a new Process:
 
![new process](..\media\new-process.png)

A window prompts the user to select the development method; for the scope of this module, we will use the **Process Designer** option:

![select process designer](..\media\select-process-designer.png)

This will open the Process Designer window:

![process designer default](..\media\process-designer-default.png)

The Process Designer is where all Processes are built, edited, and tested.

## Actions
The Actions Pane is located by default on the left-hand side of the Process Designer; this is where all the available Actions can be found, sorted into groups. Actions are the basic building blocks of a Process; Processes are essentially series of Actions, which are run sequentially.

To add an Action to the Process, drag & drop it to the main Workspace Pane, or double-click on it:

![display message action properties](..\media\display-message-action-properties.png)
 
When added, the Action’s Properties window automatically appears, allowing the user to configure the Action’s details. This window can be accessed at any time, by double-clicking the Action in the Workspace Pane.

## Variables
Variables are data containers that WinAutomation uses to store data for later use. In the previous screenshot, **%ButtonPressed%** is a variable created by the Display Message Action. Variables are contained between percentage marks, which allows them to stand out from simple text.

Variables can be produced as output from Actions, or used as input for other Actions. Opening an Excel worksheet, for example, produces a variable containing the Excel instance. This variable may then be used as input in any following Actions that require interaction with that particular Excel instance:
 
![launch excel action properties](..\media\launch-excel-action-properties.png)

![read from excel worksheet action properties](..\media\read-from-excel-worksheet-action-properties.png)
