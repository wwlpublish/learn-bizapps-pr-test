When you run complicated processes, you may need to monitor them and ensure that every action in the process works as expected.

For example, consider the previous exercise.

As you can understand from its name, the **If Folder Exists** action checks if a folder exists or not. If its condition is valid, the actions between the **If Folder Exists** and the **End If** actions are run.

![Screenshot of the previously created Process.](..\media\image-34.png)

To understand how that condition works, add a **Log Message** action below the **Create Folder** action to log a message when the folder is created.

![Screenshot of the Process Designer Log Message action.](..\media\image-35.png)

Delete the **Records** folder from your Desktop, save the process and run it.

Now, navigate to the **Logs** tab. If everything worked as expected, two log messages must have been created. The first one is an auto generated log message, while the second one was created by the Log Message action.

![Screenshot of the Logs tab in the console.](..\media\image-36.png)

If you rerun the process without deleting the **Records** folder, you will notice that only one automated log message will be created.

> [!NOTE]
> Logs are also created automatically when an error occurred or/and when the **Automatic Logging** process property is enabled. These types of logs are not created when the process is run through the **process designer**.
