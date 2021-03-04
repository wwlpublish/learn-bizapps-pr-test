For this module, we will create a WinAutomation Process and a Power Automate Flow. The flow will request three inputs from the user and run a process in WinAutomation. The Process will then retrieve the values of the three inputs from the Command Line and store them in an Excel file.

1. Start WinAutomation.
1. Inside **My Processes**, create a folder called **Desktop**.
1. Select the folder and create a new process and name it **Power Automate Exercise**.

   ![Screenshot of the exercise create folder and process WinAutomation.](..\media\exercise-create-folder-and-process.png)

1. Add the **Get Command-Line Arguments** Action from the **WinAutomation Actions** folder. This will retrieve the variables from the Power Automate flow from the Command Line.

   ![Screenshot of the exercise get command line arguments WinAutomation.](..\media\exercise-get-command-line-arguments.png)

1. Add the **Launch Excel Action**. Leave the properties unchanged.

   ![Screenshot of the exercise launch Excel action WinAutomation.](..\media\exercise-launch-excel-action.png)

1. Add the **Write to Excel Worksheet** Action from the **Excel** Folder. Set **Value to Write** to **%CommandLineArguments%** and specify to write to **Column 1** and **Row 1**.

   ![Screenshot of the exercise write to Excel worksheet action WinAutomation.](..\media\exercise-write-excel-worksheet-action.png)

1. **Save** the process and close Process Designer.

1. Go to [flow.microsoft.com](https://flow.microsoft.com/?azure-portal=true), and then navigate to **My Flows**, **desktop flow**, and click on **Create a Desktop flow**.

   ![Screenshot of the go to flows website create a Desktop flow.](..\media\go-to-flows-website-create-ui-flow.png)

1. Select **Desktop App** and click **Next**.

   ![Screenshot of the select desktop app Power Automate.](..\media\select-desktop-app-power-automate.png)

1. Add a name for your flow and click **Next**.

   ![Screenshot of the name flow Power Automate.](..\media\name-flow-power-automate.png)

1. Set up inputs. Add two more inputs of the type **Text**.

   ![Screenshot of the set up inputs Power Automate.](..\media\set-up-inputs-power-automate.png)

1. Fill in the fields as shown in the following table and screenshot and click **Next**:

   | Input Label   | Sample Data   | Input Description|
   |-|-|-|
   | Account Name | Tailwind Traders | Account Name |
   | Primary Contact | Robin Kline | Account Primary Contact |
   | Contact Email | r.kline@tailwindtraders.com | Primary Contact Email |

   ![Screenshot of the data entry inputs Power Automate.](..\media\data-entry-inputs-power-automate.png)

1. Select **+ New Step**.

    ![Screenshot of the add new step Power Automate.](..\media\add-new-step-power-automate.png)

1. Select **Run WinAutomation**.

    ![Screenshot of the select run WinAutomation Power Automate.](..\media\select-run-power-automate.png)

1. Set the process path to **/My Processes/Desktop/Power Automate Exercise**. Use **Add Dynamic Content** to add all three inputs into **Command-Line Arguments**.

    ![Screenshot of the configure WinAutomation action Power Automate.](..\media\configure-action-power-automate.png)

    > [!NOTE]
    > Each argument and dynamic expression should be separated from the previous one by a space, and surrounded by double quotes (for example “alpha” “bravo” “charlie”).

1. Skip the Review Outputs section and go to **Test**. For now, use the previously entered values, and click **Test Now**.

    ![Screenshot of the Test Now Power Automate.](..\media\test-now-power-automate.png)

1. The flow will run, and WinAutomation will display a notification at the bottom right of the screen while the process is running.

    ![Screenshot of the WinAutomation process running Notification.](..\media\winautomation-process-running-notifications.png)

1. When the process completes, click **Save and exit**. There should now be an open Excel document, with the values of the three inputs entered in separate cells.

    ![Screenshot of the Excel output from command line arguments.](..\media\excel-output-command-line-arguments.png)
