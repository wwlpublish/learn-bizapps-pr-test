In this exercise scenario, you have created and published the Bottle Management application for your
organization CoHo Winery.

You have received the following feedback:

- Users receive a warning whenever they start the application.

- An error if users try to submit volume that includes decimal numbers.

 > [!NOTE]
 > To successfully complete all steps in this lab, you will need
to have access to two users in your lab environment or work in pairs
with a classmate. If you don't have another user available, complete
the steps that you are able to and then read and review the paired activities.

## Tasks

In this exercise, you will complete the following tasks:

1. Debug by using the Monitor tool.

2. Resolve the issues.

3. Test your solutions.

4. Publish changes.

## Objectives

The objectives for this exercise are to show you how to:

- Use the Monitor tool.

- Debug issues with your canvas application.

- Invite other users to debug sessions.

- Enable debugging for a published application.

- Debug a published application with a connected user.

## Exercise 1: Import a solution and run a flow

In this exercise, you will import a solution into your environment and
then run a Power Automate cloud flow that will create sample date for you.

### Task 1: Import a solution

In this task, you will import a solution into your environment.

1. You will need to download the [zip file](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-apps/troubleshoot-monitor/CohoVineyardMonitorModule_1_0_0_1.zip) to complete this exercise. Select download once the link opens.

