In this exercise, you will be required to create a new question to the eligibility questionnaire. The question is required to capture data from the user and save it in the system but does not really impact the overall eligibility computation workflow. Hence, you would just be making changes to the portal to reflect a new question in the existing questionnaire.

## Task 1: Customize existing components and add new components in a solution 

In this task, you will reuse the existing solution that you created in Lab 1 and add a few components that will be customized to reflect the new question on the portal

1.  Navigate to the solution you created in Lab1 called **MVM in a Day** and click on **+Add Existing** and select **Table**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Add existing menu with table selected.](../media/add-table.png)](../media/add-table.png#lightbox)

1.  In the list that shows up, search for **Covid Vaccination Eligibility** table and click on **Next**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of covid vaccination eligibility table in list.](../media/eligibility-table.png)](../media/eligibility-table.png#lightbox)

1.  Once the table is added, click on **Select Components**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the select components feature.](../media/select-components.png)](../media/select-components.png#lightbox)

1.  In the list that appears, navigate to **Forms** tab and click checkbox for **Vaccination Management - Portal Web Form** in **Forms** tab and click on **Add**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the forms tab with the checkbox marked for vaccination management portal web form.](../media/checkbox.png)](../media/checkbox.png#lightbox)

1.  Click on **Publish All Customizations**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the publish all customizations feature.](../media/publish.png)](../media/publish.png#lightbox)

1.  Add new column with below values:

    **Column Name**: Are you a part of Paramilitary/Armed Forces

    **Type**: Yes/No

    Click on **Done**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new column details.](../media/new-column.png)](../media/new-column.png#lightbox)

1.  Once column is added, click on **Save Table**.

1.  Now navigate to **Forms** tab and select the **Vaccination Management - Portal Web Form**.

1.  Once the form opens up, navigate to **Table Columns** in the left navigation and click on **Work History**.

1. Click on + **Form Field** and select the newly created column called **Are you a part of paramilitary/armed forces**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the add form field button with the new column selected.](../media/form-field.png)](../media/form-field.png#lightbox)

1. The new column will show up on the form now.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the newly created column added to the form.](../media/form-column.png)](../media/form-column.png#lightbox)

1. Click on **Save** and then **Publish** to save the changes and then click **Back** to exit.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the save and publish buttons.](../media/save-publish.png)](../media/save-publish.png#lightbox)

1. Get back to solution page and click on **Publish All Customizations**.

## Task 2: Restart portal and verify your changes

1.  In the same browser where you have logged in to the lab environment, open a new tab and navigate to [https://admin.powerplatform.microsoft.com/](https://admin.powerplatform.microsoft.com/)

1.  In the navigation pane, click on **Resources** dropdown and then **Portals**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the resources dropdown menu with portals.](../media/portals.png)](../media/portals.png#lightbox)

1.  In the Search box, search for \<Your allocated environment Name\> and you can find the **Registration Portal** show up as a search result. Click on **...** and then **Manage**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of registration portal result with manage selected.](../media/manage.png)](../media/manage.png#lightbox)

1.  This should launch the Portal Admin Center in a new tab. In the Admin Center, click on **Portal Actions** and then **Restart Portal**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of portal actions with restart portal selected.](../media/restart.png)](../media/restart.png#lightbox)

1.  Once the portal restarts, navigate back to your portal page and follow the process of checking eligibility as done in Exercise 1. Follow through until you reach on the Step 2 of Eligibility questionnaire to verify your new question now shows up in the portal.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new question displayed in the portal.](../media/question-verified.png)](../media/question-verified.png#lightbox)

**Congratulations!** You have now understood how to add a new question to the Eligibility questionnaire and can track user responses in a Dataverse record.
