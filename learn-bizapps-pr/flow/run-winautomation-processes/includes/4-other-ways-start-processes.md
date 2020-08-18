In addition to starting processes manually or automatically, you can start a process through the command line, from a different process, or from Power Automate. 

## Command line

WinAutomation can perform certain basic functions, including running a process, through a Command Line Interface (CLI).

To give a command to WinAutomation through a CLI, locate the **WinAutomationController.exe** file in the WinAutomation installation folder (by default, the path to the file is **C:\Program Files\WinAutomation\WinAutomationController.exe**). After typing the filepath into the CLI, you may start a process using the /start switch. The /start switch requires the following format:

**WinAutomationControllerPath /start processPath processCLA1 processCLA2**

**processPath** is the process’ path in the WinAutomation console, starting from the **My Processes** folder in the Folders Pane. 'processCLA1', 'processCLA2' etc. are any Command Line Arguments you may wish to use. Command line arguments can be retrieved by the flow using the **Get Command Line Arguments** Action.

An example run of the **Launch Calculator** example process would be:

**C:\Program Files\WinAutomation\WinAutomationController.exe /start /Examples/01 - Beginner/01 - Run Calculator**

## Start a process actions

A process can be started by another, separate flow, through the use of the Start Process action.

![start process action properties](..\media\start-process-action-properties.png)

Select any flow from the drop-down list, and when this action runs, the selected flow will begin running.

## Power Automate

WinAutomation processes may also be invoked through a UI flow in Power Automate. Add an action in a UI flow, and select the Run WInAutomation option.
 
![run winautomation ui flows action](..\media\run-winautomation-ui-flows-action.png)

At this point, you'll have to enter the flow’s path within WinAutomation, as well as any arguments required for it. 

![run winautomation ui flows properties](..\media\run-winautomation-ui-flows-properties.png)

 