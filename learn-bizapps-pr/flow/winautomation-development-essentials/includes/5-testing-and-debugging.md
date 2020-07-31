# Testing and Debugging
During Process development, it is important to test the behavior of the Process and ensure that everything is working as expected – and if not, to locate and diagnose the underlying issues.

## Testing
Processes under development can be executed at any time in the Process Designer, through the **Start** button; during this execution, the current Action is highlighted, giving users a clear view of the execution progress.

It is possible to pause, resume, and stop the execution; it is also possible to execute one Action at a time, to closely examine the behavior of the Process in certain sections. This is all achieved using the respective buttons:

![toolbar](..\media\toolbar.png)
 
Breakpoints can be added to automatically pause the execution when a specific Action is reached; this is done by clicking to the left of the Action in question:

![main function breakpoint](..\media\main-function-breakpoint.png)
 
By right-clicking on any Action, users may start executing the Process directly from that point onward; this enables them to test specific parts of a Process without having to execute it in its entirety.

On the bottom-right corner of the Designer, the Variables pane contains all the variables used in the Process, their type, and their current value. This information changes in real time during execution, providing users a clear picture of the Process’ state at any given time. Values can even be changed manually during execution, enabling very detailed and efficient testing.

## Debugging
In addition to the above, certain features are designed specifically for locating and correcting errors.
Any design-time errors – errors that are identifiable before the Process is executed – are communicated through red **X** symbols in the Designer, while details can also be found in the Errors pane at the bottom of the Designer:

![errors pane](..\media\errors-pane.png)
 
In this example, two required fields were left blank, so the relevant Action is highlighted as erroneous, and the Errors Pane contains further details.

Runtime errors – errors that occur during Process execution only – are communicated in a similar fashion:

![errors pane continued](..\media\errors-pane-continued.png)

An incorrect value was passed as an Excel column; while trying to read from that column, the Process failed. The Action in question is highlighted, and the Errors Pane contains more detailed information on the error.
 