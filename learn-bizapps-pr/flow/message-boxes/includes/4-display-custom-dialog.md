There are certain scenarios where interacting with a user requires a more customized approach; providing multiple inputs of different types simultaneously, displaying a form window with customized UI, and allowing users to explicitly influence the flow of a Process are all possible needs during attended automation.

The **Display Custom Dialog** Action allows the creation of a fully customizable input form to accommodate such needs. To demonstrate, we will build a Process, which handles the onboarding of a new employee from an IT perspective.

First, we add the **Display Custom Dialog** Action; the Custom Dialog Designer window opens automatically:
 
![custom dialog designer](..\media\custom-dialog-designer.png)

On the left, we have a preview of the custom window; on the right, we can find all the available elements that can be added to the form, split in categories.

We begin by adding a Title from the **Misc** category; simply click on the Title on the right, or drag and drop it into the form on the left:
 
![custom dialog designer misc](..\media\custom-dialog-designer-misc.png)

Click on the Title that was added to the form to edit it:
 
![custom dialog designer header popout](..\media\custom-dialog-designer-header-popout.png)

 
![custom dialog designer employee details](..\media\custom-dialog-designer-employee-details.png)

From the **Input** category, we add an **Input** element, and a **Password** element, and edit them accordingly:
 
![custom dialog designer input](..\media\custom-dialog-designer-input.png)

Next, we will add a drop-down list to enter the employee’s department:
 
![custom dialog designer combobox popout](..\media\custom-dialog-designer-combobox-popout.png)

We will also add a date picker to enter the hire date, as well as a checkbox to designate whether the employee requires a company-issued phone; we use the **Date** and **Checkbox** elements respectively:
 
![custom dialog designer radios checkboxes](..\media\custom-dialog-designer-radios-checkboxes.png)

To complete the form, we will add two buttons; one to add the employee in question to the system, and one to end the Process. For now, we will simply name the buttons accordingly, and customize their behavior in a later step:
 
![custom dialog designer buttons](..\media\custom-dialog-designer-buttons.png)

To actually add the employee information to our software tool, we create a function named **Add Employee**:
 
![add employee function workspace](..\media\add-employee-function-workspace.png)

These Actions make use of the Custom Dialog window’s input, using the ID of each element we added to the dialog:
 
![custom dialog designer date selector](..\media\custom-dialog-designer-date-selector.png)

 
![populate text field in window properties exercise](..\media\populate-text-field-in-window-properties-exercise.png)

Now, all that is left is to configure the buttons in the Custom Dialog so that they provide the functionality we designed.

Edit the **Display Custom Dialog** Action, select **Open Designer** to view the form, and click on the buttons to edit them.

We will now configure the **Add Employee** button to run the function we created for that purpose, and the **Close** button to close the dialog when pressed:
 
![custom dialog designer button group properties](..\media\custom-dialog-designer-button-group-properties.png)

Now the Process is ready to run. When running, the form we designed pops up:
 
![custom dialog final](..\media\custom-dialog-final.png)

Every time we enter an employee’s details and press the **Add Employee** button, the function we created launches the application and enters the employee’s details into the system.

Finally, when all employees have been added, we press **Close** to close the dialog.
 
 
 