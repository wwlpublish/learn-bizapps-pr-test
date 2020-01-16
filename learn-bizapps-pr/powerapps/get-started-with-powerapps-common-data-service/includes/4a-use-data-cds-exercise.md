## Scenario

The current sales process for your company is manual and updates are only provided
each Friday. To simplify this process, minimize the opportunity for mistakes, and 
improve visibility, you have decided you want to create a new app to track sales 
leads and automatically calculate the forecasted revenue. You want to use Common 
Data Service to store the list of potential customers. 

## Use Common Data Service to store data

In this exercise, you will use Common Data Service to store the list of potential 
customers for your app. 

### Creating a Custom Entity

1. Go to the [Power Apps home page](https://powerapps.microsoft.com/?azure-portal=true) and sign in to Power Apps.
1. On the menu, expand **Data** and click **Entities**.
1. Click **New Entity**.
1. Enter the following information:
	- **Display name**: *Prospects*
1. In the Primary Field section, enter to following information:
	- **Display name**: *Prospect Name*
1. Click **Create**.
1. Click **Add field**.
1. Enter the following information:
	- **Display name**: *Stage*
	- **Data Type**: *Option Set*
1. For **Option Set**, click the dropdown and select **New option set**. Enter the following information and click **Save**.
	- **Display name**: *Prospect Stage*
	- **Name**: *prospectstage*
	- Add the following items/options: **Lead**, **Opportunity**, **Won**, **Lost**		
1. Once the option set has saved, continue entering the following information for the new field:
	- **Default value**: *Lead*
	- Check **Required**
1. Click **Done**.
1. Click **Add field**.
1. Enter the following information and then click **Done**.
	- **Display name**: *Contract Amount*
	- **Data Type**: *Currency*
1. Click **Add field**.
1. Enter the following information and then click **Done**.
	- **Display name**: *Probability*
	- **Data Type**: *Whole Number*
1. Click **Save Entity**, in the bottom right corner.
1. Click **Add field**.
1. Enter the following information and then click **Done**.
	- **Display name**: *Forecasted Revenue*
	- **Data Type**: *Currency*
	- Click **+Add** for Calculated or Rollup
	- Click **+Calculation**
1. On the popup, click **Save**.
1. A new browser window will open. Click **Add action**.
1. Enter the following formula, but do not copy and paste, type it in as your field names will not be exactly the same as the example below.  The crXXX_ is likely to be different than below.

	```cree0_contractamount * (cree0_probability / 100)```
1. Click the checkmark to save your changes. You may need to scroll right to see it.
1. Click **SAVE AND CLOSE**.
1. Click **Done**.

### Add a Business Rule

1.	On the entity designer toolbar, click **Business rules**.
1.	Click **Add business rule**, a new browser tab to open.
1.	Click on the **Condition New Condition** from the design pane.
1.	In the right-hand pane, for **Field** choose **Contract Amount**.
1.	For the Operator, choose **contains data**.
1.	Click **Apply**.
1.	In the right-hand pane, click **Components**.
1.	Click and hold **Set Business Required** and drag to the plus symbol to the right of the purple checkbox in the design pane.
1.	In the right-hand pane, for **Field** choose **Probability**.
1.	For the Status, choose **Business Required**.
1.	Click **Apply**.
1.	In the top left of the screen, click the dropdown next to **Prospects New business rule** and set the **Business rule name** to **Make Probability Required**.
1.	Click **Save** in top right corner of screen.
1.	Click **Activate** to activate the rule.
1.	Click **Activate** to confirm activation.
1.	Close the browser tab.
1.	Now back on the Entity management screen, click **Done**.

### Importing Data from an Excel file

Save the Excel spreadsheet (named Prospects.xlsx) that is located
[here](Prospects.csv) locally. You can review it before proceeding
with the following steps.

1. Open the file. Notice the “Stage” column is empty, you will need to look these up and enter them manually. 
1. On the left, click **Option sets**.
1. Click **Prospect Stage**.
1. Under Items (4), click the 3 dots **…** next to Lead.
1. Click **View more**.
1. Make a note or write down the number (will be something like 954,130,000) under Value.
1. Click the 3 dots **…** next to Opportunity.
1. Make a note or write down the number under Value.
1. Repeat these steps for the last two stages, **Won** and **Lost**.
1. Go back to your Excel file and in the Stage column enter the values as below:
	- **Contoso Flooring**: Enter the value (number) for Won.
	- **Fabrikam Inc**: Enter the value (number) for Won.
	- **Adventure Works**: Enter the value (number) for Lead.
	- **Adatum**: Enter the value (number) for Lead.
	- **VanArsdel**: Enter the value for Lost.
	- **Relecloud**: Enter the value for Opportunity.
1. Save and close the Excel file.
1. Continue with the **Prospects** entity.
1. Click the drop-down arrow to the right of **Get data** and select **Get data from Excel**.
1. Click **Upload**, locate the Prospects Excel file, and click **Open**.
1. Click **Map Fields**.  Map the following Prospect fields to the associated Source values:
	- **Contract Amount**: *ContractAmount*
	- **Prospect Name**: *Name*
	- **Stage Value**: *Stage*
	- **Probability**: *Probability*
1. Click **Save Changes** at the top.
1. Click **Import**.
1. Click **Entities**.
1. Click the **Prospects** entity and click **Data**.
1. Ensure that the data has successfully imported.

