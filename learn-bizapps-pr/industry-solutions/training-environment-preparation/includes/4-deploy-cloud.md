In this exercise, you'll deploy Microsoft Cloud for Financial Services in your Microsoft 365 tenant.

## Task 1: Create a Power Apps portal

In this task, you'll create a Power Apps portal that you can use as a sample portal by the Customer onboarding capability.

1. While signed in to your Microsoft 365 tenant, open a new tab and then go to [https://make.powerapps.com](https://make.powerapps.com/?azure-portal=true).

1. Change your **Environment** from default to the trial environment that you created in the previous section.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Apps page in Power Apps, with the Environment box highlighted.](../media/trial-environment.png)](../media/trial-environment.png#lightbox)

1. In the left navigation, select **Apps** and then select **+ New app > Portal**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Apps page showing the New app button highlighted.](../media/new-app.png)](../media/new-app.png#lightbox)

1. Set the following new portal properties and then select **Create**.

    - **Name** - Woodgrove Banking Portal

    - **Address** - fsitrialdemo

1. Select **Use data from existing website record**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Portal from blank dialog, showing the Name and Address fields filled in.](../media/portal.png)](../media/portal.png#lightbox)

Your portal will provision in the background. This process will take several minutes, so you can pause before proceeding to the next task.

## Task 2: Enable advanced Teams integration

In this task, you'll enable advanced Microsoft Teams integration that is used in the Collaboration Manager for Loans application.

1. Using your tenant credentials, go to [https://make.powerapps.com](https://make.powerapps.com/?azure-portal=true) and select your environment. Select the settings icon and then select **Advanced settings**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Home page in Power Apps, with the settings icon selected and Advanced settings highlighted.](../media/advanced.png)](../media/advanced.png#lightbox)

1. The Dynamics application will launch in another tab. Select **Settings > Administration**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Dynamics 365 with Settings selected and Administration highlighted.](../media/administration.png)](../media/administration.png#lightbox)

1. Select **System Settings**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Administration with System Settings highlighted.](../media/system.png)](../media/system.png#lightbox)

1. The **System Settings** window will open. Set both **Microsoft Teams Integration** checkboxes to **Yes** and then select **OK**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the General tab on the System Settings page, showing both Microsoft Teams Integration features enabled.](../media/teams.png)](../media/teams.png#lightbox)

## Task 3: Deploy Microsoft Cloud for Financial Services

In this task, you'll deploy all Microsoft Cloud for Financial Services capabilities.

1. While signed in to your Microsoft 365 tenant, open a new tab and then go to [https://aka.ms/solutioncenter](https://aka.ms/solutioncenter/?azure-portal=true) to access the Microsoft Cloud Solution Center. Select the **Microsoft Cloud for Financial Services** button to begin setup.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Microsoft Cloud Solution Center with Microsoft Cloud for Financial Services quick start button highlighted.](../media/cloud.png)](../media/cloud.png#lightbox)

1. Select the **Unified customer profile** capability.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Microsoft Cloud Solution Center with Unified customer profile highlighted.](../media/unified.png)](../media/unified.png#lightbox)

1. In the **Filter by capability** dropdown menu, select **All**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Microsoft Cloud for Financial Services with Filter by capability expanded and the All option highlighted.](../media/capability.png)](../media/capability.png#lightbox)

1. Select the **Add all FSI Capabilities** checkbox and then clear the **Customer intelligence** capability. Select **Deploy**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Add all FSI Capabilities checkbox selected and Customer intelligence cleared.](../media/add-all.png)](../media/add-all.png#lightbox)

1. In the **Additional components** section, select the **Sample data** and **Sample portal** checkboxes and then select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Additional components with Sample data and Sample portal selected.](../media/sample.png)](../media/sample.png#lightbox)

1. In the **Enter Dataverse environment** dropdown menu, select your environment. Select the **Terms of service** checkbox and then select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Set up new deployment with the Enter Dataverse environment dropdown menu highlighted.](../media/deployment.png)](../media/deployment.png#lightbox)

1. All pre-deployment dependencies will be installed and set up. Select **Deploy** to complete the installation.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Configure pre-deployment dependencies, with the Deploy button highlighted.](../media/deploy.png)](../media/deploy.png#lightbox)

Congratulations, you've now deployed Microsoft Cloud for Financial Services. The deployment will take several hours to complete. You can monitor this screen to check the deployment status, or you can view the status of the apps by going to [https://aka.ms/ppac](https://aka.ms/ppac/?azure-portal=true).
