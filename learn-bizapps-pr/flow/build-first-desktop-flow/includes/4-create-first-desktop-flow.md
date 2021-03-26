Navigate to [Power Automate](https://flow.microsoft.com/?azure-portal=true). Ensure that you are signed in and in the appropriate environment. Under **My Flows**, select **Desktop flows** and **Create a desktop flow**.

> [!div class="mx-imgBorder"]
> [![Screenshot of My flow, desktop flows with Create a desktop flow button.](../media/desktop-begin.png)](../media/desktop-begin.png#lightbox)

Select **Launch app** and open Power Automate Desktop from the subsequent dialog box. The desktop app will open in the designer with a new flew named "Untitled", which you can change later.

Desktop flows are created to mimic the actions of a user when performing steps in a process. You have to train the flow by adding those actions.

To add actions to your flow, you simply need to select the desired action and drag it to the main canvas. Under the **System** drop-down on the Actions Pane, select and drag **Run Application**. We will use this to open our invoicing application.

> [!div class="mx-imgBorder"]
> [![Screenshot of Run application feature under System actions.](../media/run-application.png)](../media/run-application.png#lightbox)

In the following dialog box, you need to specify the path to the application. You can do so by inputting the location manually but clicking the icon on the right allows you to select it from a file explorer. You can search in the file explorer if you do not know the exact location of your application.

Leave the remaining fields as is and press **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Run application parameters with path higlighted and Save button.](../media/save-run-application.png)](../media/save-run-application.png#lightbox)

Now that you have told Power Automate to open the application, we need to explain all the actions that come next. Earlier we chose from the actions on the action pane, but there is an even easier way to communicate actions that need to be performed, by recording your desktop. Jump over to the next unit for instructions on recording your desktop.