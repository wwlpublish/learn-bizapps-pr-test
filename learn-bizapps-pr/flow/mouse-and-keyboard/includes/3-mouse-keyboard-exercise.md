We are going to develop a Process that navigates to the Properties of the current computer, takes a screenshot of the properties window, and saves it on the Desktop.
The process will:
* Retrieve the location of the current user’s Desktop folder
* Navigate to This PC via the Start Menu
* Open the properties of This PC
* Take a screenshot of the window and save it on the Desktop 

First, use the **Get Special Folder Action**. Under **Special Folder Name**, select **DesktopDirectory**. 

![get special folder exercise part one](..\media\get-special-folder-exercise-part-one.png)

Next, use the **Move Mouse** Action. Move the mouse to the Start icon, and press **Ctrl+Shift**. This will enter the coordinates of the start icon into the two coordinate fields under **Move Mouse to**. Set **Move Mouse From Previous Position** to **With Animation (Fast Speed)**.

![move mouse exercise part two](..\media\move-mouse-exercise-part-two.png)

Next, add the **Send Mouse Click** Action. Leave the **Mouse Event to Send** option on its default setting, Left Click.
 
![send mouse click exercise part three](..\media\send-mouse-click-exercise-part-three.png)

Add the **Send Keys** Action. In **Text to Send** enter **This PC{Enter}{Apps}{R}** and set **Delay Between Keystrokes** to **500 milliseconds**.

![send keys exercise part four](..\media\send-keys-exercise-part-four.png)

* This PC will type the text “This PC” into the Start Menu search
* {Enter} will simulate pressing the enter key to open This PC
* {Apps} will open the context menu in the This PC window
* {R} will select and open Properties

![take screenshot exercise part five](..\media\take-screenshot-exercise-part-five.png)

Lastly, add the **Take Screenshot** Action. Set **Capture** to **Foreground Window**, **Save Screenshot to** to **File**, **Image File** to **%SpecialFolder%\screen.jpg** and **Image Format** to **Jpg**.
 
Running the process will result in the screen.jpg file appearing on the current user’s Desktop.