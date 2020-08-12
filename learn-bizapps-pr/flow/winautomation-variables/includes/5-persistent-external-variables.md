When you are creating a process with WinAutomation, you may sometimes want to keep the value of a specific variable available for future process runs. Persistent variables allow you to do exactly that: keep a variable’s value available for the next time that the process runs.

By marking a variable as persistent, you can be sure that its value will be kept between process runs. You can set a variable as persistent through the **Tools** menu option > **Variables Manager** window while in the **Process Designer**.

If the variable that you want to make persistent already exists, you can select it in the **User Defined Variables** tab and then click on the **Edit Variable** button. If you want to create a brand new variable and make it persistent, click on the **Add New Variable** button.

![The User Defined Variables tab in the Variables Manager window.](..\media\variables-manager-window-user-defined-variables-with-shape.png)

In the appeared dialog box, you have to enter a name for the new variable and check the **Variable is Persistent** option.

![The Variable is Persistent option in the Create New Variable window.](..\media\create-new-variable-window-variable-is-persistent-option.png)

When you first create a persistent variable, it will not have any stored value. However, if you run the process and give the variable a specific value, you will be able to see the currently stored value from the **Edit Variable** window in the **Variable Manager**.

## External Variables

If from a process (Process A) you run a different process (Process B) by using the **Start Process** action, all variables of Process A are available to Process B. These variables in Process B are considered external variables and can be used for passing data from one process to another.

For Process B to access any of the external variables, the **ext:** prefix must be included before the variable name. For example, if Process A defines a variable **%MyData%**, Process B can access the value of that variable using the notation: **%ext:MyData%**. 

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variabl-action-properties-external-variable.png)