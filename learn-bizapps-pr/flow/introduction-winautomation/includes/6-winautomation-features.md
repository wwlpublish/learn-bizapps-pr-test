WinAutomation contains a number of features designed to increase productivity while the User develops processes. 

## 1. process designer

process Designer is user-friendly with a drag&drop interface. It's equipped with features for advanced process development and troubleshooting.

Drag and drop Actions in process designer to simplify automation steps. 

Select the actions needed for the process, drag and drop them in the workspace in a sequential and logical manner. No actual scripting is needed. 
Test your automation and debug or troubleshoot it by pausing whenever needed.

Run the process step by step, review or even change variables while the process is running or go to different reusable functions. 

 ![processes designer](..\media\process-designer-2.png)

## 2. The Central Controls and Images Repository

Users may store all the elements with which the automation will interact in a central reusable repository.

WinAutomation can interact with any application on a workstation. This interaction takes place through Controls which are elements of any desktop or web application. 

Processes will access Controls through dedicated actions. 

A control can be a button, a link, a text that needs filling in and so on, which are associated with the relevant WinAutomation step. 

Controls that are chosen to interact with different applications that the automation is accessing while running, can be saved. 

This is based on the automation flow.  

In this respect, the Controls and Images Repository are where the applications used in processes are kept and reused. 

The different Controls may be stored into a central repository. 

Users may access the application controls that were saved while it is running.

Controls are UI or Web elements that can be captured and fully managed by the User. To access an application element, users may try one or more selectors. These are unlimited.

Controls may be renamed, edited, changed, updated, or deleted. 

All the UI or CSS selectors behind each control are editable, supporting variables for custom control access in case complicated scripts with multiple repetitions are required. 

The same will apply if a process tries to find any image on the machine’s screen.

Desktop or web applications are regularly updated to provide new features and a fancier interface. Consequently, their UI may change. 

Apart from keeping the process neat and easy to modify, the advantage of the Central Repository for Controls and Images is that, regardless of any application interface change, the User won't need to change a single Action of a process. Only the Central Controls will require updating. 

The automation will be up and running again in a short time.


## 3. Creating Custom Dialogs using the UI Designer.

When a User is present at a workstation, more often than not, there's a need to interact with the automation. This takes place through dialog boxes, where the automation asks the User various questions. These questions may have to do with critical human decision making or data input such as files/dates indication, yes/no answers and so on.
 
Apart from simple dialog boxes or message display, WinAutomation is equipped with a built-in UI Designer, which can add some flavor to dialog windows. 

Whenever processes require some input, the User will no longer be greeted by the usual dialog box. This feature allows the User to customize dialog boxes. This is only limited by the users CSS expertise. 

The User may design customized rich forms with any form element that is required, such as text fields, check-boxes, radio buttons, dropdown lists or buttons and so on.

Dialogs may be stylized and beautified by selecting any form element, creating professional and stylish dialog boxes for Attended automations (automations requiring a User to provide some type of input).

Select the form controls needed, and by using CSS, customize these to make the required Dialog Window.

 ![custom dialog designer](..\media\custom-dialog-designer.png)

## 4. Exception Handling

WinAutomation offers different levels of Exception Handling to cater for the most expected and unexpected cases.

Error prevention and circumvention logic is built into WinAutomation, with routines and scenarios to cover for and trace back errors. 

More specifically the User can set exception mechanisms for four different types of Exception Handling:

* The first is Action Exception Handling which concerns each and every individual Action or step within the process. If a single step of the process will make the automation fail, all the tools are available to determine how it should be handled. 

* The second is the Block of Actions Exception Handling which concerns a group of steps, including 1 to infinite steps. This is the try-catch method, which allows users to set the behavior that will be followed, in case ANY of the steps within the block fail. 

* The third is the process exception handling which concerns each and every individual process that has been developed. If any step within the process may fail, Users can determine how a process should be handled.

* The fourth and final method is the Global Exception Handling which concerns ALL processes in the WinAutomation Platform. If any process may fail, Users can determine how a process should behave.

## 5. Parallel execution, Concurrency, and process Queuing

Multitasking and Smart Concurrency policy is a feature that allows the application to govern and limit parallel process Execution.

processes can be configured and run simultaneously. WinAutomation concurrency policy will ensure optimum performance in terms of time and efficiency.

WinAutomation allows for as many processes to be run as the hardware can support. 

Different processes may run at the same time or on more than one instance of the same process. 

With parallel execution, Users make best use of their license. 

One workstation can operate in Unattended mode running multiple processes at the same time, without the need to engage more machines. 

WinAutomation technology holds back process automations in order to avoid clutter.

In the Concurrency policy for each process, if the limit of the process instances that can run at the same time has been reached, the behavior to be followed can be set - to either drop the processes if they are in wait mode, or queue the processes and make them wait for a specific period of time in the queue to be run, before rejecting them.

## 6. Advanced Synchronization

WinAutomation supports parallel execution of numerous processes, or even parallel execution of many instances of the same process. 

The configured Concurrency Policy of each process partly solves the challenge of having the same process accessing the same resources as Windows, mouse and keyboard, or controls.

With Synchronization actions, each process reserves a resource for as long as it needs to use it, marking it as busy and blocks all other processes from accessing it. 

If other processes attempt to use the same resource, it will have to wait until the resource is free and no other automation has currently locked its use.

## 7.	Control WinAutomation from the command line

Control WinAutomation from the command line without using the console.

Key WinAutomation activities may be performed from a simple command in the cmd, like starting or killing a process, enabling or disabling a process or listing all the processes that are currently running etc. 

Run simple commands, fire or stop running processes at will or even remotely through the Command line.