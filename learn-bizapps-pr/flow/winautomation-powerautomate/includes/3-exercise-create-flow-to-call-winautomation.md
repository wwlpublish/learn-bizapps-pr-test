For this module, we will create a WinAutomation Process and a PowerApps Flow. The flow will request three inputs from the user and run a process in WinAutomation. The Process will then retrieve the values of the three inputs from the Command Line and store them in an Excel file.

Start WinAutomation. Inside **My Processes**, create a folder called **Desktop**. Select the folder and create a new process and name it **Power Automate Exercise**.

![exercise create folder and process WinAutomation](..\media\exercise-create-folder-and-process-WinAutomation.png)

Add the **Get Command-Line Arguments** Action from the **WinAutomation Actions** folder. This will retrieve the variables from the PowerApps flow from the Command Line.

![exercise get command line arguments WinAutomation](..\media\exercise-get-command-line-arguments-WinAutomation.png)

Add the **Launch Excel Action**. Leave the properties unchanged.

![exercise launch Excel action WinAutomation](..\media\exercise-launch-Excel-action-WinAutomation.png)

Add the **Write to Excel Worksheet** Action from the **Excel** Folder. Set **Value to Write** to **%CommandLineArguments%** and specify to write to **Column 1** and **Row 1**.

![exercise write to Excel worksheet action WinAutomation](..\media\exercise-write-to-Excel-worksheet-action-WinAutomation.png)

**Save** the process and close Process Designer.
 
Go to **https://flow.microsoft.com/**, and then navigate to **My Flows**, **UI Flows**, and click on **Create a UI Flow**.

![go to flows website create a UI flow](..\media\go-to-flows-website-create-a-UI-flow.png)

Select **Desktop App** and click **Next**.

![select desktop app PowerApps](..\media\select-desktop-app-PowerApps.png)
 
Add a name for your flow and click **Next**.

![name flow PowerApps](..\media\name-flow-PowerApps.png)

The first step is to Set up inputs. Add **2** more inputs of the type **Text**.

![set up inputs PowerApps](..\media\set-up-inputs-PowerApps.png)

Fill in the fields as in the following table and screenshot and click **Next**:


| Input Label   | Sample Data   | Input Description|
|-|-|-|
| Account Name | Aileron Roll | Account Name |
| Primary Contact | Norbert Varga | Account Primary Contact |
| Contact Email | n.varga@aileronroll.com | Primary Contact Email |

![data entry inputs PowerApps](..\media\data-entry-inputs-PowerApps.png)
 
Click **+ New Step**.

![add new step PowerApps](..\media\add-new-step-PowerApps.png)
 
Select **Run WinAutomation**.

![select run WinAutomation PowerApps](..\media\select-run-WinAutomation-PowerApps.png)

Set the Process Path to **/My Processes/Desktop/Power Automate Exercise**. Use **Add Dynamic Content** to add all three inputs into **Command-Line Arguments**.

![configure WinAutomation action PowerApps](..\media\configure-WinAutomation-action-PowerApps.png)

> [!NOTE]
> Each argument and dynamic expression should be separated from the previous one by a space, and surrounded by double quotes (for example “alpha” “bravo” “charlie”).

Skip the Review Outputs section and go to **Test**. For now, use the previously entered values, and click **Test Now**.

![Test Now PowerApps](..\media\Test-Now-PowerApps.png)
 
The flow will run, and WinAutomation will display a notification at the bottom right of the screen while the process is running.

![WinAutomation process running Notification](..\media\WinAutomation-process-running-Notification.png)

When the process completes, click **Save and exit**. There should now be an open Excel document, with the values of the three inputs entered in separate cells.

![Excel output from command line arguments](..\media\Excel-output-from-command-line-arguments.png)