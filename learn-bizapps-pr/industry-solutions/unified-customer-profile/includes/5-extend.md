In this exercise, you will be customizing UCP application in the following ways. 

- Take UCP application as base and edit it to add a new control to it.

- Edit UCP controls such as Life Event Type to add a new Life Event Type.

## Task 1: Add new controls to UCP

In this task, we will first create a new solution and then customize UCP to add new controls.

1.  Navigate to [Power Apps](http://make.powerapps.com/?azure-portal=true) in an In-Private or Incognito window.

1.  Select the proper **Environment** in the upper right.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the environment in the upper right.](../media/environment.png)](../media/environment.png#lightbox)

1.  In Power Apps, select **Solutions** in the left sitemap. Select **+New Solution** and set following values.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new solution button.](../media/new-solution.png)](../media/new-solution.png#lightbox)

1.  Create a new solution with the following properties and select**Create**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new solution details.](../media/solution.png)](../media/solution.png#lightbox)

1.  Once the solution is created, select the solution name to begin adding components.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the solution name.](../media/solution-name.png)](../media/solution-name.png#lightbox)

1.  In the solution explorer, select**Add existing** > **App** > **Model-driven app**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the steps to add an existing model-driven-app.](../media/add-model-driven-app.png)](../media/add-model-driven-app.png#lightbox)

1.  Select the **Unified customer profile** application from the list and select**Add**. 

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the unified customer profile application selected.](../media/unified-customer-profile-application.png)](../media/unified-customer-profile-application.png#lightbox)

1.  Select the application name **Unified Customer Profile** to edit it.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the unified customer profile edit.](../media/edit-unified-customer-profile.png)](../media/edit-unified-customer-profile.png#lightbox)

1.  This will open the application editor in another tab.

1. Select the Forms dropdown and then on the edit icon for **Unified customer profile**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the forms dropdown with edit unified customer profile selected.](../media/forms-edit.png)](../media/forms-edit.png#lightbox)

1. This will open the form designer for Unified customer profile. Select the **Switch to Classic** menu item to launch the classic form designer.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the switch to classic button. ](../media/classic.png)](../media/classic.png#lightbox)

1. In the form designer, select the **Summary** tab to select it.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the summary tab in the form designer.](../media/summary.png)](../media/summary.png#lightbox)

1. Select **Insert** and then **One Column** tab.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the insert window with one column selected.](../media/insert-column.png)](../media/insert-column.png#lightbox)

1. This will add a new tab to the form under **Summary**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new tab added.](../media/new-tab.png)](../media/new-tab.png#lightbox)

1. Once the tab is added, uncheck the **Only show unused fields** checkbox.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the only show unused fields checkbox unchecked.](../media/checkbox.png)](../media/checkbox.png#lightbox)

1. In the fields list, look for **Placeholder** field. Drag and drop it to the newly added tab.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the placeholder field.](../media/placeholder.png)](../media/placeholder.png#lightbox)

1. Now double select the **Placeholder** field on the form to open the field properties. Select the **Controls** tab on the dialog.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the controls tab.](../media/controls.png)](../media/controls.png#lightbox)

1. Now select**Add Control** and look for **Customer Summary** control in the list.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the add control button.](../media/add-control.png)](../media/add-control.png#lightbox)

1. Select the **Customer Summary** control and select**Add**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the customer summary control.](../media/customer-summary-control.png)](../media/customer-summary-control.png#lightbox)

1. Once the control is added, edit properties one by one. First, select edit icon for **Contact** property.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the edit contact button.](../media/edit-contact.png)](../media/edit-contact.png#lightbox)

1. In the dialog box that opens, set the **Bind to a value on a field** value to **contactid(SingleLine.Text)** and select**OK**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the bind to a value on a field set to contact ID.](../media/bind-value.png)](../media/bind-value.png#lightbox)

1. Now select the edit icon next to **Component** property.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the component edit icon.](../media/edit-component.png)](../media/edit-component.png#lightbox)

1. Set the **Bind to static options** property to **Life events** and select**OK**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the bind to static options property set life events.](../media/bind-static.png)](../media/bind-static.png#lightbox)

1. The Field Properties dialog should now look like below. Select **OK**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the field properties.](../media/field-properties.png)](../media/field-properties.png#lightbox)

1. Set the **CustomerSummary** radio buttons for **Web, Phone, Tablet** to true, and then select**OK**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the customer summary control settings.](../media/customer-summary-control-settings.png)](../media/customer-summary-control-settings.png#lightbox)

1. The form is ready now, select the **Home** menu on the ribbon and then select**Save** and **Publish**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the home menu with save and publish selected.](../media/publish.png)](../media/publish.png#lightbox)

1. Close the tab. This will close the classic editor.

1. Go back to the modern editor and select the newly created tab in the tree view. Ensure the properties are set as below.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the modern editor with the newly created tab selected and the properties set.](../media/modern-editor.png)](../media/modern-editor.png#lightbox)

1. **Save** and **Publish** the changes.

1. Launch **Unified customer profile** again from any contact record. Note the new tab reflect along with the **Life Event** control.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the newly added tab.](../media/tab-added.png)](../media/tab-added.png#lightbox)

## Task 2: Add a new life event type

In this task, we will extend the data model to add a new Life Event Type to the Life Event table, and note that it reflects in the **Unified customer profile**.

1.  In Power Apps, select **Dataverse** > **Tables** in the left sitemap. Then set the search dropdown to **Managed** and search for **Life event** table.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the search set to managed with a search for life event.](../media/managed-life-event.png)](../media/managed-life-event.png#lightbox)

1.  In the search results, select **Life event** table.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of life event table selected in the search results.](../media/life-event-table.png)](../media/life-event-table.png#lightbox)

1.  In the table columns tab, select**Life event type** column name to edit it. Then select**Edit choice** to add the new life moment type.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the edit choice button.](../media/edit-choice.png)](../media/edit-choice.png#lightbox)

1.  In the choice edit dialog, select**Add new item**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of add new item in the choice edit dialog box.](../media/add-new-item.png)](../media/add-new-item.png#lightbox)

1.  Type in **University Enrollment** in the new item row.

1.  Select the **...** next to the newly created row and select the **View More** option.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the ellipsis with view more selected.](../media/view-more.png)](../media/view-more.png#lightbox)

1.  It will open the optionset details. Copy the **Value** field and save it for the next steps.

    Your environment's value might be different from the value shown below.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the value field.](../media/value.png)](../media/value.png#lightbox)

1.  Select **Save** and then on **Done**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the save button and the done button.](../media/save-done.png)](../media/save-done.png#lightbox)

1.  Select **Done** on the table edit dialog as well.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the done button on the table edit dialog.](../media/table-edit-done.png)](../media/table-edit-done.png#lightbox)

1. Select **Save table**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the save table button.](../media/save-table.png)](../media/save-table.png#lightbox)

1. This should close the edit table view.

1. Now search for **Life event type config** table.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the search for life event type config.](../media/life-event-type-config.png)](../media/life-event-type-config.png#lightbox)

1. Select the **Life event type config** table from search results. It will show the details of the table. Select **Data** to load the data for the table.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the data button to load the table data.](../media/data.png)](../media/data.png#lightbox)

1. Select **+Add record**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the add record button.](../media/add-record.png)](../media/add-record.png#lightbox)

1. A new tab will open up. Set the following values to create a new Life event type config. Select **Save**.

	- **Name:** University Enrollment
	
	- **Type code:** Enter the value you copied in step 7 above
	
	- **Display order:** 1

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new life event type details.](../media/life-event-details.png)](../media/life-event-details.png#lightbox)

1. After the record is saved, select**Related** tab and then **Category types relations**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the related tab with category types relations selected.](../media/category-types.png)](../media/category-types.png#lightbox)

1. In the **Category types relations** tab, select**+New Category types relations** to create a new record.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of new category types relations button.](../media/new-category-types-relations.png)](../media/new-category-types-relations.png#lightbox)

1. Set the following values to create a new **Category types relations** record and select**Save**.

	- **Name:** University Enrollment category types relations

	- **Lifemomentcategory configurations:** Select **Education** record

	- **Life event type configurations:** Select **University Enrollment** record

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the category types relations general details.](../media/general-details.png)](../media/general-details.png#lightbox)

1. The Life event configurations are now complete.

1. Launch the **Unified customer profile** application, and select**Add new event**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the add new event button on the life events screen.](../media/add-new-event.png)](../media/add-new-event.png#lightbox)

1. Note the new Life event type reflect in the **Education** category.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the university enrollment added as a type in the education category.](../media/education-university-enrollment.png)](../media/education-university-enrollment.png#lightbox)

**Congratulations!** You have extended the Unified customer profile application to edit controls on the view and add new life event configurations.