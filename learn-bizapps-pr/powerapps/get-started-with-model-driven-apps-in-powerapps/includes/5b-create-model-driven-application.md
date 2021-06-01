## Scenario

In the [exercise](/learn/modules/get-started-with-powerapps-common-data-service/4a-use-data-cds-exercise/?azure-portal=true) in the previous module of this learning path, you created 
the Prospects table in Microsoft Dataverse and imported the existing leads, 
now in this exercise you will use this data to create a model-driven app. If you do not have the *Prospects* table then refer to the previous exercise or follow the **Create the custom table** steps below.
This app will allow the sales team to enter and edit leads on the go and 
keep the managers up to date on the current leads and forecasted revenue.

### Create the custom table 
You can skip these steps if you have already created the *Prospects* table. 

1. Go to the [Power Apps home page](https://powerapps.microsoft.com/)  and sign in to Power Apps.
1. On the menu, expand **Data** and **Select Tables**.
1. Select **New Table**.
1. Enter the following information:
	- **Display name**: *Prospects*
1. In the Primary column section, enter the following information:
	- **Display Name**: *Prospect Name*
1. Select **Create**.
1. Select **Done**.

### Create the model-driven app for the prospects table

1. Sign in to [Power Apps](https://make.powerapps.com/?azure-portal=true) by using your organizational account.
1. Select the environment you want, or go to the [Power Apps admin center](https://admin.powerplatform.microsoft.com/?azure-portal=true) to create a new one.
1. On the **Home** page, select the **Model-driven app from blank**.  
1. Select **Create**.
1. Enter the following and Select **done**.
	- Name:  Prospect Entry
1. Select the **Open the Site Map Designer** pencil icon to open the site map designer.
1. Select **New Subarea**.
1. On the right, for **Title** enter **Prospects Area**.
1. Click the drop down for **select a type**, then choose **Table (Entity)**.
1. For Table (Entity), select **Prospects**.
1. Select **New Group**.
1. On the right, for **Title** enter **Prospects Group**.
1. Click **Save**.
1. Click **Publish**.

### Creating a chart

1.	Select **Charts**.
1.	Select **Create New**.
1.	For the Chart Name, enter **Forecasted Revenue by Stage**.
1.	For Legend Entries (Series), check the box, and select the **Forecasted Revenue** column.
1.	For Horizontal (Category) Axis Labels, select the **Stage** column.
1.	Select **Save and Close**.
1.	Back on the App Designer, select the checkbox next to **Forecasted Revenue by Stage**.
1.	Select **Save**.
1.	Select **Publish**.

### Creating the form

You can attempt to create a new form in the App Designer but if you run
into any issues, you can follow the steps below to create a new main
form.

1.  Go to the Power Apps Home Page, and on the left, Select **Data**.
1.  Select **Tables**.
1.  Locate and select the **Prospects** table. 
1.  Select **Forms**.
1.  Select the drop-down arrow next to Add form, and then select **Main Form** from the drop down. A new window will open.
1.  Drag the **Stage** column from the right and place it below the **Owner** column in the center.
1.  Drag the **Contract Amount** column and place it below the **Stage** column.
1.  Drag the **Probability** column and place it below the **Contract Amount** column.
1.  Drag the **Forecasted Revenue** column and place it below the **Probability** column.
1.  Now select **Forecasted Revenue** and then select **Change Properties** on the ribbon.
1.  Select the checkbox for **Read-only column**.
1.  Select **Save**.
1.  Select **Publish**.
1.  Close the window.
1.  Select **Done**.
