# Controls and Images Repositories
Automating tasks usually requires interaction with third party software, application windows, web pages, or other on-screen elements. In order to identify such elements, information about them is stored in repositories within a Process – the Controls Repository contains Controls, which are used to interact with UI elements and web pages, and the Images Repository contains user-captured images which can be used in image recognition related Actions.

Both repositories are located in the bottom of the Designer window; selecting one of the appropriate tabs opens the respective Repository:

![images repository pane](..\media\images-repository-pane.png)
  
## Controls
Controls are used to identify windows and any elements they contain.

For example, to interact with the UI of Excel in order to change a cell’s color, we will have to extract that button’s control.

In the Controls Repository, selecting **Add Control** opens the UISpy, the tool WinAutomation uses to extract controls. Navigating to the Excel interface, elements are automatically highlighted when the cursor hover over them:

![controls uispy](..\media\controls-uispy.png)
 
Clicking while pressing down the Ctrl button will capture the highlighted control:

![controls repository pane](..\media\controls-repository-pane.png)
 
Adding a Press Button in Window Action, we are prompted to select a control which identifies the button to press:

![press button in window action properties](..\media\press-button-in-window-action-properties.png)

![action properties control repository popout](..\media\action-properties-control-repository-popout.png)
 
After the appropriate Control is selected, the Action is now configured to press the button:

![press button in window action properties continued](..\media\press-button-in-window-action-properties-continued.png)
 
## Image Controls
Like Controls, Images can be added in the Images Repository, and used in related Actions.

When clicking the **Capture Image** button, the cursor changes, enabling users to select an image to extract in detail:

![capture image](..\media\capture-image.png)
 
After the Image is given a name, it can be used in image recognition Actions, like Move Mouse to Image:
 
![move mouse to image action properties](..\media\move-mouse-to-image-action-properties.png)

![action properties control repository popout continued](..\media\action-properties-control-repository-popout-continued.png)

![move mouse to image action properties continued](..\media\move-mouse-to-image-action-properties-continued.png)
 
Thus configured, the Action will search for a matching image on the display, then move the mouse cursor to it.
 