# Conditionals and Loops
As mentioned before, Actions within a Process are executed sequentially. However, there are certain Actions which may alter this sequence, to achieve greater flexibility and adaptability in the execution of a Process.

In this unit, we will examine two main categories of such Actions: Conditionals and Loops.

## Conditionals
Conditional Actions allow Processes to modify their behavior during runtime, based on the data available at the time. Essentially, they allow Processes to make choices based on the information at their disposal.

In the previous example, we can add a Conditional Action to modify the Process’ behavior based on the contents of the first cell. In this example, we will assume the first column is empty, with the possible exception of a header in cell A1.

We will add an **If** Action to the workspace, configuring it as below:
 
![if action properties](..\media\if-action-properties.png)

The value we want to make sure is empty is the variable that contains the data we read from the worksheet in the previous Action.

![NOTE]
Pressing the gear icon next to the input field will produce a list of available variables to add to the field; this makes variables easier to handle.
Press OK to add the Action to the workspace. An End If Action is also automatically added, to signify the end of the conditional block of Actions; any Actions added between the If and End If Actions will only be executed if the condition in the If Action is met.
We will add a Write to Excel Worksheet Action to test this. If there is no header, we would like to add one:

![write to excel worksheet action properties](..\media\write-to-excel-worksheet-action-properties.png)

![actions workspace](..\media\actions-workspace.png)
 
## Loops
Loops enable Processes to repeat a block of Actions multiple times. The number of repetitions is determined by the type of loop Action used and its configuration.

Let’s expand the current example by adding Row IDs up to row 10; to achieve this, we will use the Loop Action.

The Loop Action initializes an index variable, and repeats until said variable reaches a specified value. The index variable is incremented by a certain value with each repetition:

![loop action properties](..\media\loop-action-properties.png)

Configured as above, the variable **%LoopIndex%** will be initialized to 2, and will be incremented by 1 each time the loop repeats, until it reaches the value 10.

When we add the Loop Action, an End Loop Action is also automatically added to the workspace; this is analogous to the End If Action in the previous unit.

Between the Loop and End Loop Actions, we will add a Write to Excel Worksheet Action, which will write the ID in each row:
 
![write to excel worksheet action properties continued](..\media\write-to-excel-worksheet-action-properties-continued.png)

![actions workspace continued](..\media\actions-workspace-continued.png)

In this case, the loop index is used both to determine the row in which the Process will write, and the contents to be written. When this loop is executed, all rows from 2 to 10 will contain the numbers 1-9 in column A.
