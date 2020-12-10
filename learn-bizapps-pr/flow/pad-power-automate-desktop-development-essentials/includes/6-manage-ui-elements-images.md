Automating tasks usually requires interaction with third-party software, application windows, web pages, or other on-screen elements. In order to identify such elements, information about them is stored within a flow – Controls, which are used to interact with UI elements and web pages, and Images, which can be used in image recognition-related actions.

Both are located on the top-right of the designer window; selecting one of the appropriate tabs opens the respective list of elements:

![UI elements and images](..\media\ui-elements-images.png)

## UI elements
UI elements are used to identify windows and their contents.

For example, to interact with the UI of Excel in order to change a cell’s color, we will have to extract that button’s UI element.

In the UI elements tab, selecting **Add UI element** launches the tool Power Automate Desktop uses to extract UI elements. Navigating to the Excel interface, elements are automatically highlighted when the cursor hovers over them:

![controls uispy](..\media\controls-uispy.png)
 
Clicking while pressing down the Ctrl button will capture the highlighted element:

![tracking session window](..\media\tracking-session-window.png)

When all the required elements are captured, press **Done**. The captured elements will be visible in the UI elements pane:

![ui elements pane](..\media\ui-elements-pane.png)
 
Adding a **Press Button in Window** action, we are prompted to select a UI element that identifies the button to press:

![press button in window action properties](..\media\press-button-in-window-action-properties.png)
 
After the appropriate UI element is selected, the action is now configured to press the button:

![press button in window action properties continued](..\media\press-button-in-window-action-properties-continued.png)
 
## Images
Like UI elements, images can be added to the flow, and used in related actions.

When clicking the **Capture new Image** button, the cursor changes, enabling users to select an image to extract in detail:

![capture image](..\media\capture-image.png)
 
After the image is given a name, it can be used in image recognition Actions, like **Move Mouse to Image**:
 
![move mouse to image action properties](..\media\move-mouse-to-image-action-properties.png)

![action properties control repository popout continued](..\media\action-properties-image.png)

![move mouse to image action properties continued](..\media\move-mouse-to-image-action-properties-continued.png)
 
Thus configured, the action will search for a matching image on the display, then move the mouse cursor to it.