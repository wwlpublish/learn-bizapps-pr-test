Consider a scenario where you have a solution that includes an app, table, and a flow. You now want to export this solution from one tenant, which is the source, and then import it to another tenant, which is the destination.

1. In the source tenant, sign in to Power Apps and then select **Solutions**, which is available in the left vertical navigation. Select **Export**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps Solutions page with Volunteer Request selected and the Export button highlighted.](../media/export-solution-ssm.png)](../media/export-solution-ssm.png#lightbox)

1. Select **Publish**. This selection will make sure that all changes that are made to this solution are part of this published solution.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Before you export dialog with the Publish button highlighted.](../media/publish-solution-ssm.png)](../media/publish-solution-ssm.png#lightbox)

1. Select **Run** to check for issues.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Before you export dialog with the Run button highlighted.](../media/check-issues-run-ssm.png)](../media/check-issues-run-ssm.png#lightbox)

    While the check is running, you should see the **Running…** notification beneath your solution name.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Check for issues with Volunteer Request Running highlighted.](../media/check-issues-running-ssm.png)](../media/check-issues-running-ssm.png#lightbox)

1. When the check is complete, and no issues have been found, select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Before you export dialog with the Next button highlighted.](../media/click-next-saving-solution-ssm.png)](../media/click-next-saving-solution-ssm.png#lightbox)

1. You need to decide which environment that this solution will be exported to. If it's a test or a production environment, then select **Managed** (recommended). If you're moving it to another development environment, select **Unmanaged** and then select **Export**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Export this solution dialog with Export as set to Managed and the Export button highlighted.](../media/select-managed-unmanaged-ssm.png)](../media/select-managed-unmanaged-ssm.png#lightbox)

	> [!NOTE]
	> Solution Version numbers are used to keep track of the functionality contained in a particular solution release. Versioning is used in the Power Platform to determine if code being imported is a solution or a patch. Power Platform solution versions are in the format \<major\>.\<minor\>.\<build\>.\<revision\>. When you create a new version, you will be asked to enter the version number. This defaults to 1.0.0.0 and auto increments based on the Solution update. An update must have a higher major, minor, build or revision number than the parent solution. For example, for a base solution version 1.0.0.0, a small update could be a version 1.0.0.1 or a slightly more significant update could have version 1.0.1.0. A substantially more significant update could be version 2.2.0.0.

   In the upper left of the screen, you should see a message stating that the solution was exported and will download soon. Presently, a zipped file will be downloaded to your default download location.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Power Automate with the message Volunteer Request was exported and will download soon.](../media/solution-exported-label-ssm.png)](../media/solution-exported-label-ssm.png#lightbox)

    The zipped file name contains the solution name, if it's managed or unmanaged, and the version number.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of zipped file named VolunteerRequest_1_0_0_1_managed.zip.](../media/zipped-file-name-ssm.png)](../media/zipped-file-name-ssm.png#lightbox)

1. Go to your destination tenant, sign in to Power Apps, and then select **Solutions**, which is available in the left vertical navigation. Select **Import**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps Solutions page with the Import button highlighted.](../media/select-import-ssm.png)](../media/select-import-ssm.png#lightbox)

1. If you receive an authentication window, enter your credentials to continue.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Microsoft "Pick an account" authentication window.](../media/authentication-window-ss.png)](../media/authentication-window-ss.png#lightbox)

1. Select the zipped file that was exported.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Open dialog showing the zipped file that was exported.](../media/exported-zip-ss.png)](../media/exported-zip-ss.png#lightbox)

1. Select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Import Solution wizard Select Solution Package with the VolunteerRequest file selected and the Next button highlighted.](../media/next-solution-import-ssm.png)](../media/next-solution-import-ssm.png#lightbox)

1. If solution items are available, the following window will appear. If you have missed anything, for example, a choice, then you'll get an error message with details on what you are missing. Select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Import Solution wizard Solution Information with the Next button highlighted.](../media/click-next-import-solution-ssm.png)](../media/click-next-import-solution-ssm.png#lightbox)

1. Keep the **Enable any SDK message processing steps included in the solution** selected and then select **Import**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Import Solution wizard Import Options with "Enable SDK message processing..." selected and the Import button highlighted.](../media/keep-box-checked-import-ssm.png)](../media/keep-box-checked-import-ssm.png#lightbox)

1. Wait until the solution importing process has been completed.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Import Customizations window with the message Importing customizations. Please wait for the operation to complete.](../media/import-solution-ss.png)](../media/import-solution-ss.png#lightbox)

1. If you receive warnings, then you can select the warning or download the log file.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Import Solution page with a warning message.](../media/warning-message-ss.png)](../media/warning-message-ss.png#lightbox)

You'll now see your solution imported successfully in the new tenant.

> [!div class="mx-imgBorder"]
> [![Screenshot of Solutions list with Volunteer Request highlighted.](../media/solution-imported-successfully-ssm.png)](../media/solution-imported-successfully-ssm.png#lightbox)
