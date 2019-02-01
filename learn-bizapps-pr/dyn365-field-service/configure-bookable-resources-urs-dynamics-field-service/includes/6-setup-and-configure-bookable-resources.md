
Universal Resource Scheduling enables an organization to schedule anything that might be needed to better service their customers. This might include items like work orders in Dynamics 365 for Field Service.

The purpose of this hands-on-lab is to introduce you configuring Universal Resource Scheduling.

### Learning Objectives
At the end of these exercises, you will be able to accomplish the
following:

-   Enabled Mapping Functionality
-   Defined a Bookable Resource
-   Schedule Items using the schedule Board
-   Enable the Time Off Request Entity for Scheduling

Estimated time to complete this lab: 60 to 75 minutes

### Before we Begin

The Labs and exercises in this module work best when you have some sample data to work with. Depending on if the environment you are working with, you may want to install some sample data to assist with exercises. Dynamics 365 does provide the ability to add sample data as needed. If the environment you are working in does not have any sample data installed, follow the steps below to install the sample data into your environment.

> [!IMPORTANT]
> The demo data that we will be leveraging for this exercise, is a smaller set of data that will help to illustrate the configuration concepts available in the application. There is more complete demo data available that can be used for both Project Service automation and Field Service.

### Install the Field Service Demo Date—Detailed Steps

1. In Dynamics 365, select the down arrow next to **Dynamics 365**, and then select **Field Service**.
2. Using the site map, select the ellipsis (...), and select **Field Service Settings**.
3. Under *Schedule Settings*, select **Characteristics**.
4. Select **New**.
5. Enter *MCSE* in the **Name** field, select **Certification** in the **Certification** **Type** field, and then select **Save**.
6. Select **New**.
7. Type *MCSA* in the **Name** field, select **Certification** in the **Types** field, and then select **Save and Close**.

### Enable Bing Maps to use Resource Scheduling

To ensure that you are able to take full advantage of the full scheduling and mapping capabilities available with Universal Resource Scheduling, you need to ensure that it is configured to use a mapping provider. Bing Maps is the default map provider, but additional providers could be enabled. We will be using Bing Maps.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Universal Resource Scheduling**.
2.  Click the **Site Map** icon to expand the **Navigation**. From the menu that appears select **Administration**.
3.  Select **Scheduling Parameters**.
4.  Locate the **Connect to Maps** field and set it to **Yes**.

    ![Connect to Maps](../media/URS-Unit6-4.png)

5.  **Save and Close** the settings.

### Enable Bing Maps to use Resource Scheduling 

Before you can start scheduling items and assigning them to specific resources in your organization, you need to first create bookable resources in the application. A bookable resource could be an internal user, an external contact or account, or a piece of equipment. When you define a bookable resource, you can also provide details such as skills they have, where they start and end their day and so on.

In this first task we will be creating a bookable resource record for your user account.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Universal Resource Scheduling**.
2.  Click the **Site Map** Icon to expand the **Navigation**. From the menu that appears select **Resources**.
3.  Click **New** button to create a new **Bookable Resource**.
4.  Configure the Resource as follows:
    -   **Resource Type:** User
    -   **User:** Your User Record
    -   Leave the default value in the Time Zone Field.
5.  Select the Scheduling Tab, and configure as follows:
    -   **Organizational Unit:** Seattle
    -   **Start Location:** Organizational Unit Address
    -   **End Location:** Organizational Unit Address
6.  Select the Field Service tab, and configure as follows:
    -   **Hourly Rate:** 175
7.  **Save** the bookable resource record and leave it open.
8.  Locate the **Characteristics** sub-grid, click **Add New Bookable Resource Characteristic**
9.  Configure as follows:
    -   **Characteristic:** Building 12 Access
    -   **Rating Value**: Proficient
10. Additional characteristics could be added for the resource if they had multiple skills.
11. **Save and Close** the characteristic record.
12. **Save and Close** the bookable resource record**. **

### Create a new work order using and incident type

