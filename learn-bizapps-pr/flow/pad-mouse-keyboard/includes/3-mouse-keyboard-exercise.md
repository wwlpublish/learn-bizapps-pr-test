Design a flow that navigates to the properties of the current computer, takes a screenshot of the properties window, and saves it on the desktop.

The flow will:

* Retrieve the location of the current user’s desktop folder
* Navigate to this PC by using the Start Menu
* Open the properties of this PC
* Take a screenshot of the window and save it on the desktop

1. Use the **Get special folder action**. Under **Special folder name**, select **Desktop**.

    ![Screenshot of the Get special folder action properties dialog.](..\media\get-special-folder-exercise-part-one.png)

1. Use the **Move mouse** action. Set the coordinates of the Start button, and set **Move mouse from previous position** to **With animation (high speed)**.

    ![Screenshot of the Move mouse action properties dialog.](..\media\move-mouse-exercise-part-two.png)

> [!NOTE]
> If your start button is in the default bottom left position, enter Position X: 0. Position Y in this case is going to be your monitor's vertical resolution. These coordinates will take your mouse to the bottom left of your screen. Otherwise, a quick way of finding the coordinates of the Start button is to add a Get mouse position action, move the mouse to the Start button while the Flow Designer window is in the foreground, and pressing F5 to run the flow. The variables from the action will record the coordinates of the Start button. Make sure to delete or disable the Get mouse position after you have noted the required coordinates.

1. Add the **Send Mouse Click** action. Leave the **Mouse event to send** option on its default setting, Left Click.

    ![Screenshot of the Send mouse click action properties dialog.](..\media\send-mouse-click-exercise-part-three.png)

1. Add the **Send keys** action. In **Text to send** enter **This PC{Enter}{Apps}{R}** and set **Delay between keystrokes** to **500**.

    ![Screenshot of the Send keys action properties dialog.](..\media\send-keys-exercise-part-four.png)

    * This PC will type the text “This PC” into the Start Menu search
    * {Enter} will simulate pressing the enter key to open this PC
    * {Apps} will open the context menu in the PC window
    * {R} will select and open properties

     ![Screenshot of the Take screenshot action properties dialog.](..\media\take-screenshot-exercise-part-five.png)

1. Add the **Take screenshot** action. Set **Capture** to **Foreground window**, **Save screenshot to** to **File**, **Image file** to **%SpecialFolder%\screen.jpg** and **Image format** to **JPG**.

1. Running the flow will result in the screen.jpg file being placed on the current user’s desktop.
