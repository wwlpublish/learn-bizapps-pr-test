In the previous section, you learned how to implement the Navigate and Back() functions using a Control. When implementing these functions, like any other function in PowerApps, there are certain arguments that need to be defined.

Navigate function
---------------------

Here's a breakdown of the syntax for the navigation function:

**Navigate**(*Screen*, *Transition* [, *UpdateContextRecord* ] )

-   **Screen** - Required. The name of the screen to display.

-   **ScreenTransition** - Required. The visual transition to use
    between the current screen and the next screen. 

-   **UpdateContextRecord** - Optional. A record that contains the
    name of at least one column and a value for each column. This record
    updates the context variables of the new screen. For more information, see
    [UpdateContext
    function in PowerApps](https://docs.microsoft.com/powerapps/maker/canvas-apps/functions/function-updatecontext).

In the first argument, you specify the name of the screen to display. In
the second argument, you specify how the old screen changes to the new
screen. In the third argument, you have the option to specify a Context
variable. Taking a step back to the second argument, ScreenTransition,
there are a number of different ScreenTransitions you could apply. Each
ScreenTransition produces a slightly different visual experience for the
user.

Screen transitions
------------------

 **ScreenTransition.Cover** - The new screen slides into view,
    covering the current screen.

**ScreenTransition.Fade** - The old screen fades away to reveal the
    new screen.

**ScreenTransition.None** - The old screen is quickly replaced with
    the new screen.

**ScreenTransition.UnCover** - The old screen slides out of view,
    uncovering the new screen.

Here are some examples using ScreenTransitions.


| **Formula**                     | **Description**                  | **Result**          |
| :------------------- | :------------------- |:----------------|
| **Navigate( Details, ScreenTransition.None )**   | Displays the **Details** screen with no transition or change in value for a context variable. | The **Details** screen appears quickly. |
|  **Navigate( Details, ScreenTransition.Fade )**                  | Displays the **Details** screen with a **Fade** transition. No value of a context variable is changed.                   | The current screen fades away to show the **Details** screen.            |
|  **Navigate( Details, ScreenTransition.Fade, { ID: 12 } )**                   | Displays the **Details** screen with a **Fade** transition, and updates the value of the **ID** context variable to **12**.                  | The current screen fades away to show the **Details** screen, and the context variable **ID** on the screen is set to **12**.            |
                                                                                                                                                               
                                            
The **Back ()** function has an optional argument
for ScreenTransition.

Here's a more detailed example using these functions with multiple
controls in a common real-world scenario. In many of the apps that you
develop, certain screens may have multiple controls allowing users to
navigate to different screens depending on the control they select. In
the following example, you will create a simple three screen app to
demonstrate the **Navigate** and **Back()** functionality.

1.  In PowerApps Studio, create 3 blank screens.

2.  On Screen1, add a **Button** control and change the **Text**
    property to **Next**.

3.  On Screen2, add 2 **Button** controls and change the **Text** of one
    button to **Next** and the other button control to **Back**.

4.  On Screen3, add a **Button** control and change the **Text**
    property to **Back**.

5.  On Screen1, set the **OnSelect** property to

> **Navigate(Screen2,ScreenTransition.Fade)**.

6.  On Screen2, set the **OnSelect** property for the Next button to

> **Navigate(Screen3,ScreenTransition.Cover)**.

7.  Set the **OnSelect** property for the Back button to **Back().**

8.  On Screen3, set the **OnSelect** property for the Back button to
    **Back()**.

9.  To test this, put the app in Preview or Play mode and navigate
    through the app as a user would.

As you select each button, notice the subtle visual transitions of each
ScreenTransition. Remember, the Navigate function must include a
ScreenTransition. If you tried to write your Navigate function like
this, **Navigate(Screen2)**, PowerApps would display a red squiggly line
in the formula box indicating that there is an issue with the function as
written.

Back () function
--------------------

When using the **Back()** function it should be noted, this will take
you back to the previous screen that you navigated from, the key word being
"navigated". To elaborate, this does not mean the screen you or the user
was just on, you need to use the **Navigate** function to navigate
away from the screen to then use the **Back()** function to get back
there. This can be a little confusing, so here's an example of how this works. 

In the previous example there are 3 screens. Update the **OnSelect**
property of the Next button on Screen1 from
**Navigate(Screen2,ScreenTransition.Cover)** to
**Navigate(Screen3,ScreenTransition.Cover)** and the **text** property
to **Jump to Screen 3**. Now, when the user selects the button, the app
will navigate to Screen3. Then when they select the Back button on
Screen3, they will navigate back to Screen1 and skip Screen2 entirely.
This is by design in PowerApps and is important to concept understand to ensure
the navigation in your app is configured properly.

Before moving on to the next section, add one more screen to the example
app and rename the screen **Documentation**. With no Navigation pointing to this screen, it is not accessible to your end users. The purpose of this screen is to give the App creator a location in the app to make notes or add documentation about certain aspects of how the app functions. The App creator can also provide instructions for other editors of the app so they can quickly and easily identify what the previous creator did.

In this simple four screen app example, you can see how easy it is to
navigate screens by setting the **OnSelect** property of a control.
There are several additional ways to navigate through your app covered
in the next section.
