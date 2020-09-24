The **Run Application** action* can run any application or open any document by running the associated application. The action requires the application path and command-line arguments, in addition to a working folder that can be set optionally. The window state of the application can be set to **Maximized**, **Normal**, **Minimized**, or **Hidden**, and the action can be configured to wait for the launched application to load or complete.

![run application action properties](..\media\run-application-action-properties.png)

The **Run DOS Command** action can run a DOS command or a console application in invisible mode. The action waits for the command or application to complete and will then retrieve its output into a text variable. The **DOS Command or Application** field is required input, whereas the **Working Folder** field is optional. The output, error output, and exit code are stored into separate variables.

![run dos command action properties](..\media\run-dos-command-action-properties.png)

The **Run Script** actions (VBScript/JavaScript/PowerShell/Python) require the script input to run. The output is retrieved and stored into a variable. Additionally, the error output can be stored in a separate variable. 

![run vb script action properties](..\media\run-vb-script-action-properties.png)

**Terminate Process** is an action that stops any currently running process. The process can be specified by name or ID; either choice requires the input of the corresponding identifier. 

![terminate process action properties](..\media\terminate-process-action-properties.png)

The **Print Document** action requires a file path to print the specified document. The **Set Default Printer** action requires you to choose a printer from a drop-down list of detected printers and then sets it as the default printer. The **Get Default Printer** action retrieves the name of the default printer and then stores it in a variable. 

![print document action properties](..\media\print-document-action-properties.png)

The **Log Off User** action signs off the currently signed-in user, with an option for you to select **Force Log Off** if any apps are preventing the operation. 

![log off user action properties](..\media\log-off-user-action-properties.png)

The **Shutdown Computer** action can be set to **Shutdown**, **Restart**, **Suspend**, or **Hibernate**. The **Force Selected Action** check box allows the selected operation to persist in case apps are preventing shutdown. 

![shutdown computer action properties](..\media\shutdown-computer-action-properties.png)

The **Show Desktop** action is used to minimize all currently opened windows or revert them to the state that they were in before the **Show Desktop** operation. 

![show desktop action properties](..\media\show-desktop-action-properties.png)

The **Lock Workstation** action contains no editable properties and will lock the workstation to prevent unauthorized access. 


The **Play Sound** action can be set to play a specified system sound or play a .wav file. If you select a .wav file, you will be required to enter the file path. 

![play sound action properties](..\media\play-sound-action-properties.png)

The **Empty Recycle Bin** action contains no editable properties and will permanently delete all contents of the recycle bin. 


**Take Screenshot** takes a screenshot of the specified screen, all screens, or the foreground window only. The image file can be saved to the clipboard or to a file. A path and image format must be specified for the latter case. 

![take screenshot action properties](..\media\take-screenshot-action-properties.png)

The **Control Screen Saver** action can enable, disable, start, or stop the screensaver. 

![control screen saver action properties](..\media\control-screen-saver-action-properties.png)

The **Ping** action will ping a remote computer, which is specified by name or IP, with a configurable timeout. The result and roundtrip time are stored in separate variables. 

![ping action properties](..\media\ping-action-properties.png)

The **Set Environment Variable** action requires the user to specify an environment variable and a value to set. The type—user or system must also be specified. The **Get Environment Variable** action will retrieve the value of the specified variable name and store it into a WinAutomation variable. The **Delete Environment Variable** action will delete the variable with the specified name and type. 

![set environment variable action properties](..\media\set-environment-variable-action-properties.png)


The **Get Screen Resolution** action retrieves the width, height, bit count, and frequency of the specified monitor into separate variables. 

![get screen resolution action properties](..\media\get-screen-resolution-action-properties.png)


The **Get Screen Resolution** action sets the specified width, height, bit count, and frequency of the specified monitor. The **Available Resolutions** button displays all possible combinations of these values. 

![set screen resolution action properties](..\media\set-screen-resolution-action-properties.png)
