Consider a scenario where you have a solution that includes an app, table, and a flow. You now want to export this solution from one tenant, which is the source, and then import it to another tenant, which is the destination. 

1. In the source tenant, sign in to Power Apps and then select **Solutions**, which is available in the left vertical navigation. Select **Export**.

	> [!div class="mx-imgBorder"]
	> [![Select source tenant.](../media/export-solution-ssm.png)](../media/export-solution-ssm.png#lightbox)

1. Select **Publish**. This selection will make sure that all changes that are made to this solution are part of this published solution. 

	> [!div class="mx-imgBorder"]
	> [![Publish the solution.](../media/publish-solution-ssm.png)](../media/publish-solution-ssm.png#lightbox)

1. Select **Run** to check for issues.

	> [!div class="mx-imgBorder"]
	> [![Select Run to check for issues](../media/check-issues-run-ssm.png)](../media/check-issues-run-ssm.png#lightbox)

	While the check is running, you should see the **Running…** notification beneath your solution name.

	> [!div class="mx-imgBorder"]
	> [![Volunteer Request Running.](../media/check-issues-running-ssm.png)](../media/check-issues-running-ssm.png#lightbox)

1. When the check is complete, and no issues have been found, select **Next**.

	> [!div class="mx-imgBorder"]
	> [![Save solution.](../media/click-next-saving-solution-ssm.png)](../media/click-next-saving-solution-ssm.png#lightbox)

1. You need to decide which environment that this solution will be exported to. If it's a test or a production environment, then select **Managed** (recommended). If you're moving it to another development environment, select **Unmanaged** and then select **Export**.

	> [!div class="mx-imgBorder"]
	> [![Select Managed or Unmanaged.](../media/select-managed-unmanaged-ssm.png)](../media/select-managed-unmanaged-ssm.png#lightbox)

   In the upper left of the screen, you should see a message stating that the solution was exported and will download soon. Presently, a zipped file will be downloaded to your default download location. 

	> [!div class="mx-imgBorder"]
	> [![Solution was exported.](../media/solution-exported-label-ssm.png)](../media/solution-exported-label-ssm.png#lightbox)

	The zipped file name contains the solution name, if it's managed or unmanaged, and the version number.

	> [!div class="mx-imgBorder"]
	> [![Zipped file named the solution name, managed/unmanaged, and version.](../media/zipped-file-name-ssm.png)](../media/zipped-file-name-ssm.png#lightbox)

1. Go to your destination tenant, sign in to Power Apps, and then select **Solutions**, which is available in the left vertical navigation. Select **Import**.

	> [!div class="mx-imgBorder"]
	> [![Import the solution.](../media/select-import-ssm.png)](../media/select-import-ssm.png#lightbox)

1. If you receive an authentication window, enter your credentials to continue.

	> [!div class="mx-imgBorder"]
	> [![Type credentials into authentication window.](../media/authentication-window-ss.png)](../media/authentication-window-ss.png#lightbox)

1. Select the zipped file that was exported.

	> [!div class="mx-imgBorder"]
	> [![Select the zipped file that was exported.](../media/exported-zip-ss.png)](../media/exported-zip-ss.png#lightbox)

1. Select **Next**.

	> [!div class="mx-imgBorder"]
	> [![select Next to import the solution.](../media/next-solution-import-ssm.png)](../media/next-solution-import-ssm.png#lightbox)

1. If solution items are available, the following window will appear. If you have missed anything, for example, a choice, then you'll get an error message with details on what you are missing. Select **Next**.

	> [!div class="mx-imgBorder"]
	> [![Select Next to import the solution.](../media/click-next-import-solution-ssm.png)](../media/click-next-import-solution-ssm.png#lightbox)

1. Keep the **Enable any SDK message processing steps included in the solution** selected and then select **Import**.

	> [!div class="mx-imgBorder"]
	> [![Check enable SDK message processing steps included in this solution and Import.](../media/keep-box-checked-import-ssm.png)](../media/keep-box-checked-import-ssm.png#lightbox)

1. Wait until the solution importing process has been completed.

	> [!div class="mx-imgBorder"]
	> [![Solution importing.](../media/import-solution-ss.png)](../media/import-solution-ss.png#lightbox)

1. If you receive warnings, then you can select the warning or download the log file.

	> [!div class="mx-imgBorder"]
	> [![Warning message received.](../media/warning-message-ss.png)](../media/warning-message-ss.png#lightbox)

You'll now see your solution imported successfully in the new tenant.

> [!div class="mx-imgBorder"]
> [![Successfully imported solution.](../media/solution-imported-successfully-ssm.png)](../media/solution-imported-successfully-ssm.png#lightbox)
