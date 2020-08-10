Apart from manual execution and automatic execution through schedules and triggers, there are also a few more ways to run processes in WinAutomation.
## Through the command line
WinAutomation can perform certain basic functions, including executing a process, through a Command Line Interface (CLI), like the Windows CMD.

To give a command to WinAutomation through CLI, you will have to locate the **WinAutomationController.exe** file in the WinAutomation installation folder (by default, the path to the file is **C:\Program Files\WinAutomation\WinAutomationController.exe**). After typing the filepath into the CLI, you may start a process using the /start switch. The /start switch requires the following format:

**WinAutomationControllerPath /start processPath processCLA1 processCLA2**

**processPath** is the process’ path in the WinAutomation Console, starting from the **My Processes** folder in the Folders Pane. 'processCLA1', 'processCLA2' etc. are any Command Line Arguments you may wish to use. Command line arguments can be retrieved by the flow using the **Get Command Line Arguments** Action.

An example execution of the **Launch Calculator** example process would be:

**C:\Program Files\WinAutomation\WinAutomationController.exe /start /Examples/01 - Beginner/01 - Run Calculator**
## Through anther process
A process can be started by another, separate flow, through the use of the Start Process action:
 

![start process action properties](..\media\start-process-action-properties.png)

Select any flow from the drop-down list, and when this action is executed, the selected flow will begin its execution.
## Through Power Automate
WinAutomation process may also be invoked through a UI flow in Power Automate. Simple add an action in a UI flow, and select the Run WInAutomation option:
 

![run winautomation ui flows action](..\media\run-winautomation-ui-flows-action.png)

At this point, you'll have to enter the flow’s path within WinAutomation, as well as any arguments required:
 

![run winautomation ui flows properties](..\media\run-winautomation-ui-flows-properties.png)

 