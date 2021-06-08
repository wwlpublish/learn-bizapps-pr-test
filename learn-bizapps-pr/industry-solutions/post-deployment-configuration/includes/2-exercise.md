Microsoft Vaccination Management (MVM) ships with a handful of workflows to automate certain business processes. After deploying the solution, you must verify and activate the workflows based on your customer requirements. Most of the workflows are automatically activated.

In this exercise, you'll be playing the role of a System Administrator and explore the included MVM workflows and activate the inactive workflows.

Before beginning this exercise:

1. Navigate to [Power Apps](https://make.powerapps.com/?azure-portal=true) (recommend Incognito or InPrivate session).

1. Sign in using the credentials supplied in the training for your user.

1. Select the correct environment from the upper right **Environment** drop-down list.

## Explore and learn to activate the inactive workflows

1. In the left pane, select Solutions and then you can view the list of solutions deployed in the environment.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the navigation pane with Solutions highlighted.](../media/2-1-solutions.png)](../media/2-1-solutions.png#lightbox)

1. On the **Solutions** page, select **Vaccination Management Workflows**. This solution consists of all the workflows shipped as part of MVM.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Vaccination Management Workflows in the list of solutions.](../media/2-2-workflows.png)](../media/2-2-workflows.png#lightbox)

1. Verify the **status** on each of the workflows. If any of them are turned off, open the workflow, verify the steps, and select the **Activate** button to turn on the respective workflow as shown in the next steps.

1. For example, **Vaccination--Eligibility Phase Determination** workflow is turned off by default. Select to open the **Vaccination--Eligibility Phase Determination** workflow in a new tab in your browser.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Vaccination – Eligibility Phase Determination workflow with status set to Off.](../media/2-3-eligibility.png)](../media/2-3-eligibility.png#lightbox)

1. In the workflow definition, review the logic in the lower part of the screen. This workflow contains the logic to determine eligibility and sets a phase. After reviewing the logic, select **Activate**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Vaccination - Eligibility Phase Determination workflow with the Activate button highlighted.](../media/2-4-activate.png)](../media/2-4-activate.png#lightbox)

**Congratulations!** You've explored and activated all the MVM workflows.
