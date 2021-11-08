When you choose to create or edit a flow, Power Automate for desktop launches the flow designer.

The flow designer is the platform's primary development tool with which you develop flows that deploy actions. The flow designer consists of seven components that enable you to handle every aspect of the development process.

The actual development happens in the workspace, which is the main component of the window. By using the workspace, you can develop flows that run sequentially or alter the run path by using loops, conditionals, and flow control actions.

To deploy or search for an action, you can use the Actions pane located on the left side of the designer. All actions are categorized into groups based on their functionality.

![Screenshot of the Actions pane and the workspace.](..\media\flow-designer-workspace-actions-pane.png)

While automating business procedures, you might create complex flows that contain numerous actions. Power Automate for desktop allows you to simplify these flows and make testing easier through subflows.

Subflows are groups of actions that you can reference as a group within other subflows. Every flow contains the main subflow that runs automatically when the flow starts.

To create a new subflow, select the plus (**+**) icon on the **Subflows** tab above the workspace and then enter the desired name.

![Screenshot of Power Automate for desktop with the subflows dialog box highlighted.](..\media\flow-designer-subflows.png)

Every action that is used in a flow accepts some input parameters and stores its results in new variables. The platform displays all produced variables in the Variables pane, where you can search for variables, rename them, find their usages, and filter them by type.

Except for local variables that are used only in the current flow, you can create input/output variables to pass data to and from Power Automate for desktop. Input and output variables empower you to combine multiple Power Automate products and create a powerful and robust automation solution.

![Screenshot of the Variables pane in the flow designer.](..\media\flow-designer-variables-pane.png)

In scenarios where you use the UI and web automation capabilities of Power Automate for desktop, you can use the **UI elements** tab to manage the existing UI elements or create new ones. All UI elements that your flow accesses, such as buttons and check boxes, are stored on this tab.

![Screenshot of the UI elements pane in the flow designer.](..\media\flow-designer-ui-elements-pane.png)

The last main component of the flow designer is the **Images** tab. This tab stores all images that are used in the deployed actions, allowing you to access and manage them effortlessly.

![Screenshot of the Images tab in the flow designer.](..\media\flow-designer-images-pane.png)

During the development or implementation of the flow, you might encounter different types of errors. When an error happens, the platform displays the **Errors** pane and provides you with all available information to resolve it. You can use this feature to debug your flows and identify existing inconsistencies.

![Screenshot of the Errors pane in the flow designer.](..\media\flow-designer-errors-pane.png)
