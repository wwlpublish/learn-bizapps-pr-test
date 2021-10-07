You created and published the Bottle Management application at your
organization CoHo Winery.

You received feedback from your users that included the items below:

1) Users are getting a warning when they start the application.

2) Users are getting an error if they try to submit volume that
    includes decimal numbers.

**Note:** To successfully complete all steps in this lab, you will need
to have access to two users in your lab environment or work in pairs
with a classmate. If you do not have another user available, complete
the steps that you can, and read and review the paired activities.

## **Requirements:**

1) Debug using the monitor tool.

2) Resolve the issues.

3) Test your solutions.

4) Publish changes.

## **What you will learn**

1) How to use the monitor.

2) How to debug issues with your canvas application.

3) How to invite other users to debug sessions.

4) How to enable debug pushed application.

5) How to debug published application with connected user.

## **Exercise 1: Import solution and run flow**

In this exercise, you will import a solution into your environment and
run Power Automate cloud flow that will create sample date for you.

### **Task 1: Import solution**

In this task, you will import a solution into your environment.

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/)
    and select the environment you would like to use for this lab.

1. Select **Solutions** and select **Import**.

    :::image type="content" source="../media/import.png" alt-text="![Screenshot showing import solution button]":::

1. Select **Browse**.

1. Browse to the lab resources folder, select the
    CohoVineyardMonitorModule_1\_0_0\_1.zip solution, and select
    **Open**.

1. Select **Next**.

1. Select **Import** and wait for the solution importing to complete.
    Follow the step to establish the connection to Dataverse, if
    prompted.

1. Do not navigate away from this page.

### **Task 2: Run flow**

In this task, you will run a Power Automate cloud flow that will add
sample data to your environment.

1. While still on the **Solutions** tab, select **Import**.

1. Select to open the solution you imported in task 1.

    :::image type="content" source="../media/coho-solutions.png" alt-text="![Screenshot of Coho vineyard solution]":::

1. Locate and select to open the **Generate Test Data** cloud flow. If
    this is the first cloud flow for this environment, you may have to
    accept terms, and click to open again.
    :::image type="content" source="../media/coho-generate-test-data.png" alt-text="![Screenshot of generate test data and cloud flow type highlighted]":::
1. Select **Run**.

1. Select **Run flow**.

1. Select **Done** and wait for the flow run to complete. This can take
    3 to 6 minutes.
    :::image type="content" source="../media/succeeded.png" alt-text="![Screenshot of succeeded flow run]":::

1. Close the Power Automate browser window or tab.

1. Select **Done** on the popup.

1. Select **Apps**.

1. Select to launch the **CoHo Bottle Management** application.
    :::image type="content" source="../media/coho-app.png" alt-text="![Screenshot of CoHo Bottle Management app highlighted on the apps tab]":::

1. The application should load, and you should see the test data
    created by the cloud flow.
    :::image type="content" source="../media/canvas-rows.png" alt-text="![Screenshot of CoHo Bottle Management app with rows of data]":::

1. Close the application browser window or tab.

## **Exercise 2: Debug and fix load issue**

In this exercise, you will monitor the application to see what is
causing the failure when the application loads and fix it.

### **Task 1: Debug**

In this task, you will debug the application using the monitor.

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/)
    and select the environment you are using for this lab.

1. Select **Solutions** and click to open the **CoHo Vineyard --
    Monitor Module** solution.

1. Locate and select to open the **CoHo Bottle Management** canvas
    application.

1. The application should open in the app designer.

1. Select the **Advanced tools** tab and select **Open monitor**.
    :::image type="content" source="../media/open-monitor.png" alt-text="![Screenshot of open monitor highlighted in advanced tools]":::

1. The monitor should open in a new browser tab or window and connect
    to your application.

1. Do not close the monitor browser. Go back to the app designer and
    select **Preview**.
    :::image type="content" source="../media/powerapps-preview.png" alt-text="![Screenshot of preview application button]":::

