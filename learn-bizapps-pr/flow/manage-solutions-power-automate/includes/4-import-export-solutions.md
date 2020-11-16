Consider a scenario where you have a solution that includes a Microsoft Dataverse entity and its flow. You now want to export this solution from one tenant, which is the source, and import it to another tenant that is the destination.

1. In the source tenant, go to [Power Automate](https://flow.microsoft.com/?azure-portal=true). Then, on the left vertical navigation pane, select **Solutions**, select your solution, and then select **Export**.

	> [!div class="mx-imgBorder"]
	> [![Select source tenant](../media/select-solution-source-tenant-ssm.png)](../media/select-solution-source-tenant-ssm.png#lightbox)

1. Select **Publish**, which will make sure that all changes that were made to this solution are part of the published solution.

	> [!div class="mx-imgBorder"]
	> [![Publish the solution](../media/publish-solution-ssm.png)](../media/publish-solution-ssm.png#lightbox)

1. Select **Run** to check for issues.

	> [!div class="mx-imgBorder"]
	> [![Select Run to check for issues](../media/check-issues-run-ssm.png)](../media/check-issues-run-ssm.png#lightbox)

	While the check is running, the **Running...** notification should show below your solution name.

	> [!div class="mx-imgBorder"]
	> [![Volunteer Request Running](../media/check-issues-running-ssm.png)](../media/check-issues-running-ssm.png#lightbox)

1. When the check is complete, and if no issues have been found, select **Next**.

	> [!div class="mx-imgBorder"]
	> [![Save solution](../media/click-next-saving-solution-ssm.png)](../media/click-next-saving-solution-ssm.png#lightbox)

1. Decide which environment that this solution will be exported to. If it is a test or a production environment, then select **Managed (recommended)**. If you are moving it to another development environment, select *Unmanaged* and then select **Export**.

	> [!div class="mx-imgBorder"]
	> [![Select Managed or Unmanaged](../media/select-managed-unmanaged-ssm.png)](../media/select-managed-unmanaged-ssm.png#lightbox)

       In the upper-left corner of the screen, you'll see a message stating that the solution was exported and will download soon. Subsequently, a zipped file will be downloaded to your default download location.

	> [!div class="mx-imgBorder"]
	> [![Solution was exported](../media/solution-exported-label-ssm.png)](../media/solution-exported-label-ssm.png#lightbox)

	The zipped file name contains the solution name, if it is managed or unmanaged, and the version number.

	> [!div class="mx-imgBorder"]
	> [![Zipped file named the solution name, managed/unmanaged, and version](../media/zipped-file-name-ssm.png)](../media/zipped-file-name-ssm.png#lightbox)

1. Sign in to your destination tenant and go to [Power Automate](https://flow.microsoft.com/?azure-portal=true). On the left vertical navigation, select **Solutions** and then select **Import**.

	> [!div class="mx-imgBorder"]
	> [![Import the solution](../media/import-solution-ssm.png)](../media/import-solution-ssm.png#lightbox)

1. If you receive an authentication window, enter your credentials to continue.

	> [!div class="mx-imgBorder"]
	> [![Type credentials into authentication window](../media/authentication-window-ss.png)](../media/authentication-window-ss.png#lightbox)

1. Select the zipped file that was exported.

	> [!div class="mx-imgBorder"]
	> [![Select the zipped file that was downloaded](../media/select-downloaded-solution-ssm.png)](../media/select-downloaded-solution-ssm.png#lightbox)

1. Select **Next**.

	> [!div class="mx-imgBorder"]
	> [![select Next to import the solution](../media/next-solution-import-ssm.png)](../media/next-solution-import-ssm.png#lightbox)

1. If solution items are available, then you will see the following window. If you have missed anything, such as an option set, then you will get an error message with details on what you are missing. Select **Next**.

	> [!div class="mx-imgBorder"]
	> [![Select Next to import the solution](../media/click-next-import-solution-ssm.png)](../media/click-next-import-solution-ssm.png#lightbox)

1. Keep the **Enable an SDK message processing steps included in this solution** option selected and then select **Import**.

	> [!div class="mx-imgBorder"]
	> [![Check enable SDK message processing steps included in this solution and Import](../media/keep-box-checked-import-ssm.png)](../media/keep-box-checked-import-ssm.png#lightbox)

1. Wait until the solution importing process has been completed.

	> [!div class="mx-imgBorder"]
	> [![Solution importing](../media/import-solution-ss.png)](../media/import-solution-ss.png#lightbox)

1. If you have received any warnings, then you can select the warning or download the log file.

	> [!div class="mx-imgBorder"]
	> [![Warning message received](../media/warning-message-ss.png)](../media/warning-message-ss.png#lightbox)

You will now see that your solution has imported successfully in the new tenant.

> [!div class="mx-imgBorder"]
> [![Successfully imported solution](../media/imported-solution-ssm.png)](../media/imported-solution-ssm.png#lightbox)
