Conditionals are used to modify a process’ behavior based on certain conditions. Conditions may include the comparison of two values, or more specific information, such as the existence of a file or the contents of a web page.

Conditional actions are divided into two major categories in WinAutomation, based on their functionality. These are:

* The If group of actions
* The Switch group of actions

## If group of actions

The If group of actions allow users to evaluate whether a certain condition is true. The structure of an If conditional is as below:

* Initial condition
* Alternative conditions (0 or more)
* Unconditional alternative (optional)
* End of conditional block

Thus, the simplest If structure is as below:

![Screenshot of the following If action.](..\media\simplest-if.png)

```console
If %UrgentCell% = Urgent then
  Write to Excel Worksheet
  Write the value 12 hours into the cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%
End If
```

![Screenshot of Properties of 'If' action with input fields First Operand set to %UrgentCell%, Operator set to =, and Second Operand set to Urgent.](..\media\if-cell-contains-urgent.png)

Configured this way, Action #2 will only run if the %UrgentCell% variable contains the value **Urgent**.

Some initial conditions in the If group are **If**, **If File Exists**, **If Window Contains**, **If Text on-Screen** actions. All conditional blocks in the **If** group end with the **End If** Action.

Alternative conditions may be added using the **Else If** Action; these conditions will only be considered if all the previous conditions were false. For example, in the process below, the Subscription cell will only be selected if the initial condition is not met; in this case, if the %UrgentCell% variable does not contain the value **Urgent**:

![Screenshot of the following Else if action.](..\media\else-if-action.png)

```console
If %UrgentCell% = Urgent then
  Write to Excel Worksheet
  Write the value 12 hours into the cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%
Else If
  Write to Excel Worksheet
  Write the value 1 Day into the cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%
End If
```

Multiple alternative conditions can be added, and these conditions do not necessarily have to be related.

An unconditional alternative may also be added, using the **Else** Action; this will run if all the conditions before it have failed:

![Screenshot of the following Else action.](..\media\else-action.png)

```console
Get Current Date and Time
Retrieve the current date and time and store it into %CurrentDateTime%
If %CurrentDateTime.DayOfWeek% = Saturday then
  Display Message
  Display Message box with title It's Saturday and message Make the most of it!
Else If %CurrentDateTime.DayOfWeek% = Sunday then
  Display Message
  Display Message box with title It's Sunday and message Better rest up for the week ahead!
Else
  Display Message
  Display Message box with title It's a weekday and message Let's get cracking!
End If
```

## Switch group of actions

The Switch group of actions is designed to evaluate a single variable and compare it to other values. Switch and If actions vary in the following ways:

* If blocks allow more than one variable to be evaluated and compared with others; Switch checks a single variable
* If actions may be used to evaluate more than the value of a variable (for example, checking whether folders or files exist, checking values of web page or  window content); Switch actions work only with values and variables

The structure of a Switch conditional is:

* Initial value input
* Alternative cases (1 or more)
* Unconditional case (optional)
* End of conditional block

Thus, the simplest Switch structure is:

![Screenshot of the following switch action.](..\media\simplest-switch.png)

```console
Switch %UrgentCell%
  Case: = Urgent
    Write to Excel Worksheet
    Write the value 12 hours into the cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%
  End Case
End Switch
```

![Screenshot of Properties of 'Switch' action with Value to Check set to %UrgentCell% and the OK button highlighted.](..\media\switch-cell-contents.png)

![Screenshot of Properties of 'Case' action with Comparison Type set to =, Value to Compare set to Urgent, and the OK button highlighted.](..\media\case-action.png)

As with the If group of actions, the **Write to Excel Worksheet** action will only run if the %UrgentCell% variable contains the value **Urgent**.

Each Switch block begins with the **Switch** Action and ends with an **End Switch** Action. Alternative cases are added within the Switch block, using the **Case** and **End Case** actions.

Multiple alternative conditions can be added; these conditions will all refer to the variable specified in the **Switch** Action.

An unconditional alternative may also be added, using the **Default Case** Action; as was the case in the **If** group of actions, this will run if no other **Case** Action before it runs:

![Screenshot of the following Default Case action.](..\media\default-case.png)

```console
Get Current Date and Time
Retrieve the current date and time and store it into %CurrentDateTime%
Switch %CurrentDateTime.DayOfWeek% 
  Case: = Saturday
    Display Message
    Display Message box with title It's Saturday and message Make the most of it!
  End Case
  Case: = Sunday then
    Display Message
    Display Message box with title It's Sunday and message Better rest up for the week ahead!
  Default Case
    Display Message
    Display Message box with title It's a weekday and message Let's get cracking!
  End Default Case
End Switch
```
