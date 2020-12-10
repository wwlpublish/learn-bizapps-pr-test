When you choose to create or edit a flow, Power Automate Desktop launches the flow designer. 

The flow designer is the platform's primary development tool with which you develop flows deploying actions. It consists of seven components that enable you to handle every aspect of the development process.

The actual development happens in the workspace, which is the main component of the window. Using the workspace, you can develop flows that run sequentially or alter the execution path using loops, conditionals, and flow control actions.

To deploy or search for an action, you can use the actions pane located on the designer's left side. All the actions are categorized into groups based on their functionality. 

![The actions pane and the workspace.](..\media\flow-designer-workspace-actions-pane.png)

While automating business procedures, you might create complex flows that contain numerous actions. Power Automate Desktop allows you to simplify these flows and make testing easier through subflows. 

Subflows are groups of actions you can reference as a group within other subflows. Every flow contains the main subflow that runs automatically when the flow starts.

To create a new subflow, select the **+** icon in the subflows tab located above the workspace and enter the desired name.

![The subflows dialog.](..\media\flow-designer-subflows.png)

Every action used in a flow accepts some input parameters and stores its results in new variables. The platform displays all the produced variables in the variables pane. Through this pane, you can search for variables, rename them, find their usages, and filter them by type.

Except for local variables used only in the current flow, you can create input/output variables to pass data to and from Power Automate Desktop. Input and output variables empower you to combine multiple Power Automate products and create a powerful and robust automation solution. 

![The variables pane in the flow designer.](..\media\flow-designer-variables-pane.png)

In cases where you use the UI and web automation capabilities of the Power Automate Desktop, you can use the  UI elements tab to manage the existing UI elements or create new ones. All the UI elements that your flow accesses, such as buttons and checkboxes, are stored here.

![The ui elements pane in the flow designer.](..\media\flow-designer-ui-elements-pane.png)

The last main component of the flow designer is the images tab. This tab stores all the images used in the deployed actions, allowing you to access and manage them effortlessly. 

![The images pane in the flow designer.](..\media\flow-designer-images-pane.png)

During the development or the execution of the flow, you might encounter different kinds of errors. When an error happens, the platform displays the errors pane and provides you with all the available information to resolve it. You can use this feature to debug your flows and identify any existing inconsistencies. 

![The errors pane in the flow designer.](..\media\flow-designer-errors-pane.png)