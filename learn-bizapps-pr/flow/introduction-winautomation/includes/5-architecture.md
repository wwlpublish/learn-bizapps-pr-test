WinAutomation provides serverless desktop automation software for professionals and small teams. 

It can be installed on any client Workstation with Windows Vista  or later and on any server with Windows Server 2008 R2 or later. WinAutomation is compatible with both 32-bit and 64-bit workstations.

Processes can be transferred by importing and exporting between two or more WinAutomation installations. WinAutomation does not have the ability to communicate with other  WinAutomation installations, even on machines that are on the same domain or network. There is no relationship between separate WinAutomation consoles, nor is there any way to centrally manage multiple WinAutomation consoles from a single point. 

Upon WinAutomation installation, the following services are installed: 

-	WinAutomation server service. This service performs all steps necessary to assure that WinAutomation runs well.
-	WinAutomation machine agent service (WinAutomationMachineagent). This service is responsible for triggers and non-interactive processes. Triggers are used to invoke processes when a specific event occurs. Non-interactive processes are those that don't require any human interaction and can work in the background without being affected.


WinAutomation has the following components: 

* WinAutomation console, the main xomponent through which a WinAutomation installation can be managed
* WinAutomation process designer, where processes are developed and tested before running

WinAutomation uses a database to store processes, by default called “processes.dat”, under each user's Documents folder. This ensures that if multiple users log into the same workstation, each user is able to view and manage only their own processes. Note that only one user is permitted to use WinAutomation at a time as the license is per machine/per user. All WinAutomation .dat files are SQLlite databases. SQLlite is an embedded database, and doesn't require a server tool for communication.  

## WinAutomation processes 

In situations where the user is already logged on, simply starting the console, is enough to trigger the user agent. Each time the user agent connects, it sends a series of data of the user for identification to the server.

The user agent then retrieves the hotkey and the idle monitor triggers,  which the machine agent is not responsible. 

The user agent always runs the process.exe process so that it is on standby and is available after a process has been invoked. There is always one more instance of process.exe running than there are processes.  

Processes can also be invoked through the process designer. In this case, the process is invoked by the debugger.  

In cases where a user triggers a process from the console, the user agent triggers process.exe, which runs the process.
 
 ![processes diagram](..\media\processes-diagram.png)