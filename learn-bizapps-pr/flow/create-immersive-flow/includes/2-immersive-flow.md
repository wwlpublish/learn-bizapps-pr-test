We are finally ready to start building an immersive Business process
Flow with Power Automate and Common data service. Recall that all data
associated with any Business Process Flow is always stored in one or
more entities within Common Data Service and Business Process Flows.

> [!NOTE]
> You will need access to an account that has permission to create entities and fields in Common Data Service to complete this exercise and PowerApps or Dynamics 365 License. Ask your Power Platform administrator for proper permissions or log in and create a personal Power Apps and Power Automate development environment using the Community License plan (it is free) by accessing [PowerApps](https://powerapps.microsoft.com/communityplan/?azure-portal=true).

### Scenario

You work for SmogChecksRUs, a rapidly growing auto repair
company that specializes in performing automotive smog checks and other
auto services. SmogChecksRUs has been using an Excel spreadsheet to
collect customer and vehicle information, but now marketing has asked
for a better way to collect information so they can follow-up with
customers and schedule checkups every two years, improve customer
retention, and increase sales.

Management believes improved data collection and standardized processes
will improve customer satisfaction, improve customer loyalty, and
increase recurring business and overall sales revenue. You have decided
to create an immersive Business Flow using Power Automate to meet
management goals. Let's get started.

1. Log into [Power Automate](https://us.flow.microsoft.com/?azure-portal=true) and sign
in. If you are outside the United States, log into your local instance
of Power Automate.

1. Make sure to select the proper environment using the "gear" in the
top right-hand side of the top ribbon.

	![Select Environment in Power Automate](../media/3-selecting-environment-power-automate.png)

1. Select My Flows in the menu on the left then select the Business
Process Flows tab.

	![Selecting My flows and Business Process Flows in Power Automate](../media/4-selecting-my-flows-business-process-flows-power-automate.png)

1. Select the "+ New" button.

	![Creating a new Business Process Flow using the + New button](../media/5-creating-new-business-process-flow-using-new-button.png)

1. Name the Business Process Flow "Customer Check In" and select "None
(Immersive Business Process)" under the entity dropdown and select the
"Create" button as shown below. Wait a moment for the entity to be
created and the Business Process Flow editor will launch.

	![Naming the new Business Process Flow](../media/6-naming-new-business-process-flow.png)

1. After a moment, the Business Process Flow Editor will open and you
can start adding fields to the new Entity (customercheckin) that was
automagically create in step 5. Select the "Customer Check In New Stage"
as shown below.

	![Selecting Stage One in the Business Process Flow Editor](../media/7-selecting-stage-one-business-process-flow-editor.png)

1. Select the New Stage within the designer and rename the Stage to
"Collect Customer Information" then select the "Apply" button as shown
in the screenshot below.

	![Naming Stage One in the Business Process Flow Editor](../media/8-naming-stage-one-business-process-flow-editor.png)

	Now we will add some fields to the new CollectCustomerInfo entity in Common Data Service so we can capture customer information.

1. Select the "Collect Customer Info" stage the hyperlink "Click to
add fields and forms" as shown below.

	![Select Click to add fields and forms hyperlink](../media/9-select-click-add-fields-and-forms-hyperlink.png)

	![Detail of select Click to add fields and forms hyperlink](../media/10-select-click-add-fields-and-forms-hyperlink.png)

	Now let's add some fields. Add fields to the collectcustomerinfo entity
	by selecting the "Add Field" button as shown below.

	![Selecting +Add Field button](../media/11-selecting-add-field-button.png)

1. Add each field listed below - type the name and data type and
select the "Done" button each time you add a new field as shown in the
screen below.

	![Creating Entry Date Field](../media/12-creating-entry-date-field.png)

	- Entry Date - Date Only
	- First Name - Text
	- Last Name - Text
	- Phone Number - Phone
	- Address - Text
	- City - Text
	- State - Text
	- Postal Code - Text
	- Phone Number - Phone Number
	- Comments - Text Area

1. When you are done, select the "Save Entity" button as shown to
save the new fields. Make sure to select the Save Entity button or none
of the fields will be added.

	![Select Save Entity button](../media/13-select-save-entity-button.png)

1. Now we are ready to add the fields as Steps in the first Stage in
the "Customer Check In" Business Process Flow. Close the current tab of
the browser showing the entity fields and return to the Business Process
Flow designer screen as shown below.

	1. Refresh your browser.

	1. Select the "Customer Check In" Stage.

		![Add a data step](../media/14-add-data-step.png)

	1. Select the Data Step # 1 and then enter the Following as shown below:

		-   Step Name - Type "First Name"
		
		-   Data Field - Select "First Name" from the dropdown in Data Field
		
		-   Select Required checkbox
		
		-   Then select the "Apply" Button
		
		![Adding First Name Data Step](../media/15-adding-first-name-data-step.png)

1. Select the Components tab and drag a "Data Step" under data Step 1
as shown below.

	![Add another data step](../media/16-add-another-data-step.png)

1. Select Data Step #2 and enter in the following Information.

	-   Step Name - Last Name
	
	-   Data Field - Last Name
	
	-   Select the Required Checkbox
	
	-   Select the "Apply" Button

	![Add Last Name Data Step](../media/17-add-last-name-data-step.png)

1. Select the Components tab and drag additional data steps and add
fields until all fields we added in step 8 above have been entered under
stage one. (Date Entered, Address, City, State, Postal Code, Comments).

1. When you are done, Stage 1 should look as shown below. If all
looks correct then select the Update button in the ribbon.

	![All data steps in stage one](../media/18-all-data-steps-stage-one.png)

	> [!NOTE]
	> When the Data Process Flow is used, data will be saved into the
	fields we created in the customercheckin entity in Common Data Service -
	Aha!

	Now we want to collect information about the automobile being serviced so let's add a new stage and add fields about the automobile to the
	customercheckinentity.

1. Select the Components Tab and drag a new stage to the right of
stage 1. Make sure to drop it into the "+" sign. The new stage should
look like the screenshot below.

	![Add a new stage component](../media/19-add-new-stage-component.png)

1. Now repeat the steps we covered for stage 1 (steps 7 -10 above)
and add the following fields and steps.

	-   Automobile Make - Text
	
	-   Automobile Model - Text
	
	-   Automobile Year - Number
	
	-   Automobile Mileage - Number
	
	-   Automobile Comments - Text Area

Make sure to save the entity after you add the new fields.

When you are done adding the data steps, make sure to select the update
button in the ribbon as we did in step 14. Your completed stage 2 should
look like the screenshot below.

![Second stage added](../media/20-second-stage-added.png)
