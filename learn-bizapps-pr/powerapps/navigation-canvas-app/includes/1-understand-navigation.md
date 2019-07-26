In PowerApps, because most apps have multiple screens, it's essential that you understand how to implement the Navigate function in your app. The Navigate function allows users to move or navigate from screen to screen in an app. For example, if you create an app with three screens and you want to give users a way to navigate to another screen, set the
**OnSelect** property of a Button control to:

**Navigate(Screen2,ScreenTransition.Cover)**

With this formula, when the button is selected, 
Screen2 will automatically display. You could also use this formula on an icon, like
an arrow, to provide navigation in the app.

The Navigate function also allows for a visual transition as the users
move from screen to screen, which is set using **ScreenTransition**. In
the example shown above, **ScreenTransition.Cover** was
applied. There are a few different ScreenTransitions to choose from, and
each one provides a slightly different user experience when navigating
screens. ScreenTransitions will be covered in further detail later in
this module. Similar to the Navigate function, you also have the option
to use the Back() function. The Back() function is fairly
straight-forward, it sends the user back to the previous screen.

You can use Navigate to set one or more context variables. You can use
this approach to pass parameters to a screen. If you've used another
programming tool, this is similar to passing parameters to
procedures. 

Hidden screens
--------------

You can have "Hidden screens" in your app for various purposes, such
as:

-   Documentation screen

-   Settings screen

-   Special permissions screen

A "Hidden screen" allows the creator of the app to add screens but not
give users to access those screens. This is accomplished by not creating
any navigation for users to those screens. There's an example
later in this module to demonstrate this functionality further.
