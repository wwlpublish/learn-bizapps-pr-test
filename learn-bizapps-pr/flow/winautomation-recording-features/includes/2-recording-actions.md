The Macro and Web Recorders are used to assist users in the development of Processes. Using a Recorder, users can perform the task manually, and WinAutomation will automatically generate Actions to mimic the user’s behavior.

There are two types of Recorders in WinAutomation:
* The Macro Recorder, used for Windows/UI and Keyboard/Mouse related Actions
* The Web Recorder, used for automating web browser-related Actions

Each of these recorders allows the automatic creation of Actions based on the user’s manual execution of the task to be automated.
## Accessing the Recorders
The Recorders can be used to jump-start the development of a Process; in the WinAutomation Console, press the **New Process** button in the **Processes** tab; the options presented contain both the Macro and Web Recorders:
 

![select macro recorder](..\media\select-macro-recorder.png)

Selecting a Recorder option in this window will immediately start the recording.

The Recorders can also be used during manual development, through the two dedicated buttons in the Process Designer:
  

![process designer recorder buttons](..\media\process-designer-recorder-buttons.png)

## The Macro Recorder
When the Macro Recorder is launched, the Recorder Window will appear:
 

![macro web recorder window](..\media\macro-web-recorder-window.png)

This is where a preview of the recorded Actions will appear during the recording:
 

![recorded actions](..\media\recorded-actions.png)

### Macro Recording types
The Macro Recorder can be configured to either **Smart Recording**, or Recording **Based on Coordinates**. This will affect the type of Actions that will be generated; for example, clicking a button on a local application will produce a **Click Button in Window** Action in **Smart Recording**, and a **Send Mouse Click** Action in **Based on Coordinates** recording.

## The Web Recorder
When the Web Recorder is launched, the user will be prompted to select a web browser:
 

![web recorder instance selection](..\media\web-recorder-instance-selection.png)

[!NOTE]
Using a web browser for Web Recording requires an already open browser instance. The Automation Browser, which is built into WinAutomation, is an exception to this rule.

After a browser is selected, the Recorder Window will appear, as in the Macro Recorder.
 