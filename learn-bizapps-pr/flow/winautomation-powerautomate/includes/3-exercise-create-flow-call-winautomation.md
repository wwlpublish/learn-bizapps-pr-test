For this module, we will create a WinAutomation Process and a Power Automate Flow. The flow will request three inputs from the user and run a process in WinAutomation. The Process will then retrieve the values of the three inputs from the Command Line and store them in an Excel file.

1. Start WinAutomation. 
1. Inside **My Processes**, create a folder called **Desktop**. 
1. Select the folder and create a new process and name it **Power Automate Exercise**.

   ![exercise create folder and process WinAutomation](..\media\exercise-create-folder-and-process-WinAutomation.png)

1. Add the **Get Command-Line Arguments** Action from the **WinAutomation Actions** folder. This will retrieve the variables from the Power Automate flow from the Command Line.

   ![exercise get command line arguments WinAutomation](..\media\exercise-get-command-line-arguments-WinAutomation.png)

1. Add the **Launch Excel Action**. Leave the properties unchanged.

   ![exercise launch Excel action WinAutomation](..\media\exercise-launch-Excel-action-WinAutomation.png)

1. Add the **Write to Excel Worksheet** Action from the **Excel** Folder. Set **Value to Write** to **%CommandLineArguments%** and specify to write to **Column 1** and **Row 1**.

   ![exercise write to Excel worksheet action WinAutomation](..\media\exercise-write-to-Excel-worksheet-action-WinAutomation.png)

1. **Save** the process and close Process Designer.
 
1. Go to **https://flow.microsoft.com/**, and then navigate to **My Flows**, **UI Flows**, and click on **Create a UI Flow**.

   ![go to flows website create a UI flow](..\media\go-to-flows-website-create-a-UI-flow.png)

1. Select **Desktop App** and click **Next**.

   ![select desktop app Power Automate](..\media\select-desktop-app-PowerAutomate.png)
 
1. Add a name for your flow and click **Next**.

   ![name flow Power Automate](..\media\name-flow-PowerAutomate.png)

1. Set up inputs. Add two more inputs of the type **Text**.

   ![set up inputs Power Automate](..\media\set-up-inputs-PowerAutomate.png)

1. Fill in the fields as shown in the following table and screenshot and click **Next**:


   | Input Label   | Sample Data   | Input Description|
   |-|-|-|
   | Account Name | Aileron Roll | Account Name |
   | Primary Contact | Norbert Varga | Account Primary Contact |
   | Contact Email | n.varga@aileronroll.com | Primary Contact Email |

   ![data entry inputs Power Automate](..\media\data-entry-inputs-PowerAutomate.png)
 
 1. Select **+ New Step**.

   ![add new step Power Automate](..\media\add-new-step-PowerAutomate.png)
 
1. Select **Run WinAutomation**.

   ![select run WinAutomation Power Automate](..\media\select-run-WinAutomation-PowerAutomate.png)

1. Set the process path to **/My Processes/Desktop/Power Automate Exercise**. Use **Add Dynamic Content** to add all three inputs into **Command-Line Arguments**.

   ![configure WinAutomation action Power Automate](..\media\configure-WinAutomation-action-PowerAutomate.png)

> [!NOTE]
> Each argument and dynamic expression should be separated from the previous one by a space, and surrounded by double quotes (for example “alpha” “bravo” “charlie”).

1. Skip the Review Outputs section and go to **Test**. For now, use the previously entered values, and click **Test Now**.

   ![Test Now Power Automate](..\media\Test-Now-PowerAutomate.png)
 
1. The flow will run, and WinAutomation will display a notification at the bottom right of the screen while the process is running.

   ![WinAutomation process running Notification](..\media\WinAutomation-process-running-Notification.png)

1. When the process completes, click **Save and exit**. There should now be an open Excel document, with the values of the three inputs entered in separate cells.

   ![Excel output from command line arguments](..\media\Excel-output-from-command-line-arguments.png)