1. Go to [Power Apps maker portal](https://make.powerapps.com/)
    and select the environment that you want to use for this lab.

1. Select **Solutions > Import**.

    :::image type="content" source="../media/import.png" alt-text="![Screenshot of the Import button in the Solutions area.]":::

1. Select **Browse**.

1. Select the
    CohoVineyardMonitorModule_1\_0_0\_1.zip solution, and then select
    **Open**.

1. Select **Next**.

1. Select **Import** and wait for the solution importing process to complete.
   Follow the step to establish the connection to Dataverse, if prompted.

1. Do not navigate away from this page.

### Task 2: Run a flow

In this task, you will run a Power Automate cloud flow that will add
sample data to your environment.

1. On the **Solutions** tab, select **Import**.

1. Select to open the solution that you imported in **Task 1: Import a solution**.

    :::image type="content" source="../media/coho-solutions.png" alt-text="![Screenshot of Coho Vineyard - Monitor Module solution.]":::

1. Locate and select to open the **Generate Test Data** cloud flow. If
    this cloud flow is the first for this environment, you might need to
    accept terms and then select to open it again.
    
    :::image type="content" source="../media/coho-generate-test-data.png" alt-text="![Screenshot of Generate Test Data display name and Cloud flow type highlighted.]":::

1. Select **Run**.

1. Select **Run flow**.

1. Select **Done** and then wait for the flow run to complete. This process can take 3 to 6 minutes.

    :::image type="content" source="../media/succeeded.png" alt-text="![Screenshot of succeeded flow run]":::

1. Close the Power Automate browser window or tab.

1. Select **Done** on the pop-up window.

1. Select **Apps**.

1. Select to launch the **CoHo Bottle Management** application.

    :::image type="content" source="../media/coho-app.png" alt-text="![Screenshot of the CoHo Bottle Management app highlighted on the Apps tab.]":::

   The application should load, and the test data that was created by the cloud flow should display.
   
    :::image type="content" source="../media/canvas-rows.png" alt-text="![Screenshot of CoHo Bottle Management app with rows of data]":::

1. Close the application browser window or tab.

## Exercise 2: Debug and fix a load issue

In this exercise, you will monitor the application to determine what has
caused the failure when the application loads, and then you will fix it.

### Task 1: Debug

In this task, you will debug the application by using the Monitor tool.

1. Go to [Power Apps maker portal](https://make.powerapps.com/)
    and select the environment that you are using for this lab.

1. Select **Solutions** and then select to open the **CoHo Vineyard - Monitor Module** solution.

1. Locate and select to open the **CoHo Bottle Management** canvas application.

   The application should open in the app designer.

1. Select the **Advanced tools** tab and then select **Open monitor**.

    :::image type="content" source="../media/open-monitor.png" alt-text="![Screenshot of the Open monitor option highlighted on the Advanced tools tab.]":::

   Monitor should open in a new browser tab or window and connect to your application.

1. Do not close the Monitor browser. Return to the app designer and then select the **Preview** button.

    :::image type="content" source="../media/powerapps-preview.png" alt-text="![Screenshot of the Preview button in the browser.]":::

1. The application should open in preview mode. Select the **Refresh** button.

    :::image type="content" source="../media/powerapps-refresh.png" alt-text="![Screenshot of the Refresh button.]":::

1. Return to Monitor to review the events. Select the warning event of delegation category that appears.

    :::image type="content" source="../media/warning-event.png" alt-text="![Screenshot of the event log row.]":::

1. The properties pane should open, where you can select the **Details** tab, and then expand the **formulaData** node.

    :::image type="content" source="../media/formula-data.png" alt-text="![Screenshot of the Details tab in Monitor and the Expand button highlighted.]":::

1. Review the **formulaData** node and then expand the **data** node.

1. Scroll down and read the issue.

 :::image type="content" source="../media/issue-message.png" alt-text="![Screenshot of the issue message.]":::

1. Select **Download**. You can download Monitor event logs and upload them later or share them with team members.

1. Save the Monitor event log on your machine.

1. Select **Clear data**.

1. Close the Monitor browser window or tab.

1. Return to the designer and close the preview.

    :::image type="content" source="../media/close-preview.png" alt-text="![Screenshot of the designer, showing the preview being closed.]":::

1. Do not navigate away from this page.

### Task 2: Fix the formula

In this task, you will fix the formula.

1. Select **Tree view** and then select the **BottleGallery** option.

    :::image type="content" source="../media/tree-view.png" alt-text="![Screenshot of the BottleGallery option selected in Tree view.]":::

1. Select **items** from the formula bar. The warning also shows in the bar.

    :::image type="content" source="../media/warning-message.png" alt-text="![Screenshot of the formula bar showing the warning message.]":::

    > [!NOTE]
    > The warning might also display as shown in the following screenshot.

    :::image type="content" source="../media/warning-display.png" alt-text="![Screenshot of an alternate display for the delegation warning.]":::

1. Replace the current formula with the following formula.

    ```powerappsfl
        Filter(Bottles \'Modified On\' \> DateAdd(Today(), - 7, Days))     
    ```

   The warning should go away.

1. Select **Advanced tools** located on the left navigation pane and **Open monitor**.

1. Leave the Monitor tool running.

1. Return to the app designer and select **Preview**.

1. Select the **Refresh** button.

   The warning should no longer display.

1. Select the **Clear data** button.

1. Select **Upload**.

1. Select the file that you previously downloaded and then select **Open**.

    :::image type="content" source="../media/powerapps-file.png" alt-text="![Screenshot of the Power Apps JSON file.]":::

   The file should upload, and previous event logs should display.
   
    :::image type="content" source="../media/earlier-event-log.png" alt-text="![Screenshot of previous event logs.]":::

1. Select **Clear data**.

1. Close the Monitor browser window or tab.

1. Close the app designer preview.

1. Do not navigate away from this page.

## Exercise 3: Monitor and fix bottle fill issue

In this exercise, you will monitor the application to determine what has
caused the bottle fill submission issue.

### Task 1: Debug

In this task, you will debug the application while you update a record
by using Monitor.

1. Make sure that the application is in the app designer.

1. Select the **Advanced tools** tab and then select **Open monitor**.

 :::image type="content" source="../media/open-monitor.png" alt-text="![Screenshot of the Open monitor button highlighted.]":::

   Monitor should open in a new browser tab or window and connect to your application.

1. Leave the Monitor tool running.

1. Return to the designer and select **Preview**.

1. Enter **28** for the **Volume** for one row and then select **Fill Bottle**.

    :::image type="content" source="../media/barrel-button.png" alt-text="![Screenshot of the Fill Bottle button.]":::

1. Go to Monitor and review the event logs. Make sure that no errors display, and then select the **patchRow** operation.

    :::image type="content" source="../media/patch-row.png" alt-text="![Screenshot of the patchRow operation selected.]":::

1. Select **Details** and then review the **formulaData** and **data**
    nodes. The **Details** tab shows all information that is shown on the
    **Formula**, **Request**, and **Response** tabs.

1. Select the **Formula** tab and then review the formula.

1. Select the **Request** tab and then review the body node. Today's date should show as
    **cv_battledon** and **cv_volume** should show as **28**.
    
    :::image type="content" source="../media/request-tab.png" alt-text="![Screenshot of the Request tab.]":::

1. Select the **Response** tab and make sure that a status of **200** shows.

1. You determine that everything seems to be working as expected. Select **Clear data**.

1. Return to the designer, enter **28.5** for the **Volume** for one row and then select **Fill Bottle**.

1. Return to the Monitor tool, which should show a **Bad Request** error for
    the **patchRow** operation. Select the **patchRow** operation.
    
    :::image type="content" source="../media/bad-request.png" alt-text="![Screenshot of the patchRow operation, showing Bad Result in the status column.]":::

1. Select the **Response** tab, expand the **body** node, and then read the message. The error was caused by a type mismatch.

    :::image type="content" source="../media/error-message.png" alt-text="![Screenshot of the error message.]":::

1. Leave the Monitor tool running.

1. Return to the designer and close the preview.

1. Do not navigate away from this page.

### Task 2: Fix the mismatch issue

In this task, you will fix the type mismatch issue.

1. Select the **Tree view** and then expand **BottleGallery**.

1. Select the **ButtonFillBottle** button.

    :::image type="content" source="../media/button-fill-button.png" alt-text="![Screenshot of the ButtonFillBottle control.]":::

1. Fix this issue by disabling the button, unless the user provides a whole number value.

1. Select **DisplayMode** from the formula bar and then change the current value to the following formula.

    :::image type="content" source="../media/formula-bar.png" alt-text="![Screenshot of the formula bar.]":::

    ```powerappsfl
        If(IsMatch(TextVolume.Text,\"\\d+\"),DisplayMode.Edit,DisplayMode.Disabled)     
    ```

1. Select **Preview**.

1. Go to the Monitor tool and select **Clear data**.

1. Return to the preview and enter **28** for one row's
    **Volume**. The **Fill Bottle** button should become enabled.

1. Change the **Volume** to **28.5**. The **Fill Bottle** button should
    now become disabled.

1. Type **28 oz** for **Volume**. The **Fill Bottle** button should
    stay disabled.

1. Change the **Volume** to **28**. The **Fill Bottle** button should
    become enabled.

1. Select the **Fill Bottle** button.

1. Go to the Monitor tool and make sure that no errors have occurred.

1. Close the Monitor tool.

1. Close the preview.

## Exercise 4: Collaborate

In this exercise, you will share a debugging session with a colleague,
and then you will monitor a published application.

### Task 1: Share a debugging session

In this task, you will share a session with a colleague.

 > [!NOTE] 
 > The user whom you are sharing the session with must be a member of your
organization and have a Power Apps license.

1. Go to [Power Apps maker portal](https://make.powerapps.com/)
    and make sure that you are in the correct environment.

1. Select **Solutions** and then select to open the **CoHo Vineyard - Monitor Module** solution.

1. Locate and select to open the **CoHo Bottle Management** application.

   The application should open in the app designer.

1. Select **Advanced tools > Open monitor**.

1. Select **Invite**.

    :::image type="content" source="../media/invite-button.png" alt-text="![Screenshot of the Invite button.]":::

1. Search for and then select the user whom you want to share the session with.

    :::image type="content" source="../media/invite-people.png" alt-text="![Screenshot of the Invite people to this session screen.]":::

1. Copy the link.

    :::image type="content" source="../media/copy-link.png" alt-text="![Screenshot of the Copy user session link button.]":::

1. Send the link to the user and then tell them to select the link.

   In this test case, Joni should see the session when navigating to the link that you provided.

    :::image type="content" source="../media/monitor-session-window.png" alt-text="![Screenshot of the Monitor session window.]":::

1. Return to the designer and select the **Preview** button.

1. Select the **Refresh** button.

    :::image type="content" source="../media/refresh-button.png" alt-text="![Screenshot of the Refresh button next to Bottle Management.]":::

1. Return to the Monitor tool, where event logs will display.

   Joni should also see the same event logs.
   
    :::image type="content" source="../media/joni-event-log.png" alt-text="![Screenshot showing rows of session events.]":::

1. Close the Monitor tool.

1. The session will be over; therefore, you will need to invite Joni again if you want to share another session.

1. Close the preview.

1. Do not navigate away from this page.

### Task 2: Debug a published application

In this task, you will enable published debugging for the application,
publish the application, and then debug the application while other people are
using it.

1. Select **File > Settings**.

 :::image type="content" source="../media/settings-button.png" alt-text="![Screenshot of the Settings button in the application.]":::

1. Scroll down and turn on the **Debug published app** toggle switch.

    :::image type="content" source="../media/debug-published.png" alt-text="![Screenshot of the Debug published app toggle turned on.]":::

1. Close the settings pop-up window.

1. Select **File > Save**.

1. Select **Publish**.

1. Select **Publish this version**.

Your application is now published, and people who have access to it will be able to use it.

### Task 3: Share and debug a published application

To test the published debugging, your first task is to play the published
application. Then, you will share the application with Joni and give
the basic user security role. Next, you will edit the security role and
allow users to view and update rows from the Bottle table. Joni is a
member of your organization who has a Power Apps license.

1. Go to [Power Apps maker portal](https://make.powerapps.com/)
    and make sure that you are in the correct environment.

1. Select **Apps**.

1. Select the **CoHo Bottle Management** application and then select **Share**.

    :::image type="content" source="../media/share-button.png" alt-text="![Screenshot of the CoHo Bottle Management app selected and the Share button highlighted.]":::

1. Find and then select the user whom you want to share the application with.

1. Select the **Basic User** role and then select **Share**.

    :::image type="content" source="../media/select-user.png" alt-text="![Screenshot of the Share CoHo Bottle Management pane with the user selected.]":::

1. Close the **Share** pane.

1. Select **Settings > Admin center**.

    :::image type="content" source="../media/settings-admin.png" alt-text="![Screenshot of Settings selected and the Admin center option highlighted.]":::

1. Select the environment that you are using for this lab and then select **Settings**.

1. Expand the **Users + permissions** section and then select **Security roles**.

    :::image type="content" source="../media/security-roles.png" alt-text="![Screenshot of the Users + permissions section, showing the Security roles option highlighted.]":::

1. Select the **Basic User** security role and then select **Edit**.

1. Select the **Custom Entities** tab.

1. Locate and then select the **Bottle** table.

    :::image type="content" source="../media/bottle-user.png" alt-text="![Screenshot of the Security Role: Basic User screen with the Bottle table highlighted.]":::

1. Select the **Bottle** table three more times.

1. The user should now have Organization level access, as shown in the following image. Select **Save and Close**.

    :::image type="content" source="../media/save-close.png" alt-text="![Screenshot of the Save and Close button.]":::

   The other person should now be able to use the application.

1. Go to [Power Apps maker portal](https://make.powerapps.com/)
    and make sure that you are in the correct environment.

1. Select **Apps**.

1. Select **CoHo Bottle Management > Monitor**.

    :::image type="content" source="../media/monitor-button.png" alt-text="![Screenshot of the Monitor button in the application.]":::

1. Select **Play published application**.

1. The application should load in a new tab or window. Select **Refresh**.

1. Go to the Monitor tool, where you can view session event logs.

    :::image type="content" source="../media/session-event-log.png" alt-text="![Screenshot of multiple session rows in the event log.]":::

1. Perform some actions in the application and then view the session event logs.

1. After you are done, close the application browser tab or window.

1. Select **Clear data**.

1. Select **Connect user**.

1. Find and then select the user whom you want to connect with.

1. Copy the link.

    :::image type="content" source="../media/copy-link.png" alt-text="![Screenshot of the People who have access to this session screen, showing the Copy user session link button highlighted.]":::

1. Give the link to the user and then ask them to select that link.

1. Close the **Connect user** pane.

1. When the other user navigates to the link, a pop-up window will appear, asking if they want to join the debug session.

    :::image type="content" source="../media/join-monitor.png" alt-text="![Screenshot of the Join monitor debug session pop-up window.]":::

1. The application should load for the other user, and they will know that other people can see the session data.

    :::image type="content" source="../media/monitor-debug-session.png" alt-text="![Screenshot of the monitor debug session.]":::

1. Go to the Monitor tool, where you can view event logs from the other user's interaction.

1. Tell the other user to create and update rows and then watch the event logs in the monitor.

1. Close the Monitor tool when you are done.
