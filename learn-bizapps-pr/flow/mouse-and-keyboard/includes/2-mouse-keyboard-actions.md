The **Get Mouse Position** Action is used to locate the current position of the cursor. The position can be set to be measured from either the top-left corner of the screen or the top-left corner of the foreground window. The cursor's coordinates are measured as width and height (x and y) and stored into two separate variables. 

![Get Mouse Position action properties](..\media\Get-Mouse-Position-action-properties.png)

The **Move Mouse** Action requires some additional input beyond the target coordinates. The coordinates can be calculated from the top left of the screen, the currently active window, or the mouse's current position. The mouse can be set to move to the new position instantly, where the mouse appears to jump from one position to another or use animation to simulate a user's movement of the mouse. The speed of the animation can also be adjusted to be slow, natural, or fast.

![Move Mouse action properties](..\media\Move-Mouse-action-properties.png)

Use the **Move Mouse to Image** Action to more dynamically direct the cursor to an onscreen position as this Action targets an image wherever it may appear on the screen as opposed to a set of fixed coordinates. An image must be selected from the images repository to specify what the Action should look for on the screen. If there are no images in the repository, they can be captured by clicking on the Capture Image button in the Images Repository pop-out.

![Move Mouse to Image properties popout](..\media\Move-Mouse-to-Image-properties-popout.png)

The Action allows to add multiple images in which case it will move to the first image found. Specify whether the Action should search for the image on the entire screen or only on the foreground window (1). The search area can be further narrowed down to include only a subregion of the screen or window (2). Click Select Subregion (3) to capture a subregion of the screen or Active Window in a similar way to capturing an image. The subregion will be recorded using four coordinates that specify a rectangular area on the screen or window. Use the graphical tool (4) to determine which part of the image the cursor should move to; center, left, middle, upper right etc. Use the x and y offset fields (5) to further modify this selection. Use the tolerance field (6) to allow for some difference between the captured image and the actual image the Action will search for. The higher the tolerance, the more likely the Action will be to identify the offscreen image, even if it differs from the one captured. The tolerance is measured on a scale of 0 to 128. As with the Move Mouse Action, it is possible to determine the mouse movement's animation type and speed (7). Occurrence (8) determines which occurrence of the image the Action should move the mouse to. Optionally, the coordinates of the image found can be stored in two separate variables (9).

![Move Mouse to Image action properties](..\media\Move-Mouse-to-Image-action-properties.png)

In the **Advanced** tab, the Action can be set to wait for an image to appear on-screen as well as a duration for which it will wait before it fails. Also, a left mouse click can be sent after moving the cursor to the image. The click can occur immediately upon the cursor moving to the image or it can be delayed by the specified number of seconds.
 
![Move Mouse to Image properties Advanced tab](..\media\Move-Mouse-to-Image-properties-Advanced-tab.png)

The **Move Mouse to Text on-Screen** Action requires that an OCR Engine has been created by the respective Action. OCR engines are responsible for identifying text on screen, even if the text has been stored as an image such as a .jpg or .pdf file. In the Action properties, set the OCR Engine variable created by the OCR Action (1). Text to Find (2) is a required input and a regular expression can also be entered. In case the text appears more than once on the screen, the occurrence of the text the Action should capture can be specified (3). As with the Move Mouse to Image Action, specify if the Action should search for the text on the entire screen, or only in the foreground window (4). Additionally, a subregion relative to an image can be specified (5). the image must be selected from the images repository (6), the tolerance can be set (7), and coordinates must be provided to specify the subregion (8). As with the previous Actions, determine the animation type and speed of the mouse movement (9). The Action creates four output variables; two store the coordinates of the text found on screen (10), while another two hold the dimensions of the area occupied by the text (11).

![Move Mouse to Text on Screen action properties](..\media\Move-Mouse-to-Text-on-Screen-action-properties.png)

In the **Advanced** tab, determine whether the Action should wait for an image to appear onscreen and for how long to wait before it fails. Also, select whether to send a left mouse click after moving the cursor to the image. The click can occur immediately upon the cursor moving to the image or it can be delayed by a number of seconds. Use the graphical tool and the x and y offset fields to determine whether the cursor should move to the center or another area of the text. 
 

![Move Mouse to Text on Screen properties Advanced tab](..\media\Move-Mouse-to-Text-on-Screen-properties-Advanced-tab.png)

With the **Send Mouse Click** Action simulate using the physical mouse to send clicks or button presses. Choose whether the Action should wait a number of milliseconds before sending the click. Unless otherwise configured, the Action will send the mouse click at whatever position on screen the cursor happens to be when the process executes this Action. Check Move mouse before sending mouse event to show the options of the Move Mouse Action. A variable can be used for entering the coordinates. The coordinates can be set relative to the entire screen, the active window or the current mouse position. To enter the cursor's current position into the coordinates, press CTRL+SHIFT. As with all mouse Actions, determine the speed and animation type.
 
![Send Mouse Click action properties](..\media\Send-Mouse-Click-action-properties.png)

To simulate using the physical keyboard to enter text or other key commands use the **Send Keys** Action. Enter the text to send or enter it as a variable. For more specialized key commands, use the Insert Special Key buttons to insert special keys such as the arrow keys, Caps Lock or keys from the numeric keypad, and Insert Modifier to send keys such as Shift and Control. There is an option to set a delay between the keystrokes in milliseconds. 

![Send Keys action properties](..\media\Send-Keys-action-properties.png)

[!NOTE]
To send a key, rather than text, use curly brackets, and capitalize it.
for example: Entering {Control}({A}) in Text to Send will perform the Select All function, as it is bound to that shortcut.

The **Press/Release Key** Action allows us to combine mouse and keyboard actions to perform more advanced gestures, such as Control+click or Shift+click. Configure the action to simulate pressing and holding one or any combination of the keys Control, Alt, Shift and/or the Windows key.

![Press Release Key action properties](..\media\Press-Release-Key-action-properties.png)

[!WARNING]
The pressed key state will persist beyond the execution of the process. That is, the computer will behave as if the key is still pressed. Another Press/Release Key Action must be used to revert the key to its default state.

The **Set Key State** Action is used to enable or disable Caps Lock, Num Lock and Scroll Lock.

![Set Key State action properties](..\media\Set-Key-State-action-properties.png)

The **Block Input** Action is used to ignore mouse or keyboard input from the user during Process execution.

![Block Input action properties](..\media\Block-Input-action-properties.png)
 
[!WARNING]
To re-enable user input, add another Block Input Action to the Process, and set it to Unblock Input. For this to take effect, WinAutomation has to be run with Administrator rights.