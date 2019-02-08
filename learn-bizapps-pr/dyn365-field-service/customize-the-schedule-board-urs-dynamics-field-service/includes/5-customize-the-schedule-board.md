Universal Resource Scheduling enables an organization to schedule anything that might be needed to better service their customers. This might include items like work orders in Microsoft Dynamics 365 for Field Service.

The purpose of this hands-on-lab is to introduce you configuring Universal Resource Scheduling.

### Learning Objectives

At the end of these exercises, you will be able to accomplish the
following:

-   Enabled Mapping Functionality
-   Defined a Bookable Resource
-   Schedule Items using the schedule Board
-   Enable the Time Off Request Entity for Scheduling

Estimated time to complete this lab: *60 to 75* minutes

### Before you begin

The Labs and exercises in this module work best when you have some sample data to work with. Depending on if the environment you are working with, you may want to install some sample data to assist with exercises. Dynamics 365 does provide the ability to add sample data as needed. If the environment you are working in does not have any sample data installed, follow the steps below to install the sample data into your environment.

> [!IMPORTANT]
> The demo data that we will be leveraging for this exercise, is a smaller set of data that will help to illustrate the configuration concepts available in the application. There is more complete demo data available that can be used for both Project Service automation and Field Service.

### Install the Field Service Demo Data—Detailed Steps

1. In Dynamics 365, select the down arrow next to **Dynamics 365**, and then select **Field Service**.
2. Using the site map, select the ellipsis (...), and select **Field Service Settings**.
3. Under *Schedule Settings*, select **Characteristics**.
4. Select **New**.
5. Enter *MCSE* in the **Name** field, select **Certification** in the **Certification** **Type** field, and then select **Save**.
6. Select **New**.
7. Type *MCSA* in the **Name** field, select **Certification** in the **Types** field, and then select **Save and Close**.

### Enable Bing Maps to use Resource Scheduling

To ensure that you are able to take full advantage of the full scheduling and mapping capabilities available with Universal Resource Scheduling, you need to ensure that it is configured to use a mapping provider. Bings Maps is the default map provider, but additional providers could be enabled. We will be using Bing Maps.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Universal Resource Scheduling**.
2.  Click the **Site Map** icon to expand the **Navigation**. From the menu that appears select **Administration**.
3.  Select **Scheduling Parameters**.
4.  Locate the **Connect to Maps** field and set it to **Yes**.

![Connect to Maps](../media/csb-unit5-4.png)

5.  **Save and Close** the settings.

### Create bookable resources

Before you can start scheduling items and assigning them to specific resources in your organization, you need to first create bookable resources in the application. A bookable resource could be an internal
user, an external contact or account, or a piece of equipment. When you define a bookable resource, you can also provide details such as skills they have, where they start and end their day and so on.

In this first task we will be creating a bookable resource record for your user account.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Universal Resource Scheduling**.
2.  Click the **Site Map** Icon to expand the **Navigation**. From the menu that appears select **Resources**.
3.  Click **New** button to create a new **Bookable Resource**.
4.  Configure the Resource as follows:
    -   **Resource Type**: User
    -   **User**: *Your* User Record
    -   Leave the default value in the Time Zone Field.
5.  Select the Scheduling Tab, and configure as follows:
    -   **Organizational Unit**: Seattle
    -   **Start Location**: Organizational Unit Address
    -   **End Location**: Organizational Unit Address
6.  Select the Field Service tab, and configure as follows:
    -   **Hourly Rate**: 175
7.  **Save** the bookable resource record and leave it open.
8.  Locate the **Characteristics** sub-grid, click **Add New Bookable Resource Characteristic**
9.  Configure as follows:
    -   **Characteristic**: Building 12 Access
    -   **Rating Value**: Proficient

10. Additional characteristics could be added for the resource if they had multiple skills.
11. **Save and Close** the characteristic record.
12. **Save and Close** the bookable resource record. 

### Create a new work order using an incident type

Out of the box, Dynamics 365 for Field Service has the work order entity enabled for use with the Resource Scheduling feature. In this task, we will be creating a new work order that we can schedule using the application.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Field Service**.
2.  Click the **Site Map** Icon to expand the **Navigation**. From the menu that appears select **work orders**.
3.  Click the **New** button.
4.  Configure the work order as follows:
    -   **Service Account**: Adventure Works (Sample)
    -   **Work Order Type**: Inspection
    -   **Taxable**: No
    -   **Primary Incident Type**: MRI Inspection
5.  Click the Settings tab, and Configure as follows:
    -   **Priority**: Moderate
    -   **Service Territory**: WA
    -   **Time from Promised**: Today @ 1:00 PM
    -   **Time to Promised**: Today @ 3:00 PM
6.  **Save and Close** the work order

### Schedule the work order using the Schedule Board

