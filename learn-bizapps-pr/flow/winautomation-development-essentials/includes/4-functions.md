When a Process contains a large number of Actions, it may be split up into Functions, making it more manageable and easier to maintain. Functions can be used to organize a Process’ Actions, but they also allow the reuse of parts of the Process, which helps to avoid cluttering by copy-pasted Actions.

Finished Processes usually contain tens, hundreds, or even thousands of Actions:

![busy workspace](..\media\busy-workspace.png)
 
Let’s improve this Process’ readability without changing its functionality, using Functions to break it up into self-contained Functions. This can be done through the Functions Pane on the top-right.

The Main Function is always present, since it signifies the start of the Process; we will add more Functions by pressing the **New Function** button:

![functions pane](..\media\functions-pane.png)
 
An empty Function is created and named. We will proceed to add a few Functions which correspond to discrete parts of the Process:

![functions pane continued](..\media\functions-pane-continued.png)
 
New Functions are visible as tabs at the top of the workspace:

![functions tabs](..\media\functions-tabs.png)

Now, we can proceed to move Actions from the Main Function into these new ones:

![generate grade sheet function workspace](..\media\generate-grade-sheet-function-workspace.png)
 
Finally, to run the Functions, we must make use of the Run Function Action:

![main function workspace](..\media\main-function-workspace.png)
 
Functions can be run within other Functions as well:

![generate master file function workspace](..\media\generate-grade-sheet-function-workspace.png)
 
