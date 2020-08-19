WinAutomation contains a number of features designed to increase productivity while the user develops processes. 

## Process designer

Process designer includes a drag and drop interface, and is equipped with features for advanced process development and troubleshooting.

In process designer, select the actions needed for the process, and then drag and drop them in the workspace in sequential or logical order. No scripting is needed.

Test your automation and debug or troubleshoot it by pausing whenever needed.

You can run a process step by step, review or even change variables while the process is running or go to different reusable functions. 

 ![processes designer](..\media\process-designer-2.png)

## Central controls and the images repository

Users can store all of the elements with which the automation will interact in a central reusable repository. Central repositories help make processes easy to modify, because users don't need to change actions to update processes to use updated controls or images. 

### Controls and the central repository

WinAutomation can interact with any application on a workstation. This interaction takes place through *controls* which are elements of any desktop or web application. Controls can be stored in the central repository. 

Processes access controls through dedicated actions. A control can be a button, a link, or text to be entered, for example. Controls are associated with the relevant WinAutomation steps. Controls that interact with different applications that the automation is accessing can be saved. Users can access the application controls that were saved while a process is running.

Controls are UI or Web elements that can be captured and fully managed by the user. To access an application element, users may try one or more selectors.

Controls may be renamed, edited, changed, updated, or deleted. 

All of the UI or CSS selectors behind each control are editable, supporting variables for custom control access for use in scripts in which multiple repetitions are required. 

### Images repository

Desktop or web applications are regularly updated to provide new features and a fancier interface. Consequently, their UI may change. The images repository makes it easy to keep images up to date without having to modify individual processes.

## UI designer

When a user is present at a workstation, more often than not, there's a need to interact with the automation. User interactions take place through dialog boxes that ask users questions. These questions may have to do with critical human decision making or data input such as files, dates, yes/no answers, and so on.
 
Apart from simple dialog boxes or message display, WinAutomation is equipped with a built-in UI designer.

The US designer allows the process creator to customize dialog boxes. This is only limited by the user's CSS expertise. 

The user can form elements such as text fields, checkboxes, radio buttons, dropdown lists or buttons.

 ![custom dialog designer](..\media\custom-dialog-designer.png)

## Exception handling

WinAutomation offers different levels of exception handling. Error prevention and circumvention logic is built into WinAutomation, with routines and scenarios to cover for and trace back errors. 

Types of available exception handling include: 

* Action exception handling enables you to determine how to handle exceptions for any individual action or step in a process. 

* Block of actions exception handling enables you to set exception handling for a group of steps. This type of exception handling uses the try-catch method, which allows users to set the behavior that will be followed if any of the steps within the block fail. 

* Process exception handling can be set for any individual process. If any step within the process fails, users can determine how the error should be handled.

* Global exception handling affects all processes. If any process fails, you can determine the global error handling action. 

## Parallel execution, concurrency, and process queuing

Multitasking and concurrency policies allow WinAutomation to govern and limit parallel process execution.

Processes can be configured to run simultaneously. The WinAutomation concurrency policy will ensure optimum performance in terms of time and efficiency. WinAutomation allows for as many processes to be run as the hardware can support. Different processes may run at the same time or on more than one instance of the same process. With parallel execution, users can make efficient use of their license. 

One workstation can operate in unattended mode running multiple processes at the same time, without the need to engage more machines. WinAutomation technology holds back process automations in order to avoid clutter.

In the concurrency policy for each process, if the limit of the process instances that can run at the same time has been reached, the behavior to be followed can be set to either drop processes in wait mode, or queue processes for a specific period of time, before rejecting them.

## Advanced synchronization

WinAutomation supports parallel execution of numerous processes, or even parallel execution of many instances of the same process. 

The concurrency policy of each process partly solves the challenge of having the same process accessing the same resources as Windows, input devices, or controls.

With synchronization actions, each process reserves a resource for as long as it needs to use it, marking it as busy and blocks all other processes from accessing it. 

If other processes attempt to use the same resource, it will have to wait until the resource is free and no other automation has currently locked its use.

## Command line options

You can control WinAutomation from the command line, like starting or stopping a process, enabling or disabling a process or listing all the processes that are currently running. 
