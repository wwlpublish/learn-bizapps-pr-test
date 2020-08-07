Conditionals are used to modify a Process’ behavior based on certain conditions. Conditions may include the comparison of two values, or more specific information, such as the existence of a file or the contents of a web page.

Conditional Actions are divided into two major categories in WinAutomation, based on their functionality. These are:
* The **If** group of Actions
* The **Switch** group of Actions
## **If** group of Actions
The **If** group of Actions allow Users to evaluate whether a certain condition is true. The structure of an **If** conditional is as below:
* Initial condition
* Alternative conditions (0 or more)
* Unconditional alternative (optional)
* End of conditional block

Thus, the simplest **If** structure is as below:

![Simplest if structure](..\media\simplest-if.png)

![If cell contains urgent](..\media\if-cell-contains-urgent.png)

Configured this way, Action #2 will only be executed if the %UrgentCell% variable contains the value **Urgent**.

Some initial conditions in the **If** group are **If**, **If File Exists**, **If Window Contains**, **If Text on Screen** Actions. All conditional blocks in the **If** group end with the **End If** Action.

Alternative conditions may be added using the **Else If** Action; these conditions will only be considered if all the previous conditions were false. For example, in the Process below, the Subscription cell will only be checked if the initial condition is not met; in this case, if the %UrgentCell% variable does not contain the value **Urgent**:

![Else if action](..\media\else-if-action.png) 

Multiple alternative conditions can be added, and these conditions do not necessarily have to be related, as seen in the example above.

An unconditional alternative may also be added, using the **Else** Action; this will be executed if all the conditions before it have failed:

![Else action](..\media\else-action.png) 

## **Switch** group of Actions
The **Switch** group of Actions is designed to evaluate a single variable and compare it to other values. The points where it differs from the **If** group are:
* **If** blocks allow more than one variable to be evaluated and compared with others; **Switch** only checks one variable
* **If** group of Actions may be used to evaluate more than the value of a variable (check if folders or files exist, check web page and window content, etc.); **Switch** only works with values and variables
* Slight differences in structure

The structure of a **Switch** conditional is as below:
* Initial value input
* Alternative cases (1 or more)
* Unconditional case (optional)
* End of conditional block

Thus, the simplest **Switch** structure is as below:

![Simplest switch action](..\media\simplest-switch.png)

![Switch cell contents](..\media\switch-cell-contents.png)

![Case action](..\media\case-action.png)
    
As with the **If** group of Actions, the **Write to Excel Worksheet** Action will only be executed if the %UrgentCell% variable contains the value **Urgent**.

Each Switch block begins with the **Switch** Action and ends with an **End Switch** Action. Alternative cases are added within the Switch block, using the **Case** and **End Case** Actions.

Multiple alternative conditions can be added; these conditions will all refer to the variable specified in the **Switch** Action.

An unconditional alternative may also be added, using the **Default Case** Action; as was the case in the **If** group of Actions, this will be executed if no other **Case** Action before it has been executed:

![Default case](..\media\default-case.png)