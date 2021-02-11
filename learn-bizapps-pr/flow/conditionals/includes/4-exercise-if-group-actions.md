In this exercise, you will apply some of the If actions available, in order to identify the capabilities they offer.

1. Use a **Get Special Folder** action to retrieve the path to the desktop.

2. Check whether a folder named **Records** exists in the desktop. To do this, use the **If Folder Exists** action, and configure its input as follows:

    ![Screenshot of Properties of 'If Folder Exists' action. If Folder is set to Exists, Folder Path is set to %SpecialFolder%\Records, and the OK button is highlighted.](..\media\if-records-folder-exists.png)

3. Inside the **If** block, add an **If File Exists** action to check if the **Expenses** Excel file exists inside the **Records** folder. Configure it as follows:

    ![Screenshot of Properties of 'If File Exists' action. If File is set to Exists, Folder Path is set to %SpecialFolder%\Records\Expenses.xlsx, and the OK button is highlighted.](..\media\if-expenses-file-exists.png)

4. This will only run if the Folder exists. By this stage, your process should look like this:

    ![Screenshot of the following If action.](..\media\initial-process-structure.png)

    ```console
    Get Special Folder
    Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

    If Folder Exists
    If Folder %SpecialFolder%\Records exists

      If File Exists
      If File %SpecialFolder%\Records\Expenses.xlsx exists

      End If

    End If
    ```

5. If the file exists, move it to the desktop folder using the **Move Files** action. Otherwise, the user should be notified; add an **Else** action inside the second if block, and a **Display Message** action to inform the user that the file has already been moved:

    ![Screenshot of the following If Else action.](..\media\else-display-message.png)

    ```console
    Get Special Folder
    Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

    If Folder Exists
    If Folder %SpecialFolder%\Records exists

      If File Exists
      If File %SpecialFolder%\Records\Expenses.xlsx exists

        Move File(s)
        Move the file(s) %SpecialFolder%\Records\Expenses.xlsx into %SpecialFolder%

      Else

        Display Message
        Display Message box with message File has already moved

      End If

    End If
    ```

6. Finally, in case the folder itself does not exist, add an **Else** action inside the first **If** block, and a second **Display Message** action to inform the user that the **Records** folder does not exist:

    ![Screenshot of the following Outside else action.](..\media\outside-else-display-message.png)

    ```console
    Get Special Folder
    Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

    If Folder Exists
    If Folder %SpecialFolder%\Records exists

      If File Exists
      If File %SpecialFolder%\Records\Expenses.xlsx exists

        Move File(s)
        Move the file(s) %SpecialFolder%\Records\Expenses.xlsx into %SpecialFolder%

      Else

        Display Message
        Display Message box with message File has already moved

      End If

    Else

      Display Message
      Display Message box with message Records folder does not exist

    End If
    ```

7. We suggest that you run the process, trying different scenarios.
