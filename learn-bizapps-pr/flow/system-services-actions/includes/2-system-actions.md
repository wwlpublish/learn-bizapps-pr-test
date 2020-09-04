The **Run Application Action** can run any application or open any document by running the associated application. The Action requires the path of the application, and command-line arguments as well as a working folder can be set optionally. The window state of the application can be set to maximized, normal, minimized, or hidden, and the Action can be configured to wait for the launched application to load or complete.

![run application action properties](..\media\run-application-action-properties.png)

The **Run DOS Command Action** can run a DOS command or a console application in invisible mode. The Action waits for the command or application to complete and retrieves its output into a text variable. The DOS Command or Application is a required input. The Working Folder is optional. The output, error output, and exit code are all stored into separate variables.

![run dos command action properties](..\media\run-dos-command-action-properties.png)

The **Run Script** Actions (VBScript/JavaScript/PowerShell/Python) require the input of the script to run. The output is retrieved and stored into a variable. The error output can also be stored in a separate variable. 

![run vb script action properties](..\media\run-vb-script-action-properties.png)

**Terminate Process** is an Action that stops any currently running process. The process can be specified by name or ID. Either choice requires the input of the corresponding identifier. 

![terminate process action properties](..\media\terminate-process-action-properties.png)

The **Print Document** Action requires a file path to print the specified document. The **Set Default Printer** Action requires to choose a printer out of a drop-down list of detected printers and sets it as the default printer. The **Get Default Printer** Action retrieves the name of the default printer and stores it in a variable. 

![print document action properties](..\media\print-document-action-properties.png)

The **Log Off User** Action logs off the currently logged in user, with an option to force Log Off if any apps happen to be preventing the operation. 

![log off user action properties](..\media\log-off-user-action-properties.png)

The **Shutdown Computer** Action can be set to Shutdown, Restart, Suspend, or Hibernate. The Force Selected Action checkbox allows the selected operation to persist in case there are any apps preventing shutdown. 

![shutdown computer action properties](..\media\shutdown-computer-action-properties.png)

The **Show Desktop** Action is used to either minimize all the currently open windows, or revert them to the state they were in before the Show Desktop operation. 

![show desktop action properties](..\media\show-desktop-action-properties.png)

The **Lock Workstation** action contains no editable properties and locks the workstation to prevent unauthorized access. 


The **Play Sound** Action can be set to either play a specified system sound or play a .wav file. If a .wav file is chosen, the input of the file path is required. 

![play sound action properties](..\media\play-sound-action-properties.png)

The **Empty Recycle Bin** action contains no editable properties and permanently deletes all the contents of the recycle bin. 


**Take Screenshot** takes a screenshot of the specified screen, all screens, or the foreground window only. The image file can be saved to the clipboard or to a file. A path and image format must be specified for the latter case. 

![take screenshot action properties](..\media\take-screenshot-action-properties.png)

The **Control Screen Saver** Action can enable, disable, start, or stop the screensaver. 

![control screen saver action properties](..\media\control-screen-saver-action-properties.png)

The **Ping** Action pings a remote computer, specified by name or IP, with a configurable timeout. The result and roundtrip time are stored in separate variables. 

![ping action properties](..\media\ping-action-properties.png)

The **Set Environment Variable** Action requires the user to specify an environment variable and a value to set. The type—user or system must also be specified. The **Get Environment Variable** Action will retrieve the value of the specified variable name and store it into a WinAutomation variable. The **Delete Environment Variable** Action will delete the variable with the specified name and type. 

![set environment variable action properties](..\media\set-environment-variable-action-properties.png)


The **Get Screen Resolution Action** retrieves the Width, Height, Bit Count and Frequency of the specified monitor into separate variables. 

![get screen resolution action properties](..\media\get-screen-resolution-action-properties.png)


The **Get Screen Resolution Action** sets the specified Width, Height, Bit Count and Frequency of the specified monitor. The Available Resolutions button displays all possible combinations of these values. 

![set screen resolution action properties](..\media\set-screen-resolution-action-properties.png)
