## Mouse actions

**Get Mouse Position** locates the current position of the cursor. The position can be set to be measured from either the top-left corner of the screen or the top-left corner of the foreground window. The cursor's coordinates are measured as width and height (x and y) and stored into two separate variables. 

![Get mouse position action properties](..\media\mouse-position-action-properties.png)

**Move Mouse** requires the target coordinates and how fast to move the cursor. The coordinates can be calculated from the top left of the screen, the currently active window, or the mouse's current position. The mouse can be set to move to the new position instantly, where the mouse appears to jump from one position to another or use animation to simulate a user's movement of the mouse. The speed of the animation can also be adjusted to be slow, natural, or fast.

![Move mouse action properties](..\media\move-mouse-properties.png)

**Move Mouse to Image** sends the cursor to the onscreen position of an image wherever it appears on the screen. The target image must be selected from the images repository. If there are no images in the repository, they can be captured by clicking on the Capture Image button in the Images Repository.

![Move Mouse to Image properties popout](..\media\move-mouse-image-properties-popout.png)

You can use this action to add multiple images. When an action includes multiple images, it will move to the first image found. The callouts in the following illustration show how to configure multiple images. 
1. Specify whether the action should search for the image on the entire screen or only on the foreground window
1. The search area can be further narrowed down to include only a subregion of the screen or window
1. Click Select Subregion to capture a subregion of the screen or active window. The subregion will be recorded using four coordinates that specify a rectangular area on the screen or window. 
1. Use the graphical tool to determine which part of the image the cursor should move to; center, left, middle, upper right etc. 
1. Use the x and y offset fields to further modify this selection. 
1. Use the tolerance field to allow for some difference between the captured image and the actual image the action will search for. The higher the tolerance, the more likely the action will be to identify the offscreen image, even if it differs from the one captured. The tolerance is measured on a scale of 0 to 128. 
1. Determine the mouse movement's animation type and speed. 
1. Occurrence determines which occurrence of the image the action should move the mouse to. 
1. Optionally, the coordinates of the image found can be stored in two separate variables

   ![Move Mouse to Image action properties](..\media\move-mouse-image-action-properties.png)

In the **Advanced** tab, an action can be set to wait for an image to appear onscreen as well as a duration for the wait. Also, a left mouse click can be sent after moving the cursor to the image. The click can occur immediately after the cursor has been moved to the image or it can be delayed by the specified number of seconds.
 
![Move Mouse to Image properties Advanced tab](..\media\move-mouse-image-properties-advanced-tab.png)

**Move Mouse to Text onscreen** moves the mouse to specific text onscreen, even if the text has been stored as an image such as a .jpg or .pdf file. For this action, you must specify an optical character recognition (OCR) engine in the OCR action. The callouts in the following illustration show how to configure this action. 

1. In the action properties, set the OCR engine variable created by the OCR action 
1. Text to Find is a required input and a regular expression can also be entered
1. In case the text appears more than once on the screen, the occurrence of the text the action should capture can be specified 
1. Specify whether the action should search for the text on the entire screen, or only in the foreground window 
1. Specify a subregion relative to an image can be specified 
1. The image must be selected from the images repository 
1. The tolerance can be set 
1. Coordinates must be provided to specify the subregion
1. As with the previous actions, determine the animation type and speed of the mouse movement 
1. The action creates four output variables; two that store the coordinates of the text found on screen 
1. The other two hold the dimensions of the area occupied by the text

   ![Move Mouse to Text on Screen action properties](..\media\move-mouse-text-screen-action-properties.png)

In the **Advanced** tab, determine whether the action should wait for an image to appear onscreen and for how long to wait before it fails. Also, select whether to send a left mouse click after moving the cursor to the image. The click can occur immediately upon the cursor moving to the image or it can be delayed by a number of seconds. Use the graphical tool and the x and y offset fields to determine whether the cursor should move to the center or another area of the text. 
 

![Move Mouse to Text on Screen properties Advanced tab](..\media\move-mouse-text-screen-properties-Advanced-tab.png)

**Send Mouse Click** simulates using the physical mouse to send clicks or button presses. Choose whether the action should wait a number of milliseconds before sending the click. Unless otherwise configured, the action will send the mouse click at whatever position on screen the cursor happens to be when the process runs this action. Check Move mouse before sending mouse event to show the options of the Move Mouse action. A variable can be used for entering the coordinates. The coordinates can be set relative to the entire screen, the active window or the current mouse position. To enter the cursor's current position into the coordinates, press CTRL+SHIFT. As with all mouse actions, determine the speed and animation type.
 
![Send Mouse Click action properties](..\media\send-mouse-click-action.png)

## Keyboard actions

**Send Keys** simulates using the physical keyboard to enter text or other key commands. Enter the text to send or enter it as a variable. For more specialized key commands, use the Insert Special Key buttons to insert special keys such as the arrow keys, Caps Lock or keys from the numeric keypad, and Insert Modifier to send keys such as Shift and Control. There is an option to set a delay between the keystrokes in milliseconds. 

![Send Keys action properties](..\media\send-keys-action.png)

> [!NOTE]
> To send a key, rather than text, use curly brackets, and capitalize it. For example: Entering {Control}({A}) in Text to Send will perform the Select All function.

**Press/Release Key** enables you to combine mouse and keyboard actions to perform more advanced gestures, such as Control+click or Shift+click. Configure the action to simulate pressing and holding one or any combination of the keys Control, Alt, Shift and/or the Windows key.

![Press Release Key action properties](..\media\press-release-key-properties.png)

> [!WARNING]
> The pressed key state will persist after the process has finished. That is, the computer will behave as if the key is still pressed. You must use another Press/Release Key action must be used to revert the key to its default state.

**Set Key State** is used to enable or disable Caps Lock, Num Lock and Scroll Lock.

![Set Key State action properties](..\media\set-key-state-action.png)

**Block Input** is used to ignore mouse or keyboard input from the user while the process is running.

![Block Input action properties](..\media\block-input-action.png)
 
> [!WARNING]
> To re-enable user input, add another Block Input action to the process, and set it to Unblock Input. For this to take effect, WinAutomation has to be run with Administrator rights.
