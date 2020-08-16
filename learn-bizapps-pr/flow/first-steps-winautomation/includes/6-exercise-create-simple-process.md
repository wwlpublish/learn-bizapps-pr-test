Let's create a process that iterates ten times, and every time displays a message with the number of the current iteration. 

1.	Launch WinAutomation.

2.	Select **New Process**.

![The New Process button in the console.](..\media\image-37.png)

3.	Populate the **Name** field with the value **Iteration Example** and Select **process designer**.

![The New Process pop-up window.](..\media\image-38.png)

4.	Add a **Loop** action in the **Workspace** and set it to iterate ten times. 

![The Loop action's properties.](..\media\image-39.png)

5.	Between the **Loop** and the **End Loop** actions, add a **Display Message** action to display the **LoopIndex** variable. 

![The Display Message action's properties.](..\media\image-40.png)

6.	Select **Run** and verify that ten messages boxes with the respective iteration number appear.

![The Run button in the process designer.](..\media\image-41.png)

7.	Run the process step by step through the respective button and notice how the value of the **LoopIndex** variable changes in each step. 

![The Execute Next Action button in the process designer.](..\media\image-42.png)

8.	Select **Save** and close the process designer.

![The Save button in the process designer.](..\media\image-43.png)

9.	Now, you can run your process manually through the **Run** button in the toolbar.

![The Run button in the console.](..\media\image-44.png)

10.	Wait for the Notification popup window to show that the process ran successfully. 

![The Notification Popup Window.](..\media\image-45.png)

11.	In case you want to run the process automatically, you can add a schedule or a trigger as we showed in the previous units. 

