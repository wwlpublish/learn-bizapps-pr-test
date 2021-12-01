In this unit, you'll see how Contoso Electronics uses Power Automate to automatically convert documents to a standard format and then store them in Microsoft SharePoint Online. You'll create a flow that detects when a new file has been added to a Microsoft OneDrive for Business folder. The flow then converts that file to a PDF and stores it in a SharePoint Online folder.

## Prerequisites

For this scenario, you need an account with Muhimbi, a PDF conversion service. If you don't already have a Muhimbi account, you can sign up for a [free 30-day trial](https://www.muhimbi.com/Products/PDF-Converter-Online/?azure-portal=true).

In Muhimbi, you need to subscribe to the PDF Converter Online service.

## Add the connector

In Power Automate, in the left verification navigation, select Data, select Connections and then select + New Connection.

> [!div class="mx-imgBorder"]
> [![Screenshot of OneDrive for Business Data Connections page with New connection button highlighted.](../media/add-connector.png)](../media/add-connector.png#lightbox)

In the search available on the top-right, start typing in 'muh.' When you see the Muhimbi PDF connector, select the '+' plus sign.

> [!div class="mx-imgBorder"]
> [![Screenshot of OneDrive for Business Data Connections page with Muhimbi PDF selected.](../media/add-muhimbi-connector.png)](../media/add-muhimbi-connector.png#lightbox)

Next, select Create.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Muhimbi PDF dialog with a Create button.](../media/create-connector.png)](../media/create-connector.png#lightbox)

In the pop-up authentication window, type in the username and password you created at Muhimbi.

> [!div class="mx-imgBorder"]
> [![Screenshot of the muhimbi login page.](../media/username-password.png)](../media/username-password.png#lightbox)

You will now have a new connector added to your environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of OneDrive for Business Data Connections page with Muhimbi added.](../media/connector-added.png)](../media/connector-added.png#lightbox)

## Create the source and target folders

First, you must create the source and target folders in OneDrive for Business and SharePoint Online.

1. In OneDrive for Business, under **My files**, create a folder named **Finished Documents**.
1. In SharePoint Online, in **Shared Documents**, create a folder named **PDF – Finished files**.

## Create the flow

1. In Power Automate, select **My Flows**, and then select **+ New flow**.

1. From dropdown, under **Build your own from blank**, select **Automated cloud flow**.

1. In the Flow name field, give your flow a name, in this example we will call it *Flow Conversion and Upload*.

1. In the **Choose your flow's trigger** search field, enter *OneDrive for Business*, and select the **OneDrive for Business - When a file is created** trigger.

    ![Screenshot of a OneDrive for Business trigger.](../media/onedrive-trigger.png)

1. Then select **Create** to proceed.

1. In the **Folder** field, select the **Folder** icon, and then select the **Finished Documents** folder that you created at the beginning of this module.

1. Now you want to add another step, select **+ New step**.

1. In the search box, enter *muhimbi*, and then select the **Muhimbi PDF – Convert document** action.

    ![Screenshot of the search box with muhimbi.](../media/muhimbi-action.png)

1. If Power Automate prompts you to sign in to Muhimbi, sign in. If you don't have a subscription to Muhimbi, you can use a [free 30-day trial](https://www.muhimbi.com/register/?azure-portal=true).

1. In the **Convert document** action, set the following values:

    * **Source file name**: In the dynamic content list, select **File name**.
    * **Source file content**: In the dynamic content list, select **File content**.
    * **Output format**: Select *PDF*.

    ![Screenshot of the Muhimbi setup showing Convert document action with File name dynamic content as the Source file name, and File content as the Source file content.](../media/muhimbi-configuration.png)

    So far, you've set up these steps for your flow:

    1. The flow is triggered whenever a new file is added to a specific OneDrive for Business folder.
    1. The Muhimbi service converts that file to PDF.

    For the final step, you'll add an action that moves the PDF document to a SharePoint Online folder where the team can access it.

1. Select **+ New step**.

1. In the search field, enter *create file*, and then select the **SharePoint – Create file** action.

    ![Screenshot of Choose an action search results for SharePoint – Create file.](../media/sharepoint-create-file.png)

1. In the **Create file** action, set the following values:

	- **Site address**: Enter the URL of your SharePoint site.
	- **Folder path**: Select the Folder icon, and browse to the **PDF - Finished files** folder.
	- **File name**: In the dynamic content list, under **Convert document**, select **Base file name**. Then enter *.pdf* so that the file will be saved with the .pdf file name extension in SharePoint.
	- **File content**: In the dynamic content list, under **Convert document**, select **Processed file content**.

    ![Screenshot of the Create file action with the above mentioned properties filled in.](../media/sharepoint-configure-file.png)

1. Select **Save** at the top of the page to save your work.

## Test the flow

1. To test the flow, add a new file to your **Finished Documents** folder in OneDrive for Business.
1. In Power Automate, select **My flows**, and then select the **Flow Conversion and Upload** flow to view the run history.
1. After the flow runs, make sure that the file was converted to a PDF and saved to the **PDF – Finished files** folder in SharePoint.
