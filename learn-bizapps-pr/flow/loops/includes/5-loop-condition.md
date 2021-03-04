The Loop Condition action is used when a block of actions should be repeated until a certain condition is met - this allows Processes to repeat actions without prior knowledge of the number of repetitions required.

To demonstrate this functionality, we'll automate a process, which adds the employees’ expenses, and stops when the budget has been exceeded.

First, we'll initialize the running budget at 0, set the starting Excel line to 2, and open the file:

![Screenshot of workspace with Set Variable Excel Index = 2 and Set Variable Running Budget = 0.](..\media\workspace-example-2.png)

Next, we'll add the loop condition, configuring it so that it will end when the budget exceeds 10000:

![Screenshot of Properties of 'Loop Condition' action dialog.](..\media\loop-condition-action-properties-continued.png)

Within the loop, the process will read the amount, add it to the running budget, and increase the index in order to move on to the next row:

![Screenshot of loop condition workspace.](..\media\loop-condition-workspace-example.png)

## Exit loop

As developed, this loop will only end when the budget exceeds 10000. However, if the sum of all expenses doesn't exceed the limit, then the loop will never end.
This is a good opportunity to examine the use of the **Exit loop** action. After reading a cell’s contents, we should check if there's any data in it - if not, then the loop should end, since all data was read - therefore, we'll add an **If** action:

![Screenshot of Properties of 'If' action dialog.](..\media\if-action-properties.png)

If all data has been read and the limit hasn't been exceeded, then we'll assign the value **False** to the %Exceeded% variable and exit the loop, since there's no more data to read. We'll also initialize the %Exceeded% variable to **True** in the beginning, since, in all other scenarios, the limit will be exceeded:

![Screenshot of loop condition if workspace example.](..\media\loop-condition-if-workspace-example.png)

Finally, we'll add an **If** action to check the %Exceeded% variable, and print a message accordingly:

![Screenshot of loop condition if workspace example 2.](..\media\loop-condition-if-workspace-example-2.png)
