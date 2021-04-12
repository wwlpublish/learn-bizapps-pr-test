In this exercise, you will export a solution containing a custom connector into GitHub using the Power Platform GitHub actions.

> [!IMPORTANT]
> Use a test environment with Microsoft Dataverse provisioned. If you do not have one you can sign up for the [community plan](https://powerapps.microsoft.com/communityplan/?azure-portal=true). A GitHub account is also required to complete the exercise. You can sign up for one for free at [GitHub.com](https://GitHub.com/?azure-portal=true).

## Task 1: Import solution

In this task, you will import an unmanaged solution that contains a Contoso Invoicing custom connector. You will use this connector to complete the tasks in this exercise.

1.  Navigate to [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true) and make sure you are in the correct environment.

1.  Select **Solutions** and select **Import**.

1.  Select **Browse**.

1.  Select the ContosoInvoicingALM_1_0_0_0.zip solution and select **Open**.

1.  Select **Next**.

1.  Select **Import** and wait for the import to complete. You should get a success message after the import completes.

1.  Select **Publish all customizations** and wait for the publish to complete.

1.  Select to open the **Contoso Invoicing - ALM** solution you imported.

1.  You should see the **Contoso Invoicing - ALM** custom connector component.

1. In the upper right corner of the screen select the Settings icon and choose Session details.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting session details.](../media/exercise-1.png)](../media/exercise-1.png#lightbox)

1. In the Power Apps session details dialog, select Instance url value and copy it for use later in the exercise.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing session details and where to find the instance U R L.](../media/exercise-2.png)](../media/exercise-2.png#lightbox)

## Task 2: Create a GitHub repository

1.  Navigate to [GitHub](https://GitHub.com/?azure-portal=true) and select **Create repository**.

1.  Type ContosoInvoiceALM for the repository name.

1.  Select Add a README file.

1.  Select **Create repository**.

1.  In the new repository, select the **Settings** icon.

1.  Select **Secrets**. Secrets are environment variables that are encrypted. Anyone with collaborator access to this repository can use these secrets for Actions. You will create three secrets that will ensure our action we create does not have any sensitive information in it.

1.  Select **New repository secret**.

1.  Enter **environment** in the **Name** field.

1.  Paste your environment URL you copied in the last task, in the **Value** field.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing adding a new action secret.](../media/exercise-3.png)](../media/exercise-3.png#lightbox)

1. Select **Add Secret**.

1. Add another secret with a name of **user** with the value containing the **email** of the account you use to access the environment.

1. Add another secret with a name of **password** with the value containing the **password** of the account you use to access the environment.

1. After adding the secrets your list of values should look like the following:

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing the three actions we added environment, password, user.](../media/exercise-4.png)](../media/exercise-4.png#lightbox)

## Task 3: Create a GitHub Action

1.  In the repository navigation, select the **Action** menu item.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting actions.](../media/exercise-5.png)](../media/exercise-5.png#lightbox)

1.  Select the **setup a workflow yourself**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing set up your own workflow being selected.](../media/exercise-6.png)](../media/exercise-6.png#lightbox)

1.  In the **Edit new file** area clear out the YAML that was provided.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing clearing out the new action contents.](../media/exercise-7.png)](../media/exercise-7.png#lightbox)

1.  Open the provided export-and-branch-solution.yml file and paste the contents into the Edit new file area.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing pasting in the new action steps.](../media/exercise-8.png)](../media/exercise-8.png#lightbox)

1.  You have added the following four steps 1) Who am I to test connection, 2) Export solution, 3) Unpack the solution and 4) Create a branch and check in the solution files.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing the steps outlined above.](../media/exercise-9.png)](../media/exercise-9.png#lightbox)

1.  Select **Start commit** on right side, then select **Commit new file**. This will save your action you built.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing start commit and commit new file actions being selected.](../media/exercise-10.png)](../media/exercise-10.png#lightbox)

1.  Your action has been saved and is ready to run.

## Task 4: Run the export action

1.  Navigate to repository **Actions**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting actions to see the list.](../media/exercise-11.png)](../media/exercise-11.png#lightbox)

1.  Select the **export-and-branch-solution** action and then select **Run workflow**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting the action you just created and selecting run workflow.](../media/exercise-12.png)](../media/exercise-12.png#lightbox)

1.  With Use workflow from **main** branch-selected select **Run workflow**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting run workflow.](../media/exercise-13.png)](../media/exercise-13.png#lightbox)

1.  Monitor the workflow progress until it has completed successfully.

	> [!div class="mx-imgBorder"]
	> [![Screenshot monitoring the progress of the run of the workflow.](../media/exercise-14.png)](../media/exercise-14.png#lightbox)

1.  Select **Code** in the navigation and then select **branches**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing looking at code and looking at the number of branches and selecting the branches list.](../media/exercise-15.png)](../media/exercise-15.png#lightbox)

1.  You should see the branch that was created by the GitHub Action execution. Currently this is not merged in with your main branch. Select **New pull request** to start the merge process.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting new pull request for the branch that was just created.](../media/exercise-16.png)](../media/exercise-16.png#lightbox)

1.  In the comments area type **Initial version of connector.**

1.  Select the **Create pull request**.

1.  Now typically someone would review and merge, but since it is just you, you should approve the pull request yourself.

1. Expand **Merge pull request** and select **Squash and merge.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting the merge request.](../media/exercise-17.png)](../media/exercise-17.png#lightbox)

1. Select **Squash and merge** then select **Confirm squash and merge.**

1. Your branch with your changes has now been merged.

1. Select Code and select **solutions/ContosoInvoiciningALM**. This folder contains the solution files that were created. You can browse content of this folder what was extracted from the solution and stored as individual files.

	> [!div class="mx-imgBorder"]
	> [![Screenshot looking at the contents of the repository after the merge.](../media/exercise-18.png)](../media/exercise-18.png#lightbox)

## Task 5: Change and record connector definitions

1.  Navigate to [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true) and make sure you are in the correct environment.

1.  Select **Solutions** then select **Contoso Invoicing - ALM** solution.

1.  Select ... next to the custom connector component and select **Edit**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing editing the connector to make a change.](../media/exercise-19.png)](../media/exercise-19.png#lightbox)

1.  Change **Icon background color** to **#0066ff** and select **Update connector**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing selecting update connector after changing the color.](../media/exercise-20.png)](../media/exercise-20.png#lightbox)

1.  Repeat steps 1-12 of the **Task 4** to run the workflow, create new pull request, and merge the code into the main branch.

1.  Select **Code** in the navigation then select the pull request name to open the details.

	> [!div class="mx-imgBorder"]
	> [![Screenshot from the pull request.](../media/exercise-21.png)](../media/exercise-21.png#lightbox)

1.  Verify the recorded change in icon color from #007ee5 to #0066ff

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing the change of the icon color in the difference.](../media/exercise-22.png)](../media/exercise-22.png#lightbox)

> [!NOTE]
> There could be other automatic changes applied when you save the connector, for example, icon format may change from jpeg to png.

You now have an automated process to export and record your custom connector changes in a source control system.