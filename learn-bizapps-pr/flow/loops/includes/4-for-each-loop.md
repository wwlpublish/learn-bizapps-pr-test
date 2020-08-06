The **For Each** Action is used to iterate through a list or table of items; it's therefore common in tasks containing such structures.

To demonstrate this, we'll expand on the previous Process. Let’s assume that each employee may send multiple email messages, the expenses in which will have to be summed up before being written.

First, we add a new variable, which will contain the sum of each employee’s expenses:
 


![workspace loop example continued 2](..\media\workspace-loop-example-continued-2.png)

Since all the email messages of a specific employee have been retrieved at this point, we may add a **For Each** Action to iterate through them:
 


![for each loop action properties continued](..\media\for-each-loop-action-properties-continued.png)

Configured this way, %CurrentItem% will contain a different email message in each repetition of the **For Each** loop.

Within the loop, we will add Actions to convert the email text into a number, and add it to the employee’s total:
 


![for each loop example workspace continued](..\media\for-each-loop-example-workspace-continued.png)

Finally, note that we must change the value to be written into Excel to the Expense Sum variable (Action 11).
