Errors that occur while a process is running cause it to stop. Depending on their significance, such errors may adversely impact business continuity.

In this unit, you'll learn how to use the error handling capabilities of WinAutomation.

## Individual processes error handling (Level 3)

When an exception persists after exception handling at the action and block level, the process encounters an error, and is interrupted. At that point, you can create error handling for each individual process.

To set up error handling, find the process in the console, open its properties, and then navigate to the **Error Handling** tab.

![The Error Handling tab in the Process Properties.](..\media\error-handling-process-properties.png)

By default, processes use the default error handling options. To customize the error handling rules for an individual process, select **Override Default Options**.

![The Error Handling tab in the Process Properties with the Override Default Options radiobutton selected.](..\media\override-default-options-error-handling.png)

Error handling for a process is activated when a process fails, and are run in order. In the example above, if the process fails, an email will be sent to the specified account, an error log will be kept in the local C drive, and a screenshot will be added to the relevant log entry.

## Global process error handling (Level 4)

When a process doesn't use custom error handling rules, Global Error Handling rules are invoked. These rules are configured in the console Options tab, in the Error Handling section.

![The Behaviour tab in the WinAutomation Options.](..\media\behaviour-error-handling-options.png)

When any process fails, Global Error Handling rules are invoked, unless the process has individual error handling configured.

Note that an **Email/SMTP** subtab is also available - this contains all the information required to send an email message.
