Exception handling is often added to an already developed process, when certain risks are identified through testing.

In this exercise, you'll apply exception handling rules to a process that has already been developed and tested, to address certain issues that have been identified.

## Set up exception handling for an individual action

This process downloads an Excel file to the user’s Desktop, and proceeds to modify its data into a new worksheet.

The **Download from Web** action has been identified as a potential risk, because internet connectivity isn't always stable. To address this risk, you'll have to set up its exception handling properties.

### Step 1

Edit the action and navigate to **Exception Handling**. Then, activate the following options:

- Retry Action 2 times, with a 3-second interval,
- Run the **Check Web Access** Function, and
- Continue Process Execution, by repeating the Action.

The **Exception Handling** tab should look like this:

![The Exception Handling tab in the Download from Web action's properties.](..\media\download-from-web-action-properties.png)
 
In case this action fails, it will first retry two times, 3 seconds apart; if all retries fail, the **Check Web Access** function will be executed. This function has been designed to ping [www.microsoft.com](www.microsoft.com), to check whether there are issues with web connectivity - if the ping action produces a **Failed** result, a log entry is created in a text file on the user’s Desktop, and the process is aborted:

![The created process in the Workspace.](..\media\workspace.png)

In case the machine’s internet connectivity is at fault, the process will terminate; otherwise, the action’s exception handling will continue, so the action will be repeated.

## Set up exception handling for a block of actions

Having ensured that the **Download from Web** action will run as intended, let’s proceed to the part of the process that utilizes Excel to modify the file’s data.

After the file is opened, a series of actions are performed on its contents. Due to hardware limitations and the size of the data, the performance of the machine where this task takes place drops, sometimes causing Excel to become unresponsive. For this reason, you will have to add exception handling to all the Excel-related actions, since there is no single action which poses the risk.

### Step 2

To achieve this, add a **Begin Exception Block** action after the file is opened, and configure it so that it runs the **Restart Excel** function. Then, it continues execution by repeating the failed action:

![The Begin Exception Block action's properties.](..\media\begin-exception-block-action-properties-b.png)
 
### Step 3

Press **OK**, and move the **End Exception Block** action after the file is closed:

![The created process in the Workspace.](..\media\workspace-b.png)
  
The **Restart Excel** function simply saves the file in its current state, closes it, then reopens it. Therefore, if any of the Excel-related actions fails, the process will save and close the file, reopen it, and attempt to resume execution.