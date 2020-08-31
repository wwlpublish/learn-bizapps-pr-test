We are going to develop a process that navigates to the properties of the current computer, takes a screenshot of the properties window, and saves it on the desktop.

The process will:
* Retrieve the location of the current user’s desktop folder
* Navigate to this PC by using the Start Menu
* Open the properties of this PC
* Take a screenshot of the window and save it on the desktop 

1. Use the **Get Special Folder action**. Under **Special Folder Name**, select **DesktopDirectory**. 

    ![get special folder exercise part one](..\media\get-special-folder-exercise-part-one.png)

1. Use the **Move Mouse** action. Move the mouse to the Start icon, and press **Ctrl+Shift**. This will enter the coordinates of the start icon into the two coordinate fields under **Move Mouse to**. Set **Move Mouse From Previous Position** to **With Animation (Fast Speed)**.

    ![move mouse exercise part two](..\media\move-mouse-exercise-part-two.png)

1. Add the **Send Mouse Click** action. Leave the **Mouse Event to Send** option on its default setting, Left Click.
 
    ![send mouse click exercise part three](..\media\send-mouse-click-exercise-part-three.png)

1. Add the **Send Keys** action. In **Text to Send** enter **This PC{Enter}{Apps}{R}** and set **Delay Between Keystrokes** to **500 milliseconds**.

    ![send keys exercise part four](..\media\send-keys-exercise-part-four.png)

    * This PC will type the text “This PC” into the Start Menu search
    * {Enter} will simulate pressing the enter key to open this PC
    * {Apps} will open the context menu in the PC window
    * {R} will select and open properties

     ![take screenshot exercise part five](..\media\take-screenshot-exercise-part-five.png)

1. Add the **Take Screenshot** action. Set **Capture** to **Foreground Window**, **Save Screenshot to** to **File**, **Image File** to **%SpecialFolder%\screen.jpg** and **Image Format** to **Jpg**.
 
1. Running the process will result in the screen.jpg file being placed on the current user’s desktop.
