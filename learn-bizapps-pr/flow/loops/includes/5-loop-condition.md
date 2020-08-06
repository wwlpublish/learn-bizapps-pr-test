The **Loop Condition** Action is used when a block of Actions should be repeated until a certain condition is met - this allows Processes to repeat Actions without prior knowledge of the number of repetitions required.

To demonstrate this functionality, we'll automate a Process, which adds the employees’ expenses, and stops when the budget has been exceeded.

First, we'll initialize the running budget at 0, set the starting Excel line to 2, and open the file:
 

![workspace example 2](..\media\workspace-example-2.png)

Next, we'll add the Loop Condition, configuring it so that it will end when the budget exceeds 10000:
 

![loop condition action properties continued](..\media\loop-condition-action-properties-continued.png)

Within the loop, the Process will read the amount, add it to the running budget, and increase the index in order to move on to the next row:
 

![loop condition workspace example](..\media\loop-condition-workspace-example.png)

## Exit Loop
As developed, this loop will only end when the budget exceeds 10000. However, if the sum of all expenses doesn't exceed the limit, then the loop will never end.
This is a good opportunity to examine the use of the **Exit Loop** Action. After reading a cell’s contents, we should check if there's any data in it - if not, then the loop should end, since all data was read - therefore, we'll add an **If** Action:
 

![if action properties](..\media\if-action-properties.png)

If all data has been read and the limit hasn't been exceeded, then we'll assign the value **False** to the %Exceeded% variable and exit the loop, since there's no more data to read. We'll also initialize the %Exceeded% variable to **True** in the beginning, since, in all other scenarios, the limit will be exceeded:
 

![loop condition if workspace example](..\media\loop-condition-if-workspace-example.png)

Finally, we'll add an **If** Action to check the %Exceeded% variable, and print a message accordingly:
 

![loop condition if workspace example 2](..\media\loop-condition-if-workspace-example-2.png)