1. The application should open in preview. Select **Refresh**
    button.
    :::image type="content" source="../media/powerapps-refresh.png" alt-text="![Screenshot of refresh data button]":::

1. Go back to the monitor review the monitor events. You should see a
    warning event of delegation category, and select it.
    :::image type="content" source="../media/warning-event.png" alt-text="![Screenshot of event log row]":::

1. The properties pane should open, select the **Details** tab, and
    click expand **formulaData** node.
    :::image type="content" source="../media/formula-data.png" alt-text="![Screenshot of monitor details tab and the expand button is highlighted]":::

1. Review the **formulaData** and then select to expand the **data**
    node.

1. Scroll down and read the issue.
 :::image type="content" source="../media/issue-message.png" alt-text="![Screenshot of issue message]":::

1. Select **Download**. You can download monitor event logs and upload
    them in future time or share with team members.

1. Save the monitor event log on your machine.

1. Select **Clear data**.

1. Close the monitor browser window or tab.

1. Go back to the designer and close the preview.
    :::image type="content" source="../media/close-preview.png" alt-text="![Screenshot of issue message]":::

1. Do not navigate away from this page.

### **Task 2: Fix formula**

In this task, you will fix the

1. Select **Tree view** and then select the **BottleGallery**.
    :::image type="content" source="../media/tree-view.png" alt-text="![Screenshot of bottle gallery selected in tree view]":::

1. Select Items from the formula bar. Notice the warning is also
    showing here.
    :::image type="content" source="../media/warning-message.png" alt-text="![Screenshot of formula bar warning message]":::

    > [!NOTE]
    > You may also see the warning displayed like below.

    :::image type="content" source="../media/warning-display.png" alt-text="![Screenshot of image showing an alternate display for the delegation warning]":::

1. Replace the current formula to the formula below.

    ```powerappsfl
        Filter(Bottles \'Modified On\' \> DateAdd(Today(), - 7, Days))     
    ```

1. The warning should go away.

1. Select the **Advanced tools** and select **Open monitor** again.

1. Leave the monitor running.

1. Go back to the app designer and select **Preview**.

1. Select on the **Refresh** button.

1. You should no longer see the warning.

1. Select **Clear data** button.

1. Select **Upload**.

1. Select the file you downloaded earlier and select **Open**.
    :::image type="content" source="../media/powerapps-file.png" alt-text="![Screenshot of power apps json file]":::

1. The file should upload, and you should see your earlier event logs.
    :::image type="content" source="../media/earlier-event-log.png" alt-text="![Screenshot of earlier event log]":::

1. Select **Clear data**.

1. Close the monitor browser window or tab.

1. Close the app designer **preview**.

1. Do not navigate away from this page.

## **Exercise 3: Monitor and fix bottle fille issue**

In this exercise, you will monitor the application to see what is
causing the bottle fill submission issue.

### **Task 1: Debug**

In this task, you will debug the application while you update a record
using the monitor.

1. The application should be in the app designer.

1. Select the **Advanced tools** tab and select **Open monitor**.
 :::image type="content" source="../media/open-monitor.png" alt-text="![Screenshot of open monitor button highlighted]":::

1. The monitor should open in a new browser tab or window and connect
    to your application.

1. Leave the monitor running.

1. Go back to the designer and select **Preview**.

1. Enter **28** for the **Volume** of one of the rows and select **Fill
    Bottle**.
    :::image type="content" source="../media/barrel-button.png" alt-text="![Screenshot of fill bottle button]":::

1. Go to the monitor and review the event logs. There should be no
    errors, select **patchRow** operation.
    :::image type="content" source="../media/patch-row.png" alt-text="![Screenshot of patch row selected]":::

1. Select **Details** and review the **formulaData** and **data**
    nodes. The Details tab shows all the information shown on the
    Formula, Request, and Response tabs.

1. Select the **Formula** tab and review the formula.

1. Select the **Request** tab and review the body node. You should see
    **cv_battledon** as today's date and **cv_volume** as the **28** you
    provided.
    :::image type="content" source="../media/request-tab.png" alt-text="![Screenshot of request tab]":::

