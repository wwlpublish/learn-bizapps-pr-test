There are some scenarios where interacting with users requires a more customized approach. For example, the user may need to provide multiple inputs simultaneously, display a form window with custom UI, or influence the flow of a process.

The **Display Custom Dialog** action enables users to create a fully customizable input form to accommodate such needs. 

To become familiar with this functionality, develop a process that handles the onboarding of a new employee from an IT perspective.

1. Create a new process and add the **Display Custom Dialog** action to the workspace. When the action is deployed, the **Custom Dialog Designer** window opens automatically.

    On the left side of the window, there's a preview of the custom form. Next to the preview, the dialog displays all the available elements that can be added to the form.

    ![Screenshot of the Custom Dialog Designer with Drag & Drop Controls.](..\media\custom-dialog-designer.png)

1. Drag and drop a **Title** element from the **Misc** category into the form preview on the left.

    ![Screenshot of the Custom Dialog Designer on the Misc tab.](..\media\custom-dialog-designer-misc.png)

1. Select the added title and rename it to **Employee Details**.

    ![Screenshot of the Custom Dialog Designer showing the header pop-out.](..\media\custom-dialog-designer-header-pop-out.png)

    ![Screenshot of the Custom Dialog Designer with the title set to Employee Details.](..\media\custom-dialog-designer-employee-details.png)

1. Add an **Input** and a **Password** element to the form and edit them as shown in the following illustration.

    ![Screenshot of the Custom Dialog Designer on the Input tab.](..\media\custom-dialog-designer-input.png)

1. Add a drop-down list that enables users to select the department of the new employee.

    ![Screenshot of the Custom Dialog Designer showing the combobox pop-out.](..\media\custom-dialog-designer-combo-box-pop-out.png)

1. Add a date picker to make users select a hire date. Additionally, add a checkbox to indicate whether the employee requires a company-issued phone.

    ![Screenshot of the Custom Dialog Designer on the Radios and Checkboxes tab.](..\media\custom-dialog-designer-radios-check-boxes.png)

1. Add two buttons; one to add the employee to the system and one to end the process. The behavior of these buttons will be implemented in a later step.

    ![Screenshot of the Custom Dialog Designer on the Buttons tab.](..\media\custom-dialog-designer-buttons.png)

1. Create a new function named **Add Employee** that will populate the employee's information to the employee management system.

    The example uses a hypothetical employee management system tool. In your implementation, modify the form-filling steps to work with the currently available software.

    > [!NOTE]
    > More information about the form-filling actions and how to use controls can be found in [Use WinAutomation to interact with windows and applications](../../ui-automation/index.yml).

    ![Screenshot of the add employee function workspace.](..\media\add-employee-function-workspace.png)

1. To populate the information of a form cell into the software, use the **%CustomDialogResults["ElementID"]%** notation. 

    ![Screenshot of the Custom Dialog Designer showing the date selector pop-out with ID/Name set to HireDate highlighted.](..\media\custom-dialog-designer-date-selector.png)

    For example, to populate the hire date, use the **%CustomDialogResults["HireDate"]%** expression in the **Text to Fill In** field of the **Populate Text Field in Window** action.

    ![Screenshot of Properties of 'Populate Text Field in Window' action dialog.](..\media\populate-text-field-in-window-properties-exercise.png)

1. Edit the **Display Custom Dialog** action, select **Open Designer** to view the form, and select the buttons to edit them.

1. Configure the **Add Employee** button to run the function that was created for that purpose, and the **Close** button to close the dialog when pressed.

    ![Screenshot of the Custom Dialog Designer showing the Button Group pop-out.](..\media\custom-dialog-designer-button-group-properties.png)

1. Now the process is ready to run. When running, the custom form pops up:

    ![Screenshot of the completed custom Employee Details dialog.](..\media\custom-dialog-final.png)

1. Every time users enter an employee’s details and press the **Add Employee** button, the function launches the application and enters the employee’s details into the system.

1. When all employees have been added, press **Close** to close the dialog.