Out of the box, Dynamics 365 for Field Service has the work order entity enabled for use with the Resource Scheduling feature. In this task, we will be creating a new work order that we can schedule using the application.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Field Service**.
2.  Click the **Site Map** Icon to expand the **Navigation**. From the menu that appears select **work orders**.
3.  Click the **New** button.
4.  Configure the work order as follows:
    -   **Service Account:** Adventure Works (Sample)
    -   **Work Order Type:** Inspection
    -   **Taxable:** No
    -   **Primary Incident Type:** MRI Inspection

5.  Click the Settings tab, and Configure as follows:
    -   **Priority:** Moderate
    -   **Service Territory:** WA
    -   **Time from Promised:** Today @ 1:00 PM
    -   **Time to Promised:** Today @ 3:00 PM

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

### Working with the Map view

Another way that items can be scheduled is by using the map view on the Schedule Board. When you select the map view, resources will be color coded. Any unscheduled items, will appear on the map with a question
mark. You can schedule these items by dragging them to a specific resource that you want to assign it to.

As you start assigning items to resources, the item will change to the color of the resource selected. Additionally, the map will begin to plot a route for the resource based on the location of the work orders assigned to them.

Additional items like traffic and road maps can be overlaid on the map to assist in scheduling.

1.  On the Schedule Board, click the **Map View**.

2.  To see Traffic, click the **Show Traffic**.

3.  Locate an item on the map that is unscheduled. Drag the item to open time slot on Allison Dickson's schedule right before the work order you scheduled for her previously.

Several paragraphs -- or longer -- describing an overview of the lab including a description of the lab and why certain topics are covered. This is also called the 'LAB ABSTRACT' that will be used for hand-off to conferences as part of the content hand-off process 

### Customize the Booking Status entity

As mentioned at the beginning of the lab, Contoso Consulting want to ensure that when someone creates a time off request, that it will be displayed on the Schedule Board. Before we can start populating time off requests on the Schedule Board, we need to customize the Booking Status Entity. The Booking Status entity is used to communicate the status of the current booking such as traveling, in progress, on break, and so on. We need to add a field that flags a specific booking status as time off.

To accomplish this, we will be doing the following:

-   Adding a time off field to the Booking Status Entity.
-   Customizing the Booking Status form to include the time off field.
-   Creating a Booking Status view that only displays Booking Statuses that are flagged as time off.
-   Configuring the Booking Status Entity for editable grids to make flagging a status as time off easier.

### Add the Time Off field to the Booking Status entity

1.  In Dynamics 365 web interface, navigate to **Settings > Customizations > Customize the System**
2.  Expand the **Booking Status Entity**, select **Fields**, and click the **New** button to add a new field to the Booking Status Entity.
3.  Complete the new field as follows:
    -   **Display Name:** Time off Status
    -   **Data Type:** Two Options
4.  **Save** and **Close** the Time Off Status field.

### Create a Booking Status view that only shows Time Off statuses

1.  On the **Booking Status Entity**, select **Views**, and **Open the Active Booking Statuses** view.
2.  Click the **Save As** button, save the view as **Booking Status - Time Off,** and click **OK**.
3.  Click the **Edit Filter Criteria** button.
4.  In the edit filter criteria screen, elect the arrow on the **Status -Equals -- Active** filter, and choose **Delete**.
5.  Configure the New Filter as follows:
    -   **Time Off Status** -- **Equals** -- **Yes**
6.  Click **OK**.
7.  Click the **Add Columns** button and check the **Time Off Status** field.
8.  Click **OK**.
9.  Click the **Save and Close** button to save the **Booking Status -- Time Off** view.

### Add the Time Off field to the Booking Status form

1.  Under the **Booking Status** entity, click **Forms.**
2.  Open the **Information** form.
3.  Under **Field Explorer**, locate the **Time Off Status** field, and drag it under the **Description** field.
4.  **Save** and **Publish** the **Booking Status** form.

### Enable the Booking Status entity for editable grids

1.  Select the **Booking Status** entity, click the **Controls** tab.
2.  Click **Add Control**..., select the **Editable Grid** control, and click **Add**.
3.  Select both **Web** and **Tablet**. **Save** and **Publish** your customizations to the **Booking Status** entity.

