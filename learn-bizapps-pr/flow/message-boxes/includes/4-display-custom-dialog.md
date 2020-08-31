There are certain scenarios where interacting with a user requires a more customized approach; providing multiple inputs of different types simultaneously, displaying a form window with customized UI, and allowing users to explicitly influence the flow of a process are all possible needs during attended automation.

The Display Custom Dialog action allows the creation of a fully customizable input form to accommodate such needs. To demonstrate, we will build a process, which handles the onboarding of a new employee from an IT perspective.

1. Add the **Display Custom Dialog** action; the Custom Dialog Designer window opens automatically.
 
    ![custom dialog designer](..\media\custom-dialog-designer.png)

1. On the left, we have a preview of the custom window; on the right, we can find all the available elements that can be added to the form, split in categories.

1. Add a Title from the **Misc** category; simply click on the Title on the right, or drag and drop it into the form on the left:
 
    ![custom dialog designer misc](..\media\custom-dialog-designer-misc.png)

1. Select the title that was added to the form to edit it.

    ![custom dialog designer header popout](..\media\custom-dialog-designer-header-pop-out.png)
 
    ![custom dialog designer employee details](..\media\custom-dialog-designer-employee-details.png)

1. From the **Input** category, add an **Input** element, a **Password** element, and edit them as shown in the illustration.
 
    ![custom dialog designer input](..\media\custom-dialog-designer-input.png)

1. Add a drop-down list to enter the employee’s department.

    ![custom dialog designer combobox popout](..\media\custom-dialog-designer-combo-box-pop-out.png)

1. Add a date picker to enter the hire date, as well as a checkbox to designate whether the employee requires a company-issued phone; we use the **Date** and **Checkbox** elements respectively. 
 
    ![custom dialog designer radios checkboxes](..\media\custom-dialog-designer-radios-check-boxes.png)

1. Add two buttons; one to add the employee in question to the system, and one to end the process. For now, we will simply name the buttons accordingly, and customize their behavior in a later step. 
 
    ![custom dialog designer buttons](..\media\custom-dialog-designer-buttons.png)

1. Add the employee information to our software tool, we create a function named **Add Employee**. 
 
    ![add employee function workspace](..\media\add-employee-function-workspace.png)

1. Add Actions that make use of the Custom Dialog window’s input, using the ID of each element we added to the dialog.
 
    ![custom dialog designer date selector](..\media\custom-dialog-designer-date-selector.png)    
            
    
    ![populate text field in window properties exercise](..\media\populate-text-field-in-window-properties-exercise.png)

1. Configure the buttons in the Custom Dialog so that they provide the functionality we designed.

1. Edit the **Display Custom Dialog** action, select **Open Designer** to view the form, and click on the buttons to edit them.

1. Configure the **Add Employee** button to run the function we created for that purpose, and the **Close** button to close the dialog when pressed.
 
    ![custom dialog designer button group properties](..\media\custom-dialog-designer-button-group-properties.png)

1. Now the process is ready to run. When running, the form we designed pops up:
 
    ![custom dialog final](..\media\custom-dialog-final.png)

1. Every time we enter an employee’s details and press the **Add Employee** button, the function we created launches the application and enters the employee’s details into the system.

1. When all employees have been added, we press **Close** to close the dialog.
