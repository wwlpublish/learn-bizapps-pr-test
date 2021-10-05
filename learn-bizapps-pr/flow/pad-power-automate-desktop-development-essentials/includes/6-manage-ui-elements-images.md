Automating tasks usually requires interaction with third-party software, application windows, web pages, or other on-screen elements. In order to identify such elements, information about them is stored within a flow – Controls, which are used to interact with UI elements and web pages, and Images, which can be used in image recognition-related actions.

Both are located on the top-right of the designer window; selecting one of the appropriate tabs opens the respective list of elements:

![Screenshot of the U I elements and images tabs.](..\media\ui-elements-images.png)

## UI elements

UI elements are used to identify windows and their contents.

For example, to interact with the UI of Excel in order to change a cell’s color, we will have to extract that button’s UI element.

In the UI elements tab, selecting **Add UI element** launches the tool Power Automate for desktop uses to extract UI elements. Navigating to the Excel interface, elements are automatically highlighted when the cursor hovers over them:

![Screenshot of a group of Font controls in Excel highlighted by U I spy.](..\media\controls-ui-spy.png)

Clicking while pressing down the Ctrl button will capture the highlighted element:

![Screenshot of the Tracking session window with the Bold button selected.](..\media\tracking-session-window.png)

When all the required elements are captured, press **Done**. The captured elements will be visible in the UI elements pane:

![Screenshot of the U I elements pane with the Bold button open.](..\media\ui-elements-pane.png)

Adding a **Press Button in Window** action, we are prompted to select a UI element that identifies the button to press:

![Screenshot of the Press button in window action properties dialog.](..\media\press-button-in-window-action-properties.png)

After the appropriate UI element is selected, the action is now configured to press the button:

![Screenshot of the Press button in window action properties filled in.](..\media\press-button-in-window-action-properties-continued.png)

## Images

Like UI elements, images can be added to the flow, and used in related actions.

When clicking the **Capture new Image** button, the cursor changes, enabling users to select an image to extract in detail:

![Screenshot of the capture image cursor with crosshairs.](..\media\capture-image.png)

After the image is given a name, it can be used in image recognition Actions, like **Move Mouse to Image**:

![Screenshot of the Move mouse to image action properties dialog.](..\media\move-mouse-to-image-action-properties.png)

![Screenshot of the action properties control repository pop out with the paste icon selected.](..\media\action-properties-image.png)

![Screenshot of the move mouse to image action properties dialog with the paste icon image added.](..\media\move-mouse-to-image-action-properties-continued.png)

Thus configured, the action will search for a matching image on the display, then move the mouse cursor to it.
