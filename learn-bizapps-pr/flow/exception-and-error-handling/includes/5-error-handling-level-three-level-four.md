Errors that occur while a process is running will cause it to come to a halt. Depending on their significance, such errors may adversely impact business continuity. Levels 3 and 4 are designed to assist users in properly identifying and facing such events.

In this unit, you'll learn how to use the error handling capabilities of WinAutomation.

## Level 3 – Individual processes

When an exception persists after exception handling levels 1 and 2, the process encounters an error, and it's interrupted. However, each process may respond differently to an error, using the third level of error handling, which affects each process individually.

To access this capability, locate the process in question in the **WinAutomation Console**, and open its properties; from there, navigate to the **Error Handling** tab:

![The Error Handling tab in the Process Properties.](..\media\error-handling-process-properties.png)

By default, every process uses the default error handling options (Level 4) to customize the error handling rules for an individual process, choose the **Override Default Options** radio button. This will allow you to customize the available options:


![The Error Handling tab in the Process Properties with the Override Default Options radiobutton selected.](..\media\override-default-options-error-handling.png)

As in the previous levels, these rules are activated when this particular process fails, and are run in order: if the above process fails, a relevant email will be sent to the chosen account, an error log will be kept in the local C drive, and a screenshot will be added to the relevant Log entry.

## Level 4 – All processes

In case a process doesn't use custom error handling rules, it's subject to the **Global Error Handling** settings. These rules are configured in the **WinAutomation Console**, under the **Error Handling** subtab, which is located in the **Options** tab.

![The Behaviour tab in the WinAutomation Options.](..\media\behaviour-error-handling-options.png)

When any process fails, these rules will automatically come into effect, except if the process in question has individual error handling (Level 3) set up.

Note that an **Email/SMTP** subtab is also available - this contains all the information required to send an email message, in case the **Send Email** option is activated.