In this exercise, you will mimic onboarding the MVM solution for a new locale/geo that has different COVID vaccination eligibility rules. In that case, you would be required to override most of the existing portal behaviour and replace it with new rules. You would also be required to edit the overall eligibility workflow that evaluates if a person is eligible according to the configured rules so that the new set of rules are honoured during eligibility computation.

## Task 1: Customize existing components and add new components in a solution 

In this task, you will re-use the existing solution that you created in Lab1 and add a few components that will be customized to reflect the new question on the portal

1.  Navigate to the solution you created in Lab1 called **MVM in a Day** and search for **Covid Vaccination Eligibility** table and click on it.

1.  Once the table opens, click on **Add column** and set the following details:

    **Display Name** : Question 1

    **Data type** : Yes/No

    Click on **Done**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the table with the add column details.](../media/add-column.png)](../media/add-column.png#lightbox)

1.  Once column is added, click on **Save Table**.

1.  Repeat steps 2 to 3 for adding another column with following details:

	**Display Name** : Question 2
	
	**Data type** : Yes/No

1.  This is how your table **Columns** should look like now.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of how the table column show appear.](../media/table-column-view.png)](../media/table-column-view.png#lightbox)

1.  Click on solution name **MVM In A Day** to navigate back and **Publish all customizations**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of publish all customizations button.](../media/publish-customizations.png)](../media/publish-customizations.png#lightbox)

1.  Once published, click again on **Covid Vaccination Eligibility** table in the solution.

1.  In the list that appears, navigate to **Forms** tab and click **Vaccination Management - Portal Web Form**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the forms tab with vaccination management portal web form selected.](../media/portal-web-form.png)](../media/portal-web-form.png#lightbox)

1.  This should launch the form for editing. Now click on **First Dose** tab and then **+Component** in the navigation bar.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of add component button on the first dose tab.](../media/first-dose-component.png)](../media/first-dose-component.png#lightbox)

1. Now click **1-column tab** from the left navigation and see it reflect on the form as shown.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the 1 column tab with first dose tab displayed.](../media/1-column-tab.png)](../media/1-column-tab.png#lightbox)

1. Now click on the **New Tab** and update the **Label** to "New Questions".

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new tab label updated to new questions.](../media/new-questions.png)](../media/new-questions.png#lightbox)

1. Now click on **+Form Field** in the navigation bar and click on **Question1** and **Question2** to add them to the newly created tab.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of question 1 and question 2 selected to add to the new tab.](../media/new-question-1-2.png)](../media/new-question-1-2.png#lightbox)

1. Once added, here is how your form tab will look like:

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new questions tab with questions added.](../media/form-tab.png)](../media/form-tab.png#lightbox)

1. Click on **Save** and then **Publish**.

1. Click on **Back** to exit from the form. Then click on solution name and **Publish all customizations**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the publish all customizations button for the solution.](../media/publish-all.png)](../media/publish-all.png#lightbox)

## Task 2: Edit portal webform steps to show your page

In this task, you will edit the portal settings to reflect a new page with your questions. While you move from one page to the other on the portal, you are essentially navigating from one tab to the other on the form. To achieve this, each tab on the form is bound as a web form step on the portal. Introducing a new page requires changing the flow of the tabs and injecting a web form step in between. And that is exactly what we would do in this task. The original form step sequence is **Welcome** - **WorkHistory** followed by other tabs. You will alter the sequence to **Welcome** - **New Questions** - **WorkHistory** followed by other tabs.

1.  Launch **web.powerapps.com** using your user credentials and ensure the **Environment** is showing up correctly.

1.  Click on **Apps** and locate **Portal Management** app, click on **...** and **Play**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the portal management app play feature.](../media/portal-management-play.png)](../media/portal-management-play.png#lightbox)

1.  This will launch the **Portal Management** app in another tab.

1.  In the **Portal Management** app, click on **Web Forms** in the left navigation bar.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the web forms in the left navigation bar.](../media/web-forms.png)](../media/web-forms.png#lightbox)

1.  In the list that appears, click on **Vaccination Management - Eligibility**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of vaccination management eligibility in the active web forms list.](../media/vaccination-management-eligibility.png)](../media/vaccination-management-eligibility.png#lightbox)

1.  Once the web form opens, click on the start step **Welcome** to open the web form step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the welcome button in the web form.](../media/welcome.png)](../media/welcome.png#lightbox)

1.  Web form step should open up. In the start step value that shows **Work History**,click on **X** to clear the value and then click on search icon to create a new Web form step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the clear work history step.](../media/clear-work-history.png)](../media/clear-work-history.png#lightbox)

1.  Click on **New Web Form Step** to launch a create form for web form step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new web form step button.](../media/new-web-form-step.png)](../media/new-web-form-step.png#lightbox)

1.  Set following values in the Web Form Step and click **on Save**.

    Name : **New Questions**

    Web Form : **Vaccination Management - Eligibility**

    Type : **Load Form**

    Target Entity Logical Name : **COVID Vaccination Eligibility**

    Next Step : **Work History**

    Move Previous Permitted : **Yes**

    Enable Entity Permissions : **Yes**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the values in the web form step.](../media/image.png)](../media/image.png#lightbox)

1. Now navigate to **Form Definition** tab on the form and set the following values and then click on **Save and Close**.

    Form Name : **Vaccination Management - Portal Web Form**

    Tab Name : **New Questions**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the form name and tab name.](../media/web-form-values.png)](../media/web-form-values.png#lightbox)

1. You will land on the **Welcome** web form step again. Now set the Next step to the web form that you just created - **New Questions**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the next step set to new questions.](../media/form-definition-values.png)](../media/form-definition-values.png#lightbox)

1. Once done, **Save** the form and close.

## Task 3: Edit workflow to change eligibility logic

In this task you will edit the current eligibility logic to take into account the responses to your new questions and compute eligibility accordingly.

1.  Navigate back to your **MVM in a Day** solution and click on **+Add existing** and select **Process**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the add existing menu with process selected.](../media/set-new-questions.png)](../media/set-new-questions.png#lightbox)

1.  Search for 'Eligibility Phase'. Select the process named **Vaccination - Eligibility Phase Determination** and click on **Add**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the search for eligibility phase with vaccination eligibility phase determination selected.](../media/add-process.png)](../media/add-process.png#lightbox)

1.  Once added, click on the process **Vaccination - Eligibility Phase Determination.** This will launch the process designer in a new tab.

1.  Click on **Deactivate** button in the top ribbon. In the dialog that opens, click on **Deactivate**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the deactivate button.](../media/add-eligibility-phase.png)](../media/add-eligibility-phase.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the deactivate confirmation window.](../media/deactivate.png)](../media/deactivate.png#lightbox)

    Now the process designer will open up with the editable version of the Process.

1.  In the process designer, click on **Insert** and then select **After Step**. If it is pre-selected, then simply move to the next step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the insert menu with after step selected.](../media/insert-after-step.png)](../media/insert-after-step.png#lightbox)

1.  Then click on the **Otherwise if** written on the step that says **Phase 2**. This will highlight the whole conditional step as shown below.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the otherwise if with the conditional step selected.](../media/conditional-step.png)](../media/conditional-step.png#lightbox)

1.  Once the step is selected, click on **Add Step - Conditional Branch.** This will insert a new step post the selected conditional step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the add step menu with conditional branch selected.](../media/conditional-branch.png)](../media/conditional-branch.png#lightbox)

1.  The step appears in the workflow as shown below. Click on **\<condition\>(click to configure)**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the covid vaccination eligibility step in the workflow.](../media/configure-condition.png)](../media/configure-condition.png#lightbox)

1.  In the dialog box that opens, begin selecting the first condition. Set Primary entity dropdown to **COVID Vaccination Eligibility**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the primary entity set to covid vaccination eligibility.](../media/primary-entity.png)](../media/primary-entity.png#lightbox)

1. Now click on the next dropdown and select **Question 1** from the list.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the dropdown menu with question 1 selected.](../media/question-1.png)](../media/question-1.png#lightbox)

1. Add the following conditions and select **Equals**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the conditions added and equals selected.](../media/equals.png)](../media/equals.png#lightbox)

1. Now click on the **...** to select values from the options shown.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the ellipsis button to select values.](../media/ellipsis.png)](../media/ellipsis.png#lightbox)

1. In the dialog that pops up, select **Yes**, and then click on **\>\>\>** and then on **OK**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the select values window with yes selected.](../media/select-values.png)](../media/select-values.png#lightbox)

1. This is how your workflow step will look like now.

	> [!div class="mx-imgBorder"]
	> [![Screenshot example of the workflow step.](../media/workflow.png)](../media/workflow.png#lightbox)

1. Repeat steps 9-13 for **Question 2**. This is how your workflow step will look like after you are done. Click on **Save and Close**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the save and close button.](../media/save-close.png)](../media/save-close.png#lightbox)

1. Once the dialog closes, your workflow designer should look like below screenshot. Now select the row shown below and click on it. Then click on **Add step** - **Update record**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the select this row and click add step row.](../media/add-step.png)](../media/add-step.png#lightbox)

1. In the window that opens, set the **Phase** to 'Phase 3' as shown below and click **Save and Close**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the phase set to phase 3 and the save and close button.](../media/phase-3.png)](../media/phase-3.png#lightbox)

1. This is how your final workflow looks like. Click **Save** and then click **Activate**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot example of the final workflow.](../media/activate.png)](../media/activate.png#lightbox)

## Task 4: Restart portal and verify your changes

1.  In the same browser where you have logged in to the lab environment, open a new tab and navigate to [**https://admin.powerplatform.microsoft.com/**](https://admin.powerplatform.microsoft.com/)

1.  In the navigation pane, click on **Resources** dropdown and then **Portals**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the resources dropdown with portals selected.](../media/portals.png)](../media/portals.png#lightbox)

1.  In the Search box, search for \<Your allocated environment Name\> and you can find the **Registration Portal** show up as a search result. Click on **...** and then **Manage**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the registration portal in the search results with manage selected.](../media/manage-registration-portal.png)](../media/manage-registration-portal.png#lightbox)

1.  This should launch the Portal Admin Center in a new tab. In the Admin Center, click on **Portal Actions** and then **Restart Portal**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the portal actions menu with restart option.](../media/restart-portal-action.png)](../media/restart-portal-action.png#lightbox)

1.  Once the portal restarts, navigate back to your portal page and follow the process of checking eligibility as done in Exercise 1. Follow through till you reach on the Step 2 of Eligibility questionnaire to verify your new question now shows up in the portal.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new questions added to the portal.](../media/verify-question.png)](../media/verify-question.png#lightbox)

**Congratulations!** You have created a new eligibility questionnaire and plugged it in to fire in the eligibility process according to the response.