1. Select the **Response** tab and make sure you got status of **200**.

1. Everything seems to work as expected. Select **Clear data**.

1. Go back to the designer, enter **28.5** for the **Volume** of one of
    the rows and click **Fill Bottle**.

1. Go back to the monitor. You should see a **Bad request** error for
    the **PatchRow** operation. Click to select the **patchRow**
    operation.
    :::image type="content" source="../media/bad-request.png" alt-text="![Screenshot of patch row with bad result in the status column]":::

1. Select the **Response** tab, expand the **body** node, and read the
    message. The error was caused by a type mismatch.
    :::image type="content" source="../media/error-message.png" alt-text="![Screenshot of error message]":::

1. Leave the monitor running.

1. Go back to the designer and close the preview.

1. Do not navigate away from this page.

### **Task 2: Fix issue**

In this task, you will fix the type mismatch issue.

1. Select the **Tree view** and expand the **BottleGallery**.

1. Select the **ButtonFillBottle** button.
    :::image type="content" source="../media/button-fill-button.png" alt-text="![Screenshot of button fill bottle control]":::

1. You will fix this issue by disabling the button unless the user
    provides a whole number value.

1. Select DisplayMode from the formula bar and change the current value
    to the formula below.
    :::image type="content" source="../media/formula-bar.png" alt-text="![Screenshot of formula bar]":::

    ```powerappsfl
        If(IsMatch(TextVolume.Text,\"\\d+\"),DisplayMode.Edit,DisplayMode.Disabled)     
    ```

1. Select **Preview**.

1. Go to the monitor and select **Clear data**.

1. Go back to the preview and enter **28** for one of the row's
    **Volume**. The **Fill Bottle** should become enabled.

1. Change the **Volume** to **28.5**. The **Fill Bottle** button should
    now become disabled.

1. Type **28 oz** for **Volume**. The **Fill Bottle** button should
    stay disabled.

1. Change the **Volume** to **28**. The **Fill Bottle** button should
    become enabled.

1. Select **Fill Bottle** button.

1. Go to the monitor and make sure there are no errors.

1. Close the monitor.

1. Close the preview.

## **Exercise 4: Collaborate**

In this exercise, you will share a debugging session with a colleague,
and then you will monitor published application.

### **Task 1: Share debugging session**

In this task, you will share a session with a colleague.

Note: The user you are sharing the session with must be a member of your
organization and have a Power Apps license.

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/)
    and make sure you are in the correct environment.

1. Select **Solutions** and select to open the **CoHo Vineyard --
    Monitor Module** solution.

1. Locate and select to open the **CoHo Bottle Management** application.

1. The application should open in the app designer.

1. Select the **Advanced tools** tab and select **Open monitor**.

1. Select **Invite**.
    :::image type="content" source="../media/invite-button.png" alt-text="![Screenshot of invite user button]":::

1. Search and select the user you want to share the session with.
    :::image type="content" source="../media/invite-people.png" alt-text="![Screenshot of invite people to the session screen]":::

1. Copy the link.
    :::image type="content" source="../media/copy-link.png" alt-text="![Screenshot of copy session link button]":::

1. Send the user the link and tell them to navigate to that link.

1. In our test case Joni should see the session when she navigates to
    the link we gave here.
    :::image type="content" source="../media/monitor-session-window.png" alt-text="![Screenshot of monitor session window]":::

1. Go back to the designer and select preview.

1. Select on the **Refresh** button.
    :::image type="content" source="../media/refresh-button.png" alt-text="![Screenshot of refresh button]":::

1. Go back to the monitor. You should see event logs.

1. Joni should also see the same event logs.
    :::image type="content" source="../media/joni-event-log.png" alt-text="![Screenshot of rows of session events]":::

1. Close the monitor.

1. The session will be over, you will have to invite Joni again if you
    want to share another session with her.

1. Close the preview.

1. Do not navigate away from this page.

