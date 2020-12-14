Consider a scenario where you have a solution that includes an app, table, and a flow. You now want to export this solution from one tenant, which is the source, and import it to another tenant which is the destination. 

1. In the source tenant, sign into Power Apps and select **Solutions** which is available in the left vertical navigation and then click on export.

	> [!div class="mx-imgBorder"]
	> [![Select source tenant.](../media/export-solution-ssm.png)](../media/export-solution-ssm.png#lightbox)

1. Click on **Publish**. This will make sure all the changes made to this solution are part of this published solution. 

	> [!div class="mx-imgBorder"]
	> [![Publish the solution.](../media/publish-solution-ssm.png)](../media/publish-solution-ssm.png#lightbox)

1. Next click on **Run** to check for issues.

	> [!div class="mx-imgBorder"]
	> [![Select Run to check for issues](../media/check-issues-run-ssm.png)](../media/check-issues-run-ssm.png#lightbox)

	While it is running you should see the **Running…** right below your solution name.

	> [!div class="mx-imgBorder"]
	> [![Volunteer Request Running.](../media/check-issues-running-ssm.png)](../media/check-issues-running-ssm.png#lightbox)

1. Once the check is complete, and no issues have been found click on **Next**.

	> [!div class="mx-imgBorder"]
	> [![Save solution.](../media/click-next-saving-solution-ssm.png)](../media/click-next-saving-solution-ssm.png#lightbox)

1. You need to decide which environment this solution is being exported to. If it is a test or a production environment, then select **Managed** (recommended). If you are moving it to another development environment, then choose Unmanaged and click **Export**.

	> [!div class="mx-imgBorder"]
	> [![Select Managed or Unmanaged.](../media/select-managed-unmanaged-ssm.png)](../media/select-managed-unmanaged-ssm.png#lightbox)

    On the top left, you'll see a message stating the solution was exported and will download soon. Soon after that, a zipped file will be downloaded to your default download location. 

	> [!div class="mx-imgBorder"]
	> [![Solution was exported.](../media/solution-exported-label-ssm.png)](../media/solution-exported-label-ssm.png#lightbox)

	The zipped filename contains the solution name, if it is managed or unmanaged, and the version number.

	> [!div class="mx-imgBorder"]
	> [![Zipped file named the solution name, managed/unmanaged, and version.](../media/zipped-file-name-ssm.png)](../media/zipped-file-name-ssm.png#lightbox)

1. Now go to your destination tenant sign into Power Apps and select **Solutions** which is available in the left vertical navigation and then click on import.

	> [!div class="mx-imgBorder"]
	> [![Import the solution.](../media/select-import-ssm.png)](../media/select-import-ssm.png#lightbox)

1. If you receive an authentication window, simply type in your credentials to continue.

	> [!div class="mx-imgBorder"]
	> [![Type credentials into authentication window.](../media/authentication-window-ss.png)](../media/authentication-window-ss.png#lightbox)

1. Choose the zipped file that was exported.

	> [!div class="mx-imgBorder"]
	> [![Select the zipped file that was exported.](../media/exported-zip-ss.png)](../media/exported-zip-ss.png#lightbox)

1. Select **Next**.

	> [!div class="mx-imgBorder"]
	> [![select Next to import the solution.](../media/next-solution-import-ssm.png)](../media/next-solution-import-ssm.png#lightbox)

1. If solutions items are available, then you will see this window. If you have missed anything, for example, a Choice, then you will get an error message with details on what you are missing. Click **Next**.

	> [!div class="mx-imgBorder"]
	> [![Select Next to import the solution.](../media/click-next-import-solution-ssm.png)](../media/click-next-import-solution-ssm.png#lightbox)

1. Keep the **Enable an SDK message processing steps included in this solution** checked and then select **Import**.

	> [!div class="mx-imgBorder"]
	> [![Check enable SDK message processing steps included in this solution and Import.](../media/keep-box-checked-import-ssm.png)](../media/keep-box-checked-import-ssm.png#lightbox)

1. Wait until the solution importing process has been completed.

	> [!div class="mx-imgBorder"]
	> [![Solution importing.](../media/import-solution-ss.png)](../media/import-solution-ss.png#lightbox)

1. If you received any warnings, then you can click on the warning or download the log file.

	> [!div class="mx-imgBorder"]
	> [![Warning message received.](../media/warning-message-ss.png)](../media/warning-message-ss.png#lightbox)

You will now see your Solution imported successfully in the new tenant.

> [!div class="mx-imgBorder"]
> [![Successfully imported solution.](../media/solution-imported-successfully-ssm.png)](../media/solution-imported-successfully-ssm.png#lightbox)
