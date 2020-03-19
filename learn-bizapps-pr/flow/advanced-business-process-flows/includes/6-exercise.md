We have one last enhancement before we complete our business process 
flow. Let's start with a quick review of the fields in the main form under the
diagram of our business process flow. 

The screenshot below shows a new instance of our business process flow. 
Notice there are only two fields shown on the main screen (outlined in red), 
the Name of the record - sort of like the title of this record, and the 
owner of the record - the current user who created the instance of the 
current business process flow. Let's add some fields to make this screen a 
little more useful.

## Add fields to the main form

Follow these steps to add fields to the main form. 

![Immersive flow with only two fields on main form](../media/25-immersive-flow-2-fields-on-main-form.png)

1. Log in to Power Automate and make sure you are in the proper environment 
we have been working in, then select **My flows** and then **Business process flows**.

1. Open the Customer Check In flow in design mode by selecting the pencil icon shown below.

	![Edit customer check in immersive flow](../media/26-edit-customer-check-in.png)

1. Select the last stage (Collect Payment) and then select the **Data Fields and Forms** link as shown below.

	![Select Hyperlink Click to add fields and forms](../media/27-add-forms-fields-hyperlink.png)

1. Let's start our enhancements by adding the following fields by selecting the **+Add field** button as shown below.

	![Select the add field button in the ribbon](../media/28-add-fields.png)

	- Clerk - Text
	
	- Transaction Date - Date Only
	
	- Location - New Option Set
	
		- Los Angeles
		- San Francisco
		- San Diego
		- Portland
	
	- Invoice Number - Autonumber - just leave the defaults provided by Power Automate and Common Data Service.
	
	- Service Comments - Text Area

1. Once you have added the new fields, make sure to save the entity by 
selecting the **Save Entity** button. Don't skip saving the entity or 
your new fields will not be saved with the entity.

   ![Select the save entity button](../media/29-select-save-entity-button.png)

1. Now we are ready to enhance the main form. Select the **Forms** tab in
the current screen as shown below.

   ![Select the Forms tab in the ribbon](../media/30-select-forms-tab.png)

1. Select the top main form name - it is a hyperlink to the form
designer. (don't worry if the name of your form is different). This will
open the WYSIWIG forms designer. The WYSIWIG designer is not
available for immersive business forms at this time.

   ![Select the main form](../media/31-select-main-form.png)

1. Select **Switch to classic** when the new screen opens.

   ![Select the Switch to classic button in the ribbon](../media/32-select-switch-classic.png)

1. Scroll down to the General section at the bottom of the form.
Double-click on the **Name** field and rename the title to say Invoice
Description as shown below and select the **OK** button.

   ![Rename the Name field to Invoice Title and select the OK button](../media/33-rename-title-field.png)

1. Now drag the new fields we just added earlier in this exercise
onto the form as shown below. Then, select the **Save** button and then select
the **Publish** button in the ribbon at the top of the form designer.

   ![Save and publish form by selecting buttons in the ribbon](../media/34-save-publish-form.png)

1. Close the Designer tab in the browser.

1. Go back to the home page of Power Automate. Select **My flows** and 
**Business process flows**. Select the Customer Check In flow and run 
an instance of the flow by selecting the small triangle icon next to the 
flow name. It should look like the screenshot below. Add some data to the 
main form and the stages and save the record.

   ![Observe new fields in main form](../media/35-observe-new-fields-main-form.png)

## Add read only fields to the form

You are doing great! Now let's add a few fields to the main form
from the data that we entered within a few of the stages. We will 
make these fields read only.

1. Go back to the list of Business process flows (available from **My flows** in
Power Automate).

1. Select the pencil button next to the Customer Check In flow to enter 
the business process flow designer.

1. Select the last Stage called Collect Payment and then select the
hyperlink **Click to add fields and forms** as shown below.

   ![Select the hyperlink](../media/36-add-forms-fields-hyperlink.png)

1. Select the **Forms** tab. 

   ![Select the Forms tab in the ribbon](../media/37-select-forms-tab.png)

1. Now select the name of the main form - it is a hyperlink to the form designer.

   ![Select the main form](../media/38-select-main-form.png)

1. Next, select **Switch to classic** as shown below. Now we are back at the 
form designer. Let's make a few more changes.

   ![Select Switch to Classic button in ribbon](../media/39-select-switch-classic.png)

1. Let's enhance the main form with some of the data we collect
within the stages. Clear the **Only show unused fields** option 
above the list of fields.

   ![Clear the only show unused fields option](../media/40-uncheck-unused-fields.png)

1. Now you can see all the fields available within the Customer Check In
entity. Drag in the following fields from the field panel into the
General section of the form as shown below.

   -   Entry Date
	
   -   First Name
	
   -   Last Name
	
   -   Smog Cert Number

    ![Add additional fields from the stages](../media/41-add-additional-fields-stages.png)

1. Double click on the **Entry Date** field we just added and make it
read-only, and then select the **OK** button as shown below.

   ![Make fields read-only](../media/42-make-field-read-only.png)

1. Now do the same for the following fields to also make them read-only.

	-   First Name
	
	-   Last Name
	
	-   Smog Cert Number

1. Now, select the **Save** button in the ribbon and then select **Publish** as shown below.

	![Save and publish by selecting buttons in ribbon](../media/43-save-publish-form.png)

1. Close the Form Designer tab and return to the business process
flow designer. Double-click on the first Stage and rename it to Customer
Info. Double-click on the second Stage and rename to Automobile Info as
shown below. Finally, select the **Update** button in the ribbon so all of
these changes are saved and ready to use.

   ![Name the stages properly](../media/44-name-stages.png)

1. Close the flow designer screen and refresh your browser. Run the Customer 
Check In flow to check that all the changes you made are working properly. 
The business process flow should look like the screenshot below.

   ![Main form with all fields](../media/45-nearly-finished-main-form.png)

You can create a new instance of the Customer Check In flow by selecting
the **+Add Record** button in the ribbon. 

![New instance by adding record](../media/46-detail-view-records.png)

Congratulations, you've created a working business process flow!  
