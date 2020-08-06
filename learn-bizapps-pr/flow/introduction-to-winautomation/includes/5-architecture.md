WinAutomation is a Serverless Desktop Automation software for professionals and small teams. 

It can be installed on any Client Workstation with Windows Vista Operating system or later and on any server with Windows Server 2008 R2 or later. WinAutomation is compatible with both 32-bit and 64-bit workstations.

Processes can be transferred by importing and exporting between two or more WinAutomation installations. Other than that, there is  no ability to communicate with other distributed WinAutomation installations, even on machines that are on the same domain/network. Therefore, there is neither a relation between separate WinAutomation Consoles, nor is there any way to centrally manage multiple WinAutomation Consoles from a single point. 

Upon WinAutomation installation, the following two Services will be installed: 

1.	the WinAutomation Server, and 
1.	the WinAutomation Machine Agent Service. 

WinAutomation is split in two main parts to perform all the operations. These are: 

* the WinAutomation Console, the main Component through which the WinAutomation installation can be managed.
* the WinAutomation Process Designer, where processes are developed and tested before execution

WinAutomation uses the processes database to store all the processes developed, by default “Processes.dat” file that is stored under the users documents WinAutomation file. This reassures, that if multiple users log into the same workstation, then each User will be able to view and manage only their own processes. Keep in mind, that only one user is permitted to use WinAutomation at a time as the license is per machine/per user. All the WinAutomation .dat files, are SQLlite databases. SQLlite is an embedded database, which doesn't require a server tool for communication.  

Upon installation, two WinAutomation Services are created and are constantly running in the background:

* WinAutomation Server Service, which is responsible for the smooth operation of WinAutomation. It's the main service performing all the necessary steps assuring WinAutomation is in a healthy condition.

* WinAutomationMachineAgent is the second Service that starts and is responsible for multiple Triggers and the execution of any Non-interactive processes.

Triggers are used to invoke processes when a specific event occurs. Non-interactive processes are those that don't require any human interaction and can work in the background without being affected.

## WinAutomation Processes 

In situations where the User is already logged on, simply starting the Console, is enough to trigger the User Agent. Each time the User Agent connects, it sends a series of data of the User for identification to the Server.

 Next, the User Agent will retrieve the two triggers for which the Machine Agent is not responsible. These are the Hotkey and the Idle Monitor Triggers.

The User Agent would always execute a Process.exe process so that it would be on standby and would be available once a process has been invoked. There's always one Process.exe additional to the number of processes running. 

Apart from the WinAutomation User Agent, a process can also be invoked through the Process Designer. In this case, the process starts with the debugger.  

 In cases where a User triggers a process from the Console, the User Agent is the one triggering the Process.exe, which runs the process.
 
 ![processes diagram](..\media\processes-diagram.png)