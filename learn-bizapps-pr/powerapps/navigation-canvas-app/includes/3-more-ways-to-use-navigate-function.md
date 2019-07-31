As previously mentioned, one of the most common ways to move from screen to screen is by setting the OnSelect property of a control. Keep in mind that there are also several other ways to trigger the Navigate or Back() functions.

Navigating screens by setting the OnChange property of a drop-down control
-------------------------------------------------------------------------

One option is to you use a **DropDown** control and an If statement.
With this solution, depending on the choice selected in the drop-down menu the
app navigates to a specific screen.

1.  In PowerApps Studio, add 2 blank screens. There should be a total of
    3 blank screens.

2.  On Screen1, add a **dropdown** control.

3.  Set the **Items** property for the **dropdown** control to

```
[" ", "Active","Inactive"]
```

4.  Set the **OnChange** property for the **dropdown** control to the following

```
If(Dropdown1.Selected.Value ="Active",Navigate(Screen2,ScreenTransition.Cover),
If(Dropdown1.Selected.Value = "Inactive",Navigate(Screen3,ScreenTransition.Fade)))
```

On your keyboard, hold the Alt key to test the new functionality.
When the user selects **Active** from the drop-down menu, the user will be sent
to Screen2. When the user selects **Inactive** from the drop-down menu, the user
will be sent to Screen3. Finally, if the blank option is selected from
the drop-down menu, the app will not navigate to another screen.

Using variables and the Timer control to navigate screens
---------------------------------------------------------

You can use a variable and an If statement to set navigation. Depending
on what the variable is set to this will send the user to a specific screen. For
example, if you have the question "Do you have additional feedback to
provide regarding this incident?" If the user selects "Yes", then you
want to open the **Additional Information** screen. If the user selects,
"No", then you want to load the **Form Completed** screen.

Another option is to use a timer control. When the time runs out, the
app navigates to a different screen. For example, maybe you only want to
allow a users 30 seconds to answer the questions on a screen before
navigating to the next set of questions.

The following example builds off the previous example and incorporates variables and a
Timer control.

1.  On Screen1, add a **Timer** control.

2.  Set the **Duration** property to 10000 (milliseconds).

3.  Set the **OnTimerEnd** property to

```
If(Dropdown1.Selected.Value = " ",Navigate(Screen2,ScreenTransition.None))
```

4.  Select the drop-down control and change the **OnChange** property to

```
If(Dropdown1.Selected.Value =
"Active",Set(varStatus,1),If(Dropdown1.Selected.Value =
"Inactive",Set(varStatus,2),Set(varStatus,0)))
```

5.  Add a **Button** control under the drop-down menu, and set the **Text**
    property to **Next**.

6.  Set the **OnSelect** property for the button to

```
If(varStatus = 1,Navigate(Screen2,ScreenTransition.Cover),
If(varStatus = 2,Navigate(Screen3,ScreenTransition.Fade)))
```

Now, if the Timer Ends, the user is automatically sent to Screen two. If the user selects **Active** from the drop-down menu, a Variable named varStatus is set to 1. When the user selects the **Next** button, they will be sent to Screen2. If the user selects **Inactive** from the drop-down menu, a Variable named varStatus is set to 2. When the user selects the **Next** button, they will be sent to Screen3.
Test this by putting the app in Preview or Play mode, select the Timer control and wait for 10 seconds. Now test the variables by selecting **Active** or **Inactive** from the drop-down menu and selecting the **Next** button.

As you can see there are different ways to configure navigation in your app. In the previous example, the navigation automatically changed when the user selects a value in the drop-down control. In the second example, navigation can happen in two different ways: when the timer reaches zero or when the user selects a button. The variable still allows you to control which screen they navigate to based on the drop-down value selected, but they will not automatically navigate there when the value is selected. You have the flexibility to choose what works best in your solution.
