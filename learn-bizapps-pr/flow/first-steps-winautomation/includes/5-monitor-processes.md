When you run complicated processes, you may need to monitor them and ensure that every action in the process works as expected. 

Let's repeat the steps of the previous unit to develop a process that creates a folder called **Records** if it does not exist in the Desktop.

As you can understand from its name, the **If Folder Exists** action checks if a folder exists or not. If its condition is valid, the actions between the **If Folder Exists** and the **End If** actions is run. 

![The previously created Process.](..\media\image-34.png)

To understand how that condition works, add a **Log Message** action below the **Create Folder** action to log a message when the folder is created. 

![The Log Message action.](..\media\image-35.png)


Delete the **Records** folder from your Desktop, save the process and run it. 

Now, navigate to the **Logs** tab. If everything worked as expected, two log messages must have been created. The first one is an auto generated log message, while the second one was created through the **Log Message** action.

![The Logs tab in the Console.](..\media\image-36.png)


If you rerun the process without deleting the **Records** folder, you will notice that only one automated log message will be created.

[!NOTE]
Logs are also created automatically when an error occurred or/and when the **Automatic Logging** process property is enabled. These types of logs are not created when the process is run through the **Process Designer**. 