### Customize the Time Off Request entity

The next thing that we need to do is customize the Time Off Request entity to allow us to associate specific Time Off Requests with booking statuses. For example, if you have a doctor appointment, you should be able to note that on the Time Off Request. This will also be used to determine how the Time Off Request will be displayed on the schedule board. We want to ensure that only Booking Statuses that are considered Time Off statuses are available to choose from.

To accomplish this, we will be doing the following:

-   Adding a lookup field to the Time Off Request Entity that links to the Booking Status Entity.
-   Customizing the Time Off Request Form to include the lookup field.
-   Configure the field on the form to only display Booking Statuses that are considered Time Off statuses.

### Add a Lookup field to the Time Off Request Entity that links to the Booking Status Entity

1.  In Dynamics 365 web interface, navigate to **Settings \> Customizations \> Customize the System**
2.  Expand the **Time Off Request**, select **Fields**, and click the **New** button to add a new field to the Time Off Request entity.
3.  Configure the field as follows:
    -   **Display Name:** Time off Type
    -   **Data Type:** *Lookup*
    -   **Target Record Type:** Booking Status
4.  Click the **Save and Close** button.

### Add the Time Off Type field to the Time Off Request form and filter to show only Time Off booking statuses

1.  Under the **Time Off Request** entity, select **Forms** and open the **Information** form.
2.  Under **Field Explorer**, drag the **Time off Type** field and place under the **Start Time** field.
3.  Select the **Time Off Type** field, click the **Change Properties** button.
4.  Under **Additional Properties** configure the following:
    -   **Default View:** Booking Statuses -- Time Off
    -   **View Selector:** Off
5.  Click **OK**
6.  **Save** and **Publish** the **Time Off Request** form.
7.  In the **Default Solution**, click the **Time Off Request** entity.
8.  In the **Entity Properties**, set the **Color** field to **\#FF5AFF**.
9.  **Save** and **Publish** the **Time Off Request** entity.

### Enable the Time Off Request entity

There are two main entities that are used for scheduling an item using URS. The Resource Requirement entity and the Bookable Resource Booking entity. The Resource Requirement entity is used to define what is needed to schedule an item. Typically, the Resource Requirement includes things like the start and end time, duration, skills required and so on. Once a resource that meets the requirements is found, a Bookable Resource Booking is created and displayed on the schedule board.

For a Time Off Request to appear on the schedule board, a Resource Requirement must first exist, and then a Bookable Resource Booking can be created. To achieve this, the Time Off Request entity needs a relationship with both the Resource Requirement and Bookable Resource Booking. This can be accomplished by enabling the Time Off Request entity for URS.

To accomplish this, we will be doing the following
-   Enabling the Time Off Request entity for URS.
-   Configuring mapping for the Time Off Request entity and the Resource Requirement and Bookable Resource Booking entities.

### Enable the Time Off Request for URS

1.  In **Dynamics 365**, click **Switch to Another App**.
2.  Select the **Universal Resource Scheduling** App.
3.  Click the **Site Map** Icon.
4.  Click **Administration**.
5.  Select the **Enable Resource Scheduling for Entities.**
6.  Configure as follows:
    -   **Add Entity:** Time Off Request
    -   **Booking Relationship:** Create New Relationship
    -   **Requirement Relationship:** Create New Relationship.

7.  Click **Publish Customizations**.

8.  Under Settings for the Time Off Request entity, configure as follows:
    -   **Default Booking Duration:** 1 Hour
    -   **Disable Requirement Auto Creation:** Yes

9.  Under Attribute Mapping, configure as follows:
    -   **From Date:** Start Time
    -   **To Date:** End Time
    -   **Duration:** Duration (Deprecated)

10. Close the **Time Off Request** window.

### Create a workflow

Now that the Time Off Request entity has been enabled for URS, we need to make sure that both the necessary Resource Requirement and Corresponding Bookable Resource Booking are automatically created so they can be populated on the schedule board. To accomplish this, we will be creating a workflow that will do the following:
-   Create a Resource Requirement record with the necessary data populated from the Time Off Request.
-   Create a Bookable Resource Booking associated with the Resource Requirement that is assigned to the Resource that submitted the Time Off Request.

