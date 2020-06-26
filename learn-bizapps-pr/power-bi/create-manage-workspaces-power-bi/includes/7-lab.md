In this lab, you will explore the three core methods for sharing Power BI content.

In this lab, you learn how to:

-   Map security principals to dataset roles

-   Share a dashboard

-   Publish an app

## Configure dataset security

In this exercise, you will assign your classroom partner's account to the **Salespeople** role of your dataset.

> [!NOTE]
> The following exercise will require you to login to Power BI service, you can use your existing account or create a trial account before starting this part of the lab.

### Configure dataset security

In this task, you will use an existing account in the **Salespeople** role of your dataset.

1.  In Edge, in the Power BI service, in the **Navigation** pane, hover the cursor over the **Sales Analysis** dataset, click the vertical ellipsis (...), and then select **Security**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-1-ssm.png)](../media/lab-1-ssm.png#lightbox)

1.  In the **Row-Level Security** page, at the left, notice that the **Salespeople** role is selected.

1.  In the **Members** box, commence typing the account name of your classroom partner---when it is listed, select it.

	Adding individual accounts is time consuming and requires a lot of maintenance. Consider that the Adventure Works company would likely have a security group that contains all salespeople accounts. This security group would be the only security principal mapped to the role.

1.  Click **Add**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-2-ssm.png)](../media/lab-2-ssm.png#lightbox)

1.  At the bottom of the page, click **Save**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-3-ssm.png)](../media/lab-3-ssm.png#lightbox)

The account of your classroom partner is now mapped to the **Salespeople** role. Recall that their account is for the salesperson Pamela Ansam-Wolfe, whose sales performance is measured by the sales of two sales territory regions: US Northwest and US Southwest.

## Share a dashboard

In this exercise, you will share your **Sales Monitoring** dashboard with your classroom partner (and they will share theirs with you).

### Share a dashboard

In this task, you will each share a dashboard, and then open the shared dashboard shared with you.

With your classroom partner, work through all task steps together, [on each of your computers]{.underline}.

1.  Open the **Sales Monitoring** dashboard.

1.  On the menu bar, click **Share**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-4-ssm.png)](../media/lab-4-ssm.png#lightbox)

1.  In the **Share Dashboard** pane (located at the right), in the **Grant Access To** box, commence typing the account name of your classroom partner---when it is listed, select it.

1.  Review the available options---but do not change them.

1. At the bottom of the pane, click **Share**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-5-ssm.png)](../media/lab-5-ssm.png#lightbox)

### Open the shared dashboard

In this task, you will each open the dashboard shared with you.

1. In the **Navigation** pane, click **Shared With Me**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-6-ssm.png)](../media/lab-6-ssm.png#lightbox)

1. Notice that the **Sales Monitoring** dashboard is listed.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-7-ss.png)](../media/lab-7-ss.png#lightbox)

1. To open the dashboard, click the **Sales Monitoring** dashboard.

1. Notice that the dashboard **Sales YTD** tile value is **$13M**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-8-ss.png)](../media/lab-8-ss.png#lightbox)

The **Sales YTD** tile displays a value for US Northwest and US Southwest regions only.

Sharing dashboards (and reports) is easily achieved and managed by the content owner. Power BI provides a read-only experience to recipients. If the owner enables re-sharing, recipients can share the content with others.

This approach should be reserved for ad hoc sharing requirements. If you need to share many Power BI items, then publishing an app is a better option. You'll publish your Sales Analysis workspace as an app in the next exercise.

## Publish an app

In this exercise, you will publish the contents of your **Sales Analysis** workspace, and then "get" the app published by your classroom partner.

### Publish an app

In this task, you will publish the contents of your **Sales Analysis** workspace, and then "get" the app published by your classroom partner.

1. In the **Navigation** pane, open your **Sales Analysis** workspace.

1. In the **Navigation** pane, click the name of the workspace.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-9-ssm.png)](../media/lab-9-ssm.png#lightbox)

1. At the top-right, click **Publish App**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-10-ssm.png)](../media/lab-10-ssm.png#lightbox)

1. Notice that the publish app process requires configuration in three tabs: **Setup**, **Navigation**, and **Permissions**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-11-ssm.png)](../media/lab-11-ssm.png#lightbox)

1. In the **Description** box, enter: **Sales analysis and exploration**

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-12-ssm.png)](../media/lab-12-ssm.png#lightbox)

1. For the **App Logo**, click **Upload**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-13-ssm.png)](../media/lab-13-ssm.png#lightbox)

1. In the **Open** window, navigate to the **D:\DA100\Lab12A\Assets\Icons** folder.

1. Select one of the JPG files, and then click **Open**.

1. For the **App Theme Color**, select any color.

1. Select the **Navigation** tab.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-14-ssm.png)](../media/lab-14-ssm.png#lightbox)

1. In the **Navigation** section, notice the workspace content that will be published.

It is possible to set the order of the workspace content, and also add sections and links. Sections are a single-level grouping of content (similar to a folder). Links are a link to any valid web page. You won't modify the navigation setup in this lab.

1. Select the **Permissions** tab.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-15-ssm.png)](../media/lab-15-ssm.png#lightbox)

1. In the **Specific Individuals or Groups** box, commence typing the account name of your classroom partner---when it is listed, select it.

The **Entire Organization** option may be disabled if the tenant admin has restricted it. In this case, the **Install this App Automatically** option will also be disabled. If enabled, the app could be pushed to all users. You will learn how to "get" the app in the next task.

1. At the bottom-right corner, click **Publish App**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-16-ssm.png)](../media/lab-16-ssm.png#lightbox)

1. When prompted to publish the app, click **Publish**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-17-ssm.png)](../media/lab-17-ssm.png#lightbox)

1. When notified that the app was successfully published, click **Close**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-18-ssm.png)](../media/lab-18-ssm.png#lightbox)

### Get the app

In this task, you will "get" the app, and explore the app contents.

1. In the **Navigation** pane, click **Apps**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-19-ssm.png)](../media/lab-19-ssm.png#lightbox)

1. In the middle of page, click **Get Apps**.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-20-ss.png)](../media/lab-20-ss.png#lightbox)

1. In the AppSource window, for the **Sales Analysis** app published by your classroom partner, click the **Get it Now** link.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-21-ssm.png)](../media/lab-21-ssm.png#lightbox)

1. When the app is added, to open the app, click the app tile.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-22-ss.png)](../media/lab-22-ss.png#lightbox)

1. When the app opens, review the navigation pane (located at the left).

1. Notice that the first item in the navigation pane has opened.

1. In the navigation pane, expand **Sales Report**, and then select the **Overview** page.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-23-ssm.png)](../media/lab-23-ssm.png#lightbox)

1. Notice that **Region** slicer only displays two regions---the regions assigned to Pamela Ansam-Wolfe.

	> [!div class="mx-imgBorder"]
	> [![alt text](../media/lab-24-ss.png)](../media/lab-24-ss.png#lightbox)

1. Select the **My Performance** page.

1. Notice that the page displays the sales and targets for Pamela Ansam-Wolfe.

1. Open the **Sales Exploration** report, and then interact with the visuals on each page.

