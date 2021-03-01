The Switch group of actions is used when a process’ next steps depend on the value of a specific variable. Let’s clarify this with an example.

The following process retrieves a list of all the files in the Documents folder, and produces a file count based on 3 types of filenames: those containing the word **Payments**, those containing the word **Employees**, and those containing the word **Schedule**. A message containing the file counts is then displayed on the screen for the user to review.

First, we will retrieve the path to the Documents folder, retrieve all the files inside, and initialize four variables to act as file counters:

![Screenshot of the following initialization of file counter variables.](..\media\initializing-file-counters.png)

```console
Get Special Folder
Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

Get Files in Folder
Retrieve the file in folder %SpecialFolder% that match * and store them into %Files%

Set Variable
Set variable %Payments% = 0

Set Variable
Set variable %Employees% = 0

Set Variable
Set variable %Schedule% = 0

Set Variable
Set variable %Others% = 0
```

Because the files located in the Documents folder are stored in a list, we will use a For Each loop to iterate through each file:

![Screenshot of the following For each action.](..\media\for-each-action-added.png)

```console
Get Special Folder
Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

Get Files in Folder
Retrieve the file in folder %SpecialFolder% that match * and store them into %Files%

Set Variable
Set variable %Payments% = 0

Set Variable
Set variable %Employees% = 0

Set Variable
Set variable %Schedule% = 0

Set Variable
Set variable %Others% = 0

For Each
Loop for each item contained in variable %Files% and store the current item into %CurrentItem%

End Loop
```

Now, each file must be checked for the required keywords. To achieve this, we will use a **Switch** action:

![Screenshot of Properties of 'Switch' action with Value to Check set to %CurrentItem% and the OK button highlighted.](..\media\switch-current-item.png)

![Screenshot of the following Switch action.](..\media\switch-action-added.png)

```console
Get Special Folder
Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

Get Files in Folder
Retrieve the file in folder %SpecialFolder% that match * and store them into %Files%

Set Variable
Set variable %Payments% = 0

Set Variable
Set variable %Employees% = 0

Set Variable
Set variable %Schedule% = 0

Set Variable
Set variable %Others% = 0

For Each
Loop for each item contained in variable %Files% and store the current item into %CurrentItem%

  Switch %CurrentItem%
  End Switch

End Loop
```

Next, we will add the alternative cases, using **Case** actions. The **Contains** comparison is used, since filenames may contain more characters than our keywords:

![Screenshot of Properties of 'Case' action with Comparison Type set to Contains, Ignore Case selected, Value to Compare set to Payments, and the OK button highlighted.](..\media\case-contains-payments.png)

Eventually, the process should look like this:

![Screenshot of the following Switch action with cases added.](..\media\cases-added.png)

```console
Get Special Folder
Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

Get Files in Folder
Retrieve the file in folder %SpecialFolder% that match * and store them into %Files%

Set Variable
Set variable %Payments% = 0

Set Variable
Set variable %Employees% = 0

Set Variable
Set variable %Schedule% = 0

Set Variable
Set variable %Others% = 0

For Each
Loop for each item contained in variable %Files% and store the current item into %CurrentItem%

  Switch %CurrentItem%
    Case: contains Payments
    End Case
    Case: contains Employees
    End Case
    Case: contains Schedule
    End Case
  End Switch

End Loop
```

We will also add an unconditional alternative, in case some files contain none of our keywords:

![Screenshot of the following Switch action with the default case added.](..\media\default-case-added.png)

```console
Get Special Folder
Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

Get Files in Folder
Retrieve the file in folder %SpecialFolder% that match * and store them into %Files%

Set Variable
Set variable %Payments% = 0

Set Variable
Set variable %Employees% = 0

Set Variable
Set variable %Schedule% = 0

Set Variable
Set variable %Others% = 0

For Each
Loop for each item contained in variable %Files% and store the current item into %CurrentItem%

  Switch %CurrentItem%
    Case: contains Payments
    End Case
    Case: contains Employees
    End Case
    Case: contains Schedule
    End Case
    Default Case
    End Default Case
  End Switch

End Loop
```

Inside each case, we will increase the respective counter variable; finally, a message box will be displayed:

![Screenshot of the following completed Switch action to increase counters based on the switch value.](..\media\increasing-counters-based-on-switch-value.png)

```console
Get Special Folder
Get the path of the folder DesktopDirectory and store it into %SpecialFolder%

Get Files in Folder
Retrieve the file in folder %SpecialFolder% that match * and store them into %Files%

Set Variable
Set variable %Payments% = 0

Set Variable
Set variable %Employees% = 0

Set Variable
Set variable %Schedule% = 0

Set Variable
Set variable %Others% = 0

For Each
Loop for each item contained in variable %Files% and store the current item into %CurrentItem%

  Switch %CurrentItem%
    Case: contains Payments
      Increase Variable
      Increase Variable %Payments% by 1
    End Case
    Case: contains Employees
      Increase Variable
      Increase Variable %Employees% by 1
    End Case
    Case: contains Schedule
      Increase Variable
      Increase Variable %Schedule% by 1
    End Case
    Default Case
      Increase Variable
      Increase Variable %Others% by 1
    End Default Case
  End Switch

End Loop

Display Message
Display Message box with title Files report and message Files report

Payments: %Payments%
Employees: %Employees%
Schedule: %Schedule%
Others: %Others%
```
