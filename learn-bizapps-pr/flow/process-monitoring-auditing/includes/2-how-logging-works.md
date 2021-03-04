WinAutomation provides two different types of logging:

- Automatic
- Custom

Automatic logging is preconfigured and will record all processes that are implemented through the **WinAutomation Console** or because of a trigger or schedule. The processes that are run through the **Process Designer** aren't recorded in the database because it's considered a debugging feature.

If the WinAutomation platform encounters an error or bug, it's logged into the log database as an internal exception.

![Screenshot of WinAutomation Logs created with automatic logging.](..\media\automatic-logging.png)

Except for automatic logging, WinAutomation supports the creation of custom entries through the **Log Message** action. These events are recorded when the process runs through the **WinAutomation Console** or the **Process Designer**.

![Screenshot of an example process with a Log Message action.](..\media\log-message-action.png)

All logs are stored in a central log file. The default location of the file is **C:\ProgramData\Softomotive\WinAutomation\Logs.dat**.
