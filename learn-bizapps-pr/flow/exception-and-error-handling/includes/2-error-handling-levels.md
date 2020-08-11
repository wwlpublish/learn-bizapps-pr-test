Exception and error handling is a mechanism, which allows WinAutomation to handle and recover from unexpected circumstances and issues that might occur while a process is running.

In the example we explored in the introduction of this module, consider the scenario where the client database cannot be accessed because of a network issue. Attempting to connect to the database would then cause an exception, and the process would then stop running, producing an error.

In this unit, you'll learn about exceptions and errors, and about the four levels of exception and error handling in WinAutomation.

## About exceptions

Exceptions are events which occur while a process is running; these events disrupt the expected flow of a process, and will cause it to fail if they are not handled properly. Exceptions occur when an action cannot run as intended, and may be caused by various factors: incorrect inputs, unexpected values, software/hardware failures, unavailable resources, etc.

## About errors

Errors are the result of unhandled exceptions. When an exception occurs while a process is running, the process will fail by default, since it can no longer continue running. Any exception that is left unhandled, or is handled in a way that does not allow the continuation of the process’ flow, causes an error in the process.

## Exception and error handling levels

Exception and error handling in WinAutomation is divided into four distinct levels:

- Level 1: Individual actions
- Level 2: Action blocks
- Level 3: Individual processes
- Level 4: All processes

All four levels are optional, and are activated in order: If an action fails, its individual exception handling properties will be activated (Level 1). If the exception is successfully handled, then the process will resume; if not, the Block level exception handling (Level 2) will take effect. If the exception is still not contained, the process will fail, triggering its own error handling (Level 3); if no individual error handling has been set up for that specific process, then the global error handling settings (Level 4) will be activated.