1.  In the **Default Solution**, locate **Processes**, click the **New** button to add a new process.
2.  Configure the new process as follows:
    -   **Process Name:** *Schedule Time Off*
    -   **Category:** *Workflow*
    -   **Entity:** *Time Off Request*
3.  Click **OK**
4.  Under **Options for Automatic Processes**, set the **Scope** to **Organization**. Ensure that **Start when**  is set to **Record is Created**.
5.  In the **Workflow Designer** click the **Add Step** button, from the menu that appears, select **Create Record**.
6.  In the **Description** field, enter **Create a Resource Requirement for the Time Off Request**.
7.  Select **Resource Requirement** and click **Set Properties**.
8.  Configure the Resource Requirement as follows:
-   **Name:** {Name(Time Off Request)}
-   **From Date: {**Start Time(Time Off Request)}
-   **To Date:** {End Time(Time Off Request)}
-   **Duration:** {Duration(Time Off Request)}
-   **Status:** Active
-   **Time Off Request:** {Time Off Request(Time Off Request)}
-   **Allocation Method:** None
9.  Click **Save and Close**.
10. In the **Workflow Designer** click the **Add Step** button, from the menu that appears, select **Create Record**.
11. In the **Description** field, enter **Schedule the Time Off Request**.
12. Select **Bookable Resource Booking** and click **Set Properties**.
13. Configure the Bookable Resource Booking as follows:
-   **Name:** {Name(Time Off Request)}
-   **Start Time:** {Start Time(Time Off Request)}
-   **End Time:** {End Time(Time Off Request)}
-   **Duration:** {Duration(Time Off Request)}
-   **Resource:** {Resource(Time Off Request)}
-   **Booking Status:** {Time Off Type (Time Off Request)}
-   **Resource Requirement:** {Resource Requirement(Create(Resource Requirement))}
14. Click **Save and Close**.
15. **Save** and **Activate** the workflow.

### Add Time off booking statuses to Dynamics

Now that everything has been setup and configured in Dynamics 365, we will see how they all works together. We will add some Time Off statuses
to the application, and then use those statuses to create a Time Off Request that will be automatically added to the Schedule Board.

To accomplish this, we will be doing the following:
-   Adding three new Time Off Booking Statuses.
    -   Doctor appointment
    -   Vacation
    -   Seminar
-   Creating a Time Off Request record for vacation.
-   Viewing the Time Off Request on the Schedule Board.

1.  In **Dynamics 365**, **Switch to Another App**, select the **Universal Resource Scheduling** App.
2.  Click the **Site Map** Icon, under **Settings**, click **Booking Statuses**.
3.  Click the **New** button.
4.  Configure the Booking Status as follows:
    -   **Name:** Dr. Appointment
    -   **Time Off Status:** Yes
5.  Click **Save and Close**
6.  Click the **New** button, and configure the Booking Status as follows:
    -   **Name**: Vacation
    -   **Time Off Status:** Yes
7.  Click **Save and Close**
8.  Click the **New** button, and configure the Booking Status as follows:
    -   **Name:** Seminar
    -   **Time Off Status:** Yes
9.  Click **Save and Close**

### Create a Time Off Request

1.  In **Dynamics 365**, click **Switch to Another App,** select the **Field Service** App.
2.  Click the **Site Map** icon.
3.  From the menu that appears, under **Service Delivery**, select **Time Off Request**.
4.  Click the **New** Button.
5.  Configure the Time Off Request as follows:
   a.  **Resource:** *Your Resource Record*
   b.  **Start Time:**  *Tomorrow at 8:00 AM*
   c.  **End Time:** *Tomorrow at 5:00 PM*
   d.  **Time Off Type:** *Vacation*
6.  Click the **Save and Close** button.
7.  Click the **Site Map** Icon, under **work order & Scheduling**, click the **Schedule Board**.
8.  Scroll to tomorrow's date
9.  Notice the **Time Off Request** appears.