Universal Resource Scheduling provides several items that can be used to assist in scheduling resources for specific items. The two primary components that are used are the Schedule Board and the Schedule Assistant. The Schedule Board provides the ability to manually schedule items, and the assistant offers suggestions on resources based on factors like location, skills, and availability. In this task we will examine how you can use the schedule board to schedule items and a high level.

1.  Click the **Site Map** icon to expand the **Navigation**. From the menu that appears select **Schedule Board**.
2.  The Schedule Board provides several options that can be used to schedule items, such as a filter, and a map view.
3.  Expand the **Booking Requirements** pane.
4.  Select **Unscheduled work orders**.
5.  Locate the **work order** for Adventure Works (Sample) that you created in a previous task. Drag it to Allison Dickson on the schedule board. Notice that it the text will appear red until you find a time that falls within the time window promised.
6.  Release the mouse button and the item will be placed on the schedule board.
7.  Locate and select the work order for **Fourth Coffee (Sample)** under **Unscheduled work orders.**  Click **Find Availability**.
8.  Dynamics 365 will analyze the requirements needed for this item and will factor in other items such as any skills required, work order & resource locations, and resource availability to create a list of suggested resources that would be able to work on this item.
9.  As you hover over the available time block for **Van Amundson**, a **Book** icon will appear. Click the **Book** icon to schedule Van for this work order.
10. Click the **Exit Search** Icon to return to the Schedule Board.

### Create a Schedule Board tab that shows resources by territory

As a dispatcher, you spend a lot of time scheduling for the multiple territories that your organizations support. One scenario that comes up often, is the need to schedule for Washington Customer. Since the board will be focused on Washington customers, you would like to ensure the following:
-   Only open requirements in the Washington Territory are displayed in the Requirements panel.
-   Only open requirements in the Washington Territory are shown on the Map View.
-   The view is only showing Washington Resources.
-   When a resource is selected, the details view includes the territory.

### Customize the Resource Requirement views

1.  In Dynamics 365, select Dynamics 365-Custom. Navigate to **Settings** \> **Customizations** \> **Customize the System**.
2.  Expand **Entities**, expand the **Resource Requirement** entity, and select **views**.
3.  Locate and open the **Unscheduled Work Order Requirements** view.
4.  Click **Save As** and save the view as **Unscheduled WA Work Order Requirements**.
5.  Select the **Edit Filter Criteria** button.
6.  Locate and click in the **Select** field below the System Status -- Equals -- Open Unscheduled.
7.  Configure the items as follows:
    -   **Field**: Service Territory
    -   **Operator**: Equals
    -   **Value**: WA
8.  After you have defined the criteria, click **OK**.
9.  **Save and Close** the Unscheduled WA Work Order Requirements View.
10. Locate and open the **Active Resource Requirements** view
11. Click **Save As** to save the view as **Active Resource Requirements (with Territory)**
12. Click the **Add Columns** button.
13. From the list, select the **Territory** field, and click **OK**.
14. Ensure the Territory field has a green boarder around it, and using the arrows position the Territory field in between the Duration and Priority fields.
15. **Save and Close** the **Active Resource Requirements (With Territory view)**
16. Click **Publish All Customizations**

### Create and configure the WA Resources Schedule Board tab

1.  Select the down arrow next to the **Dynamics 365** text in the upper left corner.
2.  From the menu that appears, select **Field Service.**
3.  In the sitemap, navigate to **Schedule Board** under the **Work Order & Schedules** heading.
4.  Click the **Add Tab** button in the upper right corner of the screen nest to initial public view.
5.  In the **Name** field, enter **WA Resources**. Ensure that the **Shared with** field is set to **Just Me.**
6.  Under **Map Settings**, set the **Requirement Map Filter View** to **Unscheduled WA Work Order Requirements.**
7.  Click the **Schedule Types** tab.
8.  Click to select the **Work Order** entity. In the **Requirement Details View** field, select **Active Resource Requirements (With Territory)**
9.  Click to select the **Requirement Panels** tab.
10. Configure the new Requirement panel view as follows:
    -   **View Type**: Requirement Views
    -   **Title**: Unscheduled WA Work Orders
    -   **View**: Unscheduled WA Work Order requirements
11. Click the **Add new panel** button to add the Unscheduled WA Work Order Requirements.
12. Check the **Hide default requirement panels**.
13. Click the **Add** button to add the new Schedule Board tab.
14. After the WA Resources tab loads, locate the **Filter** tab on the Filter and Map View.
15. In the **Territories** filter control, select WA
16. Ensure all other filter criteria is empty can click **Search**.
17. Locate the **Options** button on the **Filter** tab. Click the options button and choose **Save current filters as default**.
18. Switch to the **Initial Public View** tab.
19. Switch back to the **WA Resources** tab.
20. The Requirements panel should only show the **Unscheduled WA Work Orders** tab.
21. Select a requirement from the Unscheduled WA Work Orders tab. Notice that it displays the Territory in the details section.

