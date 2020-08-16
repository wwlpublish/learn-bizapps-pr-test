In this unit, we will develop a simple process that creates a folder called Records if it does not already exist. 

To create a process:

1.	Launch WinAutomation.

2.	Select the **New Process** button.

![The New Process button in the console.](..\media\image-17.png)

3.	Choose a name for your process and select **process designer**.

![The New Process pop-up window.](..\media\image-18.png)

4.	Add a **Get Special Folder** action in the Workspace to get the path for your Desktop folder. 

![The Get Special Folder action's properties.](..\media\image-19.png)

5.	Add an **If Folder Exists** action to check whether the **Records** folder exists. 

![The If Folder Exists action's properties.](..\media\image-20.png)

6.	Between the **If Folder Exists** and the **End If** actions, add a **Create Folder** action to create a folder named **Records** inside the Desktop Folder.

![The Create Folder action's properties.](..\media\image-21.png)

7.	Select the **Run** button to verify that your process runs as expected. A folder named **Records** must be created in your Desktop. 

![The Run button in the process designer.](..\media\image-22.png)

8.	In case you want to check how every single action is run, you can run the process step by step by using the Execute Next Action button. 

![The Execute Next Action button in the process designer.](..\media\image-23.png)

9.	Select **Save** and close the process designer.

![The save button in the process designer.](..\media\image-24.png)

10.	Now, you can run your process manually through the **Run** button in the console toolbar.

![The Run button in the console.](..\media\image-25.png)

11.	While the process is running, a Notification popup window will be displayed to inform you about the running process.  

![The Notification Popup Window.](..\media\image-26.png)

12.	If you want to cancel the execution of the process, you can press the **Stop** button. 

![The Stop button in the console.](..\media\image-27.png)

13.	In case you want to run the process at specific days automatically, navigate to the **Scheduler** tab.

![The Scheduler tab in the console.](..\media\image-28.png)

14.	Select **New** and select **Schedule**.

![The New option in the Scheduler tab.](..\media\image-29.png)

15.	Now, configure the fields according to your needs. For example, to run the process automatically every Monday and Friday, set the fields like the image below.

![The Schedule Properties window.](..\media\image-30.png)

16.	In case you want to use a trigger instead of a schedule to run the process automatically, navigate to the **Triggers** tab.

![The Triggers tab in the console.](..\media\image-31.png)

17.	Select **New** and select the type of trigger you want to deploy. 

![The New option in the Triggers tab](..\media\image-32.png)

18.	In this example, we created a **HotKey Trigger** that runs the process every time the **CTRL + F10** key combination is pressed.

![The HotKey Trigger Properties window.](..\media\image-33.png)