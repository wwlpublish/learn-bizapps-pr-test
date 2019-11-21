You can export and then import a flow so that others can use it.

## Export a flow

1. Go to Power Automate, and sign in by using your organizational account.
1. In the left pane, select **My flows**.
1. For the flow that you want to export, select the **More commands** button (the three vertical dots), select **Export**, and then select **Package (.zip)**.

    ![Export a package](../media/flow-export.png)

1. Fill in information about the package:

    - **Name**: Enter a name for the flow.
    - **Environment**: Enter the environment for the flow.
    - **Description**: Enter a description of the flow.
    - **Review package content**: Select export options, and add comments to provide instruction or add version notes.

1. Select **Export** to export the zip file. You can then select the folder to download to.

When you export a flow, the dependent resources for your flow are also exported into the package.

## Import a flow

After a flow has been exported, anyone that you send the zip file to can import it.

1. Go to Power Automate, and sign in by using your organizational account.
1. In the left pane, select **My flows**.
1. Select **Import**.

    ![Import a flow](../media/flow-import.png)

1. On the **Import package** page, select **Upload**, and then, in the dialog box, select the zip file that you exported.
1. Back on the **Import package** page, select **Import**.

    - In the flow settings, you can select whether to create a new flow or update an existing one with the flow definition from the package.
    - You must also select the connections that are required to set up the flow as part of the import process.
    - The **Import** button should become available after you've set all the required settings.

1. After the flow is completely imported, select **Save Power Automate**.
