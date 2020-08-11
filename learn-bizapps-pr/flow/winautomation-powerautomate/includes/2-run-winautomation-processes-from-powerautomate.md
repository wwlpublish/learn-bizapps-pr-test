Once you have created your automation Process in WinAutomation, you can run it from a flow in Power Automate through UI flows (desktop) attended or unattended. 
Create a new desktop UI flow. Delete the default first step of **Record app**.

![Record app first step deletion](..\media\Record-app-first-step-deletion.png)

Select **New step**, select **WinAutomation**, and then select the **Run WinAutomation (preview)** action.

![choose an action select WinAutomation](..\media\choose-an-action-select-WinAutomation.png)

1.	In the **Run WinAutomation (preview)** card, fill in the **Process Path** and any optional **command-line arguments** for the WinAutomation Process that you want to run.

![configure WinAutomation action](..\media\configure-WinAutomation-action.png)

> [!NOTE]  
> You must create and store WinAutomation Processes locally. Process Path is a case-sensitive path in the WinAutomation Console for the Process, from a base directory of My Processes in the Folders Pane on the left side. If you have put the Process in a subfolder, you will need to include that information in the Process Path. Don’t put quotes around the Process Path.

> [!TIP]  
> You can use UI flows inputs and Dynamic content in the target WinAutomation Process path and arguments from Power Automate flow.
  1. You can now save and test your UI flow to see how it launches the WinAutomation Process.
  1. You can then add the UI flow into a flow. You can even connect to other Power Automate connectors and triggers.
  1. You can then select attended or unattended as the run type.
 
> [!IMPORTANT]
> In your WinAutomation Process, you can use the Get Command-Line Arguments action to retrieve the command-line arguments. The variable %CommandLineArguments% is a List of Text Values. Any value in the list can be referenced with its index. For example If we have a list of three text values [“Alpha”,”Bravo”,”Charlie”], to retrieve the first item in a list, we will reference it like so: %CommandLineArguments[0]%. The second and third items are referenced with the indices [1] and [2], respectively.

![Get Command Line Arguments action properties](..\media\Get-Command-Line-Arguments-action-properties.png)

> [!IMPORTANT]  
> Do not pass sensitive text such as passwords through the command-line arguments.

> [!IMPORTANT]  
> If you’re running UI flows on an unattended cluster, ensure that WinAutomation is installed on all machines on which the target Process is copied. For more information on attended and unattended UI flows, click here.
1. You can save and then run the flow and see it launch the WinAutomation Process. The UI flow will return after the WinAutomation Process run completes. You can view the run results from Power Automate. If the Process fails, you can see the error messages as well.

> [!TIP]  
> If you get exceptions, you may not have the latest UI flows installed. Install the latest UI flows.

1. If you want WinAutomation to capture a screenshot when a Process fails, do the following:
1. From the WinAutomation Console, right click on a Process, select "Edit Process's Properties". Go to the "Error Handling" tab and choose "Override Default Options". Click "Add screenshot to logs" and save. Now if a Process fails, you can view the screenshot captured at runtime from the Power Automate UI flow run details. For more information on Process properties, see WinAutomation docs: Process Properties.

![WinAutomation process properties error handling tab](..\media\WinAutomation-process-properties-error-handling-tab.png)

Currently you have to use certain WinAutomation steps to write results and outputs from the process into a file in the cloud share or email the results out. Then you can use connectors from Power Automate to access and use those results.