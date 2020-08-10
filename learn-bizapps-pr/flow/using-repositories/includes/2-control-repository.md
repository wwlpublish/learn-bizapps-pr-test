The **Controls Repository** stores all the controls used in UI and web automation actions, such as buttons and checkboxes. Upon creating a new process, the **C0ntrols Repository** will be empty. To create a new  control, you can use one of the following methods.

![The Controls Repository in the Process Designer.](..\media\process-designer-controls-repository.png)

The first way to create a new control is through the **Add Control** button in the **Controls Repository**. 

1.	Click the **Add Control** button.

    ![The Add Control button in the Controls Repository.](..\media\controls-repository-add-control-button.png)

1.	Use the **Live Helpers** (orange boxes) and select the desired element.

    ![An example of the Live Helpers in the Microsoft Word.](..\media\live-helpers-word.png)

1.	Press **Ctrl + Left Click** while the desired element is selected to create the control. 

    ![The created control in the Controls Repository.](..\media\created-control-controls-repository.png)

    Although the procedure is the same for web and UI/Windows controls, the created selectors are different. Web controls consist of CSS selectors, while the UI/Windows controls consist of UI selectors. 

The second method to create a control is through an action. 

1.	Add to the **Workspace** an action that requires a control, such as the **Click Link on Web Page** action. 

    ![The Click Link on Web Page action in the Workspace.](..\media\click-link-on-web-page-action-workspace.png)

1.	Open the action's properties and click on the **Select Control From Repository** button. 

    ![The Select Control From Repository button in the Link on Web Page action's properties.](..\media\click-link-on-web-page-action-select-control.png)

1.	Click on the **Add Control** button to create a new control. 

    ![The Add Control option in the Link on Web Page action's properties.](..\media\click-link-on-web-page-action-add-control.png)

1.	Use the **Live Helpers** (orange boxes) and select the desired element.

    ![An example of the Live Helpers in the Microsoft Word.](..\media\live-helpers-word.png)

1.	Press **Ctrl + Left Click** while the desired element is selected to create the control. 

    ![The created control in the Controls Repository.](..\media\created-control-controls-repository.png)

[!Note]
If you want to create a web control on Microsoft Edge, Google Chrome, or Mozilla Firefox, you need to install the respective extension.

In some cases, you may need to create more than one selector to capture an element. WinAutomation allows you to create multiple selectors for one control and prioritize them. If one selector fails, the next one will be used. 

To create multiple selectors for a control, double-click on the desired control and press the **Add Selector** button. If you want to create a selector with recapture, click on the arrow next to the **Add Selector** button and select the respective option. 

![The Add Selector button in the Control's pop-up window.](..\media\control-window-add-selector-button.png)

Lastly, WinAutomation allows you to develop CSS selectors manually. This feature can be useful in web applications in which particular actions cannot be captured using the **Web Helpers**.

To develop a new selector manually:

1.	Click on the arrow next to the **Add Control** button in the **Controls Repository** and select **Add Empty Root Control**.

    ![The Add Empty Root Control in the Controls Repository.](..\media\add-empty-root-control-controls-repository.png)

1.	Double-click on the created control.

    ![The created control in the Controls Repository.](..\media\created-empty-control-controls-repository.png)

1.	Click on the **Add Selector** button.

    ![The Add Selector button in the Control's pop-up window.](..\media\empty-control-window-add-selector-button.png)

1.	Develop your selector. 

    ![The Selector Builder window.](..\media\selector-builder-window.png)