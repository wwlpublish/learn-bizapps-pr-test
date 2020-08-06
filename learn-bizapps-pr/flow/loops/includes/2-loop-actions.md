Loops are used to repeat a block of Actions multiple times, in order to automate repetitive tasks. The number of repetitions depends on the type of loop that will be used, as well as the size of the dataset that needs to be processed.
There are three distinct types of loops in WinAutomation:
* Simple Loop
* For Each loop
* Loop Condition

Each of these loop types allows the repetition of a block of Actions - what sets them apart is the way they are configured, and the scenarios in which they are used.

## Simple Loops
The **Loop** Action allows the creation of simple loops. Simple loops use a Loop Index variable - it's assigned an initial value, an end value, and an increment value. When the loop begins, the Index is assigned its initial value, and every time a repetition ends, the increment value is added to the Index - if the Index has reached or surpassed its end value, the loop ends, otherwise it repeats.

When configured as below, the loop will repeat %ClientNumber% times:
 
![loop action properties](..\media\loop-action-properties.png)

The **Loop** Action is most commonly used when the number of repetitions required is known beforehand, or when an Index value is required within the Block of Actions that are repeated – for example, when iterating a list or table.
## Loop Condition
The **Loop Condition** Action is designed to repeat as long as a specified condition is true. When a repetition ends, the condition is evaluated; if it’s true, then the loop repeats, otherwise it ends.

When configured as below, the loop will keep repeating until the total budget is greater than 10000:

![loop condition action properties](..\media\loop-condition-action-properties.png)

The **Loop Condition** Action is mostly used when the number of required repetitions is not known, and depends on a certain condition being met.
## For Each loop
The **For Each** Action iterates through a list or table of items, and repeats once for each item. The loop will end when it has iterated through all the items of the list or table it received as input.

In the following example, the loop will repeat once for each file in the given list:
 


![for each loop action properties](..\media\for-each-loop-action-properties.png)

The **For Each** Action is most often preferred when a task must be repeated using data in the form of lists or tables.
## End Loop
The **End Loop** Action is automatically added when any of the above three loops are used, and marks the end of the block of Actions that should be repeated:
 


![for each loop example workspace](..\media\for-each-loop-example-workspace.png)

In the above example, Actions 2-4 will be repeated for each email message stored in the %RetrievedEmails% list.
## Exit Loop
The **Exit Loop** Action is used to immediately exit a loop, regardless of whether its end condition has been met. This Action permits Users to immediately end a loop in certain cases where this is required.

**Exit Loop** must be placed within a loop block, and is always used within a conditional:
 


![exit loop action workspace](..\media\exit-loop-action-workspace.png)

In the above scenario, the loop will end when the total budget is greater than 10000 – however, if the Process encounters a non-positive number, indicating that there is no more data to add, the loop will end immediately.
