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
1. On the menu, expand **Data** and Select **Entities**.
1. Select **New Entity**.
1. Enter the following information:
	- **Display name**: *Prospects*
1. In the Primary Field section, enter the following information:
	- **Display name**: *Prospect Name*
1. Select **Create**.
1. Select **Add field**.
1. Enter the following information:
	- **Display name**: *Stage*
	- **Data Type**: *Option Set*
1. For **Option Set**, Select the dropdown and select **New option set**. Enter the following information and Select **Save**.
	- **Display name**: *Prospect Stage*
	- **Name**: *prospectstage*
	- Add the following items/options: **Lead**, **Opportunity**, **Won**, **Lost**		
1. Once the option set has saved, continue entering the following information for the new field:
	- **Default value**: *Lead*
	- Check **Required**
1. Select **Done**.
1. Select **Add field**.
1. Enter the following information and then Select **Done**.
	- **Display name**: *Contract Amount*
	- **Data Type**: *Currency*
1. Select **Add field**.
1. Enter the following information and then Select **Done**.
	- **Display name**: *Probability*
	- **Data Type**: *Whole Number*
1. Select **Save Entity**, in the bottom-right corner.
1. Select **Add field**.
1. Enter the following information and then Select **Done**.
	- **Display name**: *Forecasted Revenue*
	- **Data Type**: *Currency*
	- Select **+Add** for Calculated or Rollup
	- Select **+Calculation**
1. On the popup, Select **Save**.
1. A new browser window will open. Select **Add action**.
1. Enter the following formula, but do not copy and paste, type it in as your field names will not be exactly the same as the example below.  The crXXX_ is likely to be different than below.

	```cree0_contractamount * (cree0_probability / 100)```
1. Select the checkmark to save your changes. You may need to scroll right to see it.
1. Select **SAVE AND CLOSE**.
1. Select **Done**.

### Add a Business Rule

1.	On the entity designer toolbar, Select **Business rules**.
1.	Select **Add business rule**, a new browser tab will open.
1.	Select on the **Condition New Condition** from the design pane.
1.	In the right-hand pane, for **Field** choose **Contract Amount**.
1.	For the Operator, choose **contains data**.
1.	Select **Apply**.
1.	In the right-hand pane, Select **Components**.
1.	Select and hold **Set Business Required** and drag to the plus symbol to the right of the purple checkbox in the design pane.
1.	In the right-hand pane, for **Field** choose **Probability**.
1.	For the Status, choose **Business Required**.
1.	Select **Apply**.
1.	In the top left of the screen, Select the dropdown next to **Prospects New business rule** and set the **Business rule name** to **Make Probability Required**.
1.	Select **Save** in top-right corner of screen.
1.	Select **Activate** to activate the rule.
1.	Select **Activate** to confirm activation.
1.	Close the browser tab.
1.	Now back on the Entity management screen, Select **Done**.

### Importing Data from an Excel file

You will use the Excel spreadsheet named [Prospects](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-apps/Prospects.zip/?azure-portal=true) for this
exercise. Open the link, and select the Download button and save it locally. 

1. Open the file. Notice the “Stage” column is empty, you will need to look these up and enter them manually. 
1. Go to the [Power Apps home page](https://powerapps.microsoft.com/?azure-portal=true) and sign in to Power Apps.
1. Go back to your Excel file and in the Stage column enter the values as below:
	- **Contoso Flooring**: Won.
	- **Fabrikam Inc**:  Won.
	- **Adventure Works**: Lead.
	- **Adatum**: Lead.
	- **VanArsdel**: Lost.
	- **Relecloud**: Opportunity.
1. Save and close the Excel file.
1. Continue with the **Prospects** entity.
1. Select the drop-down arrow to the right of **Get data** and select **Get data from Excel**.
1. Select **Upload**, locate the Prospects Excel file, and Select **Open**.
1. Select **Map Fields**.  Map the following Prospect fields to the associated Source values:
	- **Contract Amount**: *ContractAmount*
	- **Prospect Name**: *Name*
	- **Stage Value**: *Stage*
	- **Probability**: *Probability*
1. Select **Save Changes** at the top.
1. Select **Import**.
1. Select **Entities**.
1. Select the **Prospects** entity and Select **Data**.
1. Ensure that the data has successfully imported.