### **Task 2: Debug published application**

In this task, you will enable published debugging for the application,
publish the application, and debug the application while other users are
using the application.

1. Select **File** and select **Settings**.
 :::image type="content" source="../media/settings-button.png" alt-text="![Screenshot of application settings button]":::

1. Scroll down and turn on **Debug published app**.
    :::image type="content" source="../media/debug-published.png" alt-text="![Screenshot of debug published app]":::

1. Close the settings popup.

1. Select **File** again and click **Save**.

1. Select **Publish**.

1. Select **Publish this version**.

1. Your application is now published and users who have access to it
    will be able to use it.

### **Task 3: Share application and debug published**

To test the published debugging, you will first play the published
application and then you will share the application with Joni and give
the basic user security role, you will also edit the security role and
allow users to see and update rows form the bottle table. Joni is a
member of our organization, and she has a Power Apps license.

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/)
    and make sure you are in the correct environment.

1. Select **Apps**.

1. Select **CoHo Bottle Management** application and click **Share**.
    :::image type="content" source="../media/share-button.png" alt-text="![Screenshot of share application button]":::

1. Find the user you want to share the application with and select.
    :::image type="content" source="../media/share-button.png" alt-text="![Screenshot of share application button]":::

1. Select the **Basic User** role and click **Share**.
    :::image type="content" source="../media/select-user.png" alt-text="![Screenshot of share application with user selected]":::

1. Close the share pane.

1. Select **Settings** and select **Admin center**.
    :::image type="content" source="../media/settings-admin.png" alt-text="![Screenshot of settings button and a rectangle around the admin center]":::

1. Select the environment you are using for this lab and click
    **Settings**.

1. Expand the **Users + permissions** section and select **Security
    roles**.
    :::image type="content" source="../media/security-roles.png" alt-text="![Screenshot of rectangle around the security roles button]":::

1. Select the **Basic User** security role and click **Edit**.

1. Select the **Custom Entities** tab.

1. Locate the **Bottle** table and click on it.
    :::image type="content" source="../media/bottle-user.png" alt-text="![Screenshot of rectangle around the security roles button]":::

1. Click the **Bottle** table three more times.

1. The user should now have Organization level access, as shown in the
    image below. Select **Save and Close**.
    :::image type="content" source="../media/save-close.png" alt-text="![Screenshot of save and close button]":::

1. The other user should now be able to use the application.

1. Navigate to [Power Apps maker portal](https://make.powerapps.com/)
    and make sure you are in the correct environment.

1. Select **Apps**.

1. Select **CoHo Bottle Management** application and click **Monitor**.
    :::image type="content" source="../media/monitor-button.png" alt-text="![Screenshot of rectangle around the monitor application button]":::

1. Select **Play published application**.

1. The application should load in a new tab or window. Select
    **Refresh**.

1. Go to the monitor. You should see session event logs.
    :::image type="content" source="../media/session-event-log.png" alt-text="![Screenshot of session rows in the event log]":::

1. Go ahead and perform some actions in the application and then see
    the session event logs.

1. After you are done close the application browser tab or window.

1. Select **Clear data**.

1. Select **Connect user**.

1. Find the user you want to connect and select.

1. Copy the link.
    :::image type="content" source="../media/copy-link.png" alt-text="![Screenshot of session rows in the event log]":::

1. Give the link to the user and ask them to navigate to that link.

1. Close the connect user pane.

1. When the other user navigates to the link, they will see a popup
    that looks like the image below. Ask them to join.
    :::image type="content" source="../media/join-monitor.png" alt-text="![Screenshot of join monitor debug popup]":::

1. The application should load for the other user, and they will be
    aware other people can see the session data.
    :::image type="content" source="../media/monitor-debug-session.png" alt-text="![Screenshot of monitor debug session]":::

1. Go to the monitor. You should see event logs from the others user's
    interaction.

1. Tell the other user to create and update rows and watch the event
    logs in the monitor.

1. Close the monitor when done.
