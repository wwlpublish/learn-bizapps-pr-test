WinAutomation provides two different kinds of logging:
- Automatic logging
- Custom logging

Automatic logging is preconfigured and records all the processes executed through the **Console** or because of a trigger or schedule. The processes executed through the **Process Designer** aren't recorded in the database, since it's considered a debugging feature. 

If the WinAutomation platform itself faces an error or bug, it's logged into the log database as an internal exception.

![Logs created with automatic logging.](..\media\automatic-logging.png)

Except for automatic logging, WinAutomation supports the creation of custom entries through the **Log Message** action. These events are recorded when the process runs through the **Console** or the **Process Designer**.

![An example process with a Log Message action.](..\media\log-message-action.png)

All logs are stored in a central log file. The default location of the file is: 
**C:\ProgramData\Softomotive\WinAutomation\Logs.dat**