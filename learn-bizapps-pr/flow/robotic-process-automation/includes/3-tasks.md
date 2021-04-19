Power Automate Desktop can both capture the steps performed by the user and edit the steps in desktop flows.

The user can record tasks with

- Desktop recorder: Records the steps on Windows native applications.
- Web recorder: Records steps in a browser for web applications.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate Desktop recorder buttons.](../media/3-recorder-buttons.png)](../media/3-recorder-buttons.png#lightbox)

## Desktop recorder

The Desktop recorder identifies and highlights objects in the application user interface such as buttons, menus, and fields. It then records the mouse clicks and keyboard entries against that object.

> [!div class="mx-imgBorder"]
> [![Screenshot of steps captured by the Desktop recorder.](../media/3-recorded-tasks.png)](../media/3-recorded-tasks.png#lightbox)

## Web recorder

The web records identifies what is clicked and entered into a web page. The process is similar and is tailored towards web applications.

## Editing steps and actions

Once steps have been recorded, you can edit to remove unnecessary actions and add further actions. You can also edit the objects selected in the application and add new UI objects.

> [!div class="mx-imgBorder"]
> [![Screenshot of user interface actions in Power Automate Desktop.](../media/3-user-interface-actions.png)](../media/3-user-interface-actions.png#lightbox)

Power Automate has a wide range of capabilities and can perform many actions including:

- Running SQL queries against a SQL Server database.
- Manipulate the contents of an Excel worksheet.
- Process emails in Outlook.
- Run PowerShell scripts on the local computer
- Copy to and from the clipboard
- Access Active Directory objects
- Access cloud services

Power Automate Desktop is powerful with many possible actions. The solution architect should decide the most appropriate technology for performing actions. For example, should a SQL query be performed using a desktop flow, a cloud flow, or by an Azure function.

## Variables

Flow variables allow information to change in every run of a desktop flow. If you're using a desktop flow for any type of data entry, you'll need flow variables to define the fields that you need to enter. The solution architect should encourage the use of flow variables and ensure that there's a naming convention for variables.

Input variables are information that you pass to a desktop flow. Output variables are outcomes that the desktop flow passed back after the desktop flow has run. Power Automate Desktop provides the ability to receive input values from cloud flows and return values back to the cloud flow by using output variables. As a result, your automations can be seamlessly integrated. The solution architect should ensure the input and output variables are specified at the design stage, as it is likely that cloud and desktop flows will be built by different makers.

If input variables are different for each environment, then you should define Environment Variables for input variables in the flows.
