**The estimated time to complete the lab is 45 minutes**

In this lab, you will create the **Sales Monitoring** dashboard.

In this lab, you learn how to:

- Pin visuals to a dashboard

- Use Q&A to create dashboard tiles

- Configure a dashboard tile alert

### Lab story

This lab is one of many in a series of labs that was designed as a complete story from data preparation to publication as reports and dashboards. You can complete the labs in any order. However, if you intend to work through multiple labs, for the first 10 labs, we suggest you do them in the following order:

1. [Prepare data in Power BI Desktop](https://docs.microsoft.com/learn/modules/get-data/lab-prepare/?azure-portal=true)

1. [Load data in Power BI Desktop](https://docs.microsoft.com/learn/modules/clean-data-power-bi/8-lab/?azure-portal=true)

1. [Model data in Power BI Desktop, part 1](https://docs.microsoft.com/learn/modules/design-model-power-bi/8-lab/?azure-portal=true)

1. [Model data in Power BI Desktop, part 2](https://docs.microsoft.com/learn/modules/design-model-power-bi/9-lab/?azure-portal=true)

1. [Create DAX calculations in Power BI Desktop, part 1](https://docs.microsoft.com/learn/modules/create-measures-dax-power-bi/6-lab/?azure-portal=true)

1. [Create DAX calculations in Power BI Desktop, part 2](https://docs.microsoft.com/learn/modules/create-measures-dax-power-bi/8-lab/?azure-portal=true)

1. [Design a report in Power BI Desktop, part 1](https://docs.microsoft.com/learn/modules/visuals-power-bi/8-lab/?azure-portal=true)

1. [Design a report in Power BI Desktop, part 2](https://docs.microsoft.com/learn/modules/data-driven-story-power-bi/13-lab/?azure-portal=true)

1. **Create a Power BI dashboard** << You are here. This is the lab for the current module.

1. [Perform data analysis in Power BI Desktop](https://docs.microsoft.com/learn/modules/ai-visuals-power-bi/5-lab/?azure-portal=true)

1. [Create a Power BI paginated report](https://docs.microsoft.com/learn/modules/create-paginated-reports-power-bi/6-lab/?azure-portal=true)

> [!NOTE]
> Each lab starts with a PBIX file that has all of the previous lab work completed. If you should lose your work for any reason, you can open the PBIX file that includes the progress up to that point from the folder indicated at the beginning of the next lab.

## Exercise 1: Create a dashboard

In this exercise, you will create the **Sales Monitoring** dashboard. The completed dashboard will look like the following:

> [!div class="mx-imgBorder"]
> [![Screenshot of the Sales Monitoring dashboard.](../media/lab-1-ss.png)](../media/lab-1-ss.png#lightbox)

### **Task 1: Get started – Sign in**

In this task you'll set up the environment for the lab by signing in to Power BI.

> [!Important]
> If you have already signed in to Power BI in a previous lab, continue from the next task.

1. To open Microsoft Edge, on the taskbar, select the Microsoft Edge program shortcut.

1. In the Microsoft Edge browser window, navigate to [https://powerbi.com](https://powerbi.com).

    > [!Tip]
    > You can also use the Power BI Service favorite on the Microsoft Edge favorites bar.

1. Select **Sign In** (located at the top-right corner).

1. Enter the account details provided to you.

1. If prompted to update the password, reenter the provided password, and then enter and confirm a new password.

    > [!Important]
    > Be sure to record your new password.

1. Complete the sign in process.

1. If prompted by Microsoft Edge to stay signed in, select **Yes**.

1. In the Microsoft Edge browser window, in the Power BI service, in the **Navigation** pane, expand **My Workspace**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Navigation pane with the My workspace expand icon highlighted.](../media/lab-1-a-ssm.png)](../media/lab-1-a-ssm.png#lightbox)

1. Leave the Microsoft Edge browser window open.

### **Task 2: Get started – Open report**

In this task you'll set up the environment for the lab by opening the starter report.

> [!Important]
> If you are continuing on from the previous lab (and you completed that lab successfully), do not complete this task. Instead, continue from the next task.

1. To open the Power BI Desktop, on the taskbar, select the Microsoft Power BI Desktop shortcut.

1. To close the getting started window, at the top-left of the window, select **X**.

1. If Power BI Desktop is not signed in to the Power BI service, at the top-right, select **Sign In**.

1. Complete the sign in process using the same account used to sign in to the Power BI service.

1. To open the starter Power BI Desktop file, select the **File** ribbon tab to open the backstage view.

1. Select **Open Report**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the File menu expanded and the Open report option highlighted.](../media/lab-1-b-ssm.png)](../media/lab-1-b-ssm.png#lightbox)

1. Select **Browse Reports**.

1. In the **Open** window, navigate to the **D:\DA100\Labs\09-create-power-bi-dashboard\Starter** folder.

1. Select the **Sales Analysis** file.

1. Select **Open**.

1. Close any informational windows that may open.

1. To create a copy of the file, select the **File** ribbon tab to open the backstage view.

1. Select **Save As**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the File menu expanded and the Save as option highlighted.](../media/lab-1-c-ssm.png)](../media/lab-1-c-ssm.png#lightbox)

1. If prompted to apply changes, select **Apply**.

1. In the **Save As** window, navigate to the **D:\DA100\MySolution** folder.

1. Select **Save**.

### **Task 3: Get started – Publish the report**

In this task you'll set up the environment for the lab by creating a dataset.

> [!Important]
> If you've already published the report in the **Design a report in Power BI Desktop, Part 2** lab, continue from the next task.

1. In the Microsoft Edge browser window, in the Power BI service, in the **Navigation** pane, at the bottom, select **Get Data**.

1. In the **Files** tile, select **Get**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Files tile with the Get button highlighted.](../media/lab-1-d-ssm.png)](../media/lab-1-d-ssm.png#lightbox)

1. Select the **Local File** tile.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power B I Local File tile.](../media/lab-1-e-ssm.png)](../media/lab-1-e-ssm.png#lightbox)

1. In the **Open** window, navigate to the **D:\DA100\Labs\design-report-in-power-bi-desktop-enhanced\Solution** folder.

1. Select the **Sales Analysis.pbix** file, and then select **Open**.

1. If prompted to replace the dataset, select **Replace**.

### **Task 4: Create a dashboard**

In this task you'll create the **Sales Monitoring** dashboard. You'll pin a visual from the report, and add a tile based on an image data URI, and use Q&A to create a tile.

1. In the Microsoft Edge browser window, in the Power BI service, open the **Sales Analysis** report.

1. In the **Overview** page, set the **Year** slicer to **FY2020**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Year slicer set to F Y 2020.](../media/lab-2-b-ssm.png)](../media/lab-2-b-ssm.png#lightbox)

1. Set the **Region** slicer to **Select All**.

    When pinning visuals to a dashboard, they will use the current filter context. Once pinned, the filter context cannot be changed. For time-based filters, it’s a better idea to use a relative date slicer (or, Q&A using a relative time-based question).

1. To create a dashboard and pin a visual, hover the cursor over the **Sales and Profit Margin by Month** (column/line) visual.

1. At the top-right corner, select the pushpin.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the pushpin in the top right corner.](../media/lab-2-ssm.png)](../media/lab-2-ssm.png#lightbox)

1. In the **Pin to Dashboard** window, in the **Dashboard Name** box, enter **Sales Monitoring**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Pin to dashboard window.](../media/lab-2-a-ssm.png)](../media/lab-2-a-ssm.png#lightbox)

1. Select **Pin**.

1. Open the **Navigation** pane, and then open the **Sales Monitoring** dashboard.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Sales Monitoring dashboard in the Navigation pane.](../media/lab-3-a-ssm.png)](../media/lab-3-a-ssm.png#lightbox)

1. Notice that the dashboard has a single tile.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Sales, Profit Margin by month chart tile.](../media/lab-3-b-ssm.png)](../media/lab-3-b-ssm.png#lightbox)

1. To add a tile based on a question, at the top-left of the dashboard, select **Ask a Question About Your Data**.

    You can use the Q&A feature to ask a question, and Power BI will respond with a visual.

1. Select any one of the suggested questions beneath the Q&A box, in blue boxes.

1. Review the response.

1. Remove all text from the Q&A box.

1. In the Q&A box, enter the following: **Sales YTD**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Q & A box.](../media/lab-3-c-ssm.png)](../media/lab-3-c-ssm.png#lightbox)

1. Notice the response of **(Blank)**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Sales YTD showing the word Blank.](../media/lab-5-ss.png)](../media/lab-5-ss.png#lightbox)

    You may recall you added the **Sales YTD** measure in the **Create DAX calculations in Power BI Desktop, Part 2** lab. This measure is a Time Intelligence expression, so it requires a filter on the **Date** table to produce a result.

1. Extend the question with: **in year FY2020**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Q & A field with the text Sales Y T D in year FY2020.](../media/lab-6-ssm.png)](../media/lab-6-ssm.png#lightbox)

1. Notice the response is now **$33M**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Blank response replaced with $33M.](../media/lab-7-ss.png)](../media/lab-7-ss.png#lightbox)

1. To pin the response to the dashboard, at the top-right corner, click **Pin Visual**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Pin Visual option on the Pin to dashboard window.](../media/lab-8-ssm.png)](../media/lab-8-ssm.png#lightbox)

1. When prompted to pin the tile to the dashboard, select **Pin**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Pin to dashboard window with the Pin button highlighted.](../media/lab-9-ssm.png)](../media/lab-9-ssm.png#lightbox)

1. To return to the dashboard, at the top-left corner, select **Exit Q&A**.

1. To add the company logo, on the menu bar, click **Edit**, and then select **Add a tile**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Edit menu expanded with the Add a tile option highlighted.](../media/lab-4-a-ss.png)](../media/lab-4-a-ss.png#lightbox)

    Using this technique to add a dashboard tile lets you embellish your dashboard with media, including web content, images, richly-formatted text boxes, and video (using YouTube or Vimeo links).

1. In the Add a Tile pane (located at the right), select the Image tile.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Image tile in the Add a Tile pane.](../media/lab-4-b-ss.png)](../media/lab-4-b-ss.png#lightbox)

1. Select **Next**.

1. In the **Add Image Tile** pane, in the **URL** box, enter the complete URL found in the **D:\DA100\Resources\AdventureWorksLogo_DataURL.txt** file.

    > [!Note]
    > You can embed an image by using its URL, or you can use a data URL, which embeds content inline.

1. At the bottom of the pane, click **Apply**.

1. To resize the logo tile, drag the bottom-right corner, and resize the tile to become one unit wide, and two units high.

    Tile sizes are constrained into a rectangular shape. It's only possible to resize into multiples of the rectangular shape.

1. Organize the tiles so that the logo appears at the top-left, with the **Sales YTD** tile beneath it, and the **Sales, Profit Margin** tile at the right.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the two tiles on the Sales Monitoring dashboard.](../media/lab-4-ss.png)](../media/lab-4-ss.png#lightbox)

### Task 5: Edit tile details

In this task, you will edit the details of two tiles.

1. Hover the cursor over the **Sales YTD** tile, and then at the top-right of the tile, select the ellipsis, and then select **Edit Details**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the drop-down menu showing Edit details.](../media/lab-10-ssm.png)](../media/lab-10-ssm.png#lightbox)

1. In the **Tile Details** pane (located at the right), in the **Subtitle** box, enter **FY2020**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Tile details window with the Subtitle field highlighted and containing F Y 2020.](../media/lab-11-ssm.png)](../media/lab-11-ssm.png#lightbox)

1. At the bottom of the pane, select **Apply**.

1. Notice that the **Sales YTD** tile displays a subtitle.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of F Y 2020 text displayed as a subtitle under Sales Y T D on the tile.](../media/lab-12-ssm.png)](../media/lab-12-ssm.png#lightbox)

1. Edit the tile details for the **Sales, Profit Margin** tile.

1. In the **Tile Details** pane, in the **Functionality** section, check **Display Last Refresh Time**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Funtionality section with Display last refresh time checked.](../media/lab-13-ssm.png)](../media/lab-13-ssm.png#lightbox)

1. Select **Apply**.

1. Notice that the tile describes the last refresh time (which you did when refreshing the data model in Power BI Desktop).

    You'll simulate a data refresh later in the lab and see that the refresh time updates.

### Task 6: Configure an alert

In this task, you will configure a data alert.

Data alerts can only be configured on dashboard tiles, and specifically tiles that display a single numeric value.

1. Hover the cursor over the **Sales YTD** tile, select the ellipsis, and then select **Manage Alerts**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the ellipsis drop-down menu with Manage alerts highlighted.](../media/lab-14-ssm.png)](../media/lab-14-ssm.png#lightbox)

1. In the **Manage Alerts** pane (located at the right), select **Add Alert Rule**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Manage alerts pane with Add alert rule button.](../media/lab-15-ssm.png)](../media/lab-15-ssm.png#lightbox)

1. In the **Threshold** box, replace the value with **35000000** (35 million).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Threshold box with the Threshold field containing 35000000.](../media/lab-16-ssm.png)](../media/lab-16-ssm.png#lightbox)

    This configuration ensures you'll be notified whenever the tile updates to a value above 35 million.

1. At the bottom of the pane, select **Save and Close**.

You’ll refresh the dataset in the next exercise. Typically, this would be achieved by using scheduled refresh, in which case Power BI would use a gateway to connect to the SQL Server database. However, due to constraints in the classroom setup, there is no gateway. So, you’ll open Power BI Desktop, perform a manual data refresh, and then upload the file to your workspace.

## Exercise 2: Refresh the dataset

In this exercise, you'll first load sales order data for June 2020 into the **AdventureWorksDW2020** database. Then you'll open your Power BI Desktop file, perform a data refresh, and then upload the file to your workspace.

### Task 1: Update the lab database

In this task, you'll run a PowerShell script to update data in the **AdventureWorksDW2020** database.

1. In File Explorer, inside the **D:\DA100\Setup** folder, right-click the **UpdateDatabase-2-AddSales.ps1** file, and then select **Run with PowerShell**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Run with PowerShell option.](../media/lab-17-ssm.png)](../media/lab-17-ssm.png#lightbox)

1. If prompted to change the execution policy, press **A**.

1. When prompted to press any key to continue, press **Enter** again.

    The **AdventureWorksDW2020** database now includes sales orders for June 2020.

### Task 2: Refresh the Power BI Desktop file

In this task, you will open the Sales Analysis Power BI Desktop file, perform a data refresh, and then upload the file to your **Sales Analysis** workspace.

1. In Power BI Desktop file, in the **Fields** pane, right-click the **Sales** table, and then select **Refresh data**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the context menu with Refresh data highlighted.](../media/lab-18-a-ssm.png)](../media/lab-18-a-ssm.png#lightbox)

1. When the refresh completes, save the Power BI Desktop file.

1. To publish the file to your workspace, on the **Home** ribbon tab, from inside the **Share** group, click **Publish**.

1. When prompted to replace the dataset, select **Replace**.

    The dataset in the Power BI service now has June 2020 sales data.

1. Close Power BI Desktop.

## Exercise 3: Review the dashboard

In this exercise, you will review the dashboard to verify updated sales, and that the alert was triggered.

### Task 1: Review the dashboard

In this task, you will review the dashboard to verify updated sales, and that the alert was triggered.

1. In the Microsoft Edge browser window, in the Power BI service, review the **Sales Monitoring** dashboard.

1. In the **Sales, Profit Margin** tile, in the subtitle, verify that the data was refreshed **NOW**.

1. Verify also that there is now a column for **2020 Jun**.

    If you don’t see the June 2020 data, you might need to press F5 to reload the web browser.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Sales, Profit Margin tile.](../media/lab-18-ssm.png)](../media/lab-18-ssm.png#lightbox)

    The alert on the **Sales YTD** tile should have triggered also. After a short while, the alert should notify you that sales now exceeds the configured threshold value.

1. Notice that the **Sales YTD** tile has updated to **$37M**.

1. Verify that the **Sales YTD** tile displays an alert notification icon.

    If you don't see the notification, you might need to press **F5** to reload the browser. If you still don't see the notification, wait some minutes longer.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the notification icon on the Sales YTD tile.](../media/lab-19-ssm.png)](../media/lab-19-ssm.png#lightbox)

    Alert notifications appear on the dashboard tile, and can be delivered by email, and push notifications to mobile apps including the Apple Watch.

1. At the top-right corner of the web page, select the **Notifications** icon.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the notifications icon in the top-right corner.](../media/lab-19-a-ssm.png)](../media/lab-19-a-ssm.png#lightbox)

1. In the **All Notifications** pane, review the details of the alert notification.

1. To close the pane, select **Close**.

    > [!WARNING]
    > If you leave the lab open, it will time out after one to four hours. Your work in the *current* module's lab will be lost, but each lab after the first one includes a PBIX file with the work from all previous labs completed so that you don't need to start over.

[!INCLUDE [](../../../includes/power-bi-lab-end.md)]
