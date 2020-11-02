All WinAutomation processes are stored collectively in one database file called *processes.dat*. The platform uses this file to save new processes or restore existing ones. 

To back up this database:

1.	Navigate to **Settings** and then select **Processes File**.

    ![The Processes File tab.](..\media\processes-file-tab-settings-options.png)

1.	Select **Backup Database**.

    ![A button to backup the database file.](..\media\backup-button-processes-file-tab.png)

1.  In the pop-up window, select a destination folder for the file. 

    ![A popup window to select a destination folder.](..\media\backup-select-destination-folder.png)

Alternatively, you can create a backup of the database by manually copying the file from the defined location.

![The database file selected in the Windows File Explorer.](..\media\backup-file-explorer.png)

The first field of the Processes File tab determines the location of the database file. The default location is: **C:\Users\\\<username\>\Documents\WinAutomation\Processes.dat**

![The location of database file.](..\media\processes-file-location-processes-file-tab.png)

To restore a database file:

1.	Navigate to **Settings** and then **Processes File**.

    ![The Processes File tab.](..\media\processes-file-tab-settings-options.png)

1.	Select **Restore Database**.

    ![A button to restore a database file.](..\media\restore-button-processes-file-tab.png)

1.	In the pop-up window, select the file to be restored.

    ![A popup window to select a database file to be restored.](..\media\restore-select-database-file.png)

You can also restore a database by replacing the current file in the appropriate folder.

> [!WARNING]
> Restoring a database file will delete all of the existing processes in your current database and replace them with the ones from the backup copy. 