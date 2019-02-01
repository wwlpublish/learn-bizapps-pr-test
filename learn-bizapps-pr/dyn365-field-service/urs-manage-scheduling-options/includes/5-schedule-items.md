Universal Resource Scheduling enables an organization to schedule anything that might be needed to better service their customers. This might include items like work orders in Dynamics 365 for Field Service. The purpose of this hands-on-lab is to introduce you to scheduling items using Universal Resource Scheduling.

### Learning Objectives

At the end of these exercises, you will be able to accomplish the following:

The Labs and exercises in this module work best when you have some
sample data to work with. Depending on the environment you are
working with, you may want to install some sample data to assist with
exercises. Dynamics 365 does provide the ability to add sample data as
needed. If the environment you are working in does not have any sample
data installed, follow the steps below to install the sample data into
your environment.

> [!IMPORTANT] 
> The demo data that we will be leveraging for this exercise, is a smaller set of data that will help to illustrate the configuration concepts available in the application. There is more complete demo data available that can be used for both Project Service automation and Field Service.

## Install the Field Service Demo Data -- Detailed Steps:

1.  Locate the **FS\_Demo\_Data.zip** file available in the class resources.
2.  Right click the **FS\_Demo\_Data.zip** file, and choose **Unblock**
    *(It may not be there and that is OK)*
3.  Right click the **FS\_Demo\_Data.zip** file, and select **Extract All**
4.  Click **Browse**, select a location for the extracted files, click **Extract**

![Browse Icon](../media/MSO-Unit5-1.png)

5.  Open the **FS\_PkgFolder** in the extracted FieldServiceDemo Data folder
6.  Right click the **DemoDataConfig.xml** file, and select **Edit**
7.  Edit the NewName value to a user in your Dynamics 365 Deployment (Example: the user that was created initially when you deployed your trial)

![Edit New Name](../media/MSO-Unit5-2.png)

8.  **Save and Close** the DemoDataConfig file.

> [!Important] 
> Before you continue make sure there is no sample data installed in your Dynamics 365 Org. Go to **Settings** \> **Data Management** and Select Demo Data. If it is installed Select Remove Sample Data before continuing.

9.  Right click the **PackageDeployer** application in the FieldServiceDemotData folder and select **Run as Administrator**
10. If necessary, click **Yes** on the User Access Control Message
11. On the Welcome Screen, click **Continue**
12. Select **Office 365** for the **Deployment Type**.
13. Set the Online Region to your Region, enter your username and password, and click **Login**

![PackageDeployer](../media/MSO-Unit5-3.png)

14. On the **Field Service Demo Data Setup Tool** screen, click **Next**
15. On the **Ready to Install** Screen, click **Next**
16. Once the Installer configuration is complete, click **Next**
17. Wait for the Installer to complete (May take up to 30 or 45 Minutes), click **Next**
18. Click **Finish** to complete the Field Service Sample Data installation.

### Enable Bing Maps to use with Resource Scheduling. 

To ensure that you are able to take full advantage of the full scheduling and mapping capabilities available with Universal Resource Scheduling, you need to ensure that it is configured to use a mapping provider. Bings Maps is the default map provider, but additional providers could be enabled. We will be using Bing Maps.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Universal Resource Scheduling**.
2.  Click the **Site Map** icon to expand the **Navigation**. From the menu that appears select **Administration**.
3.  Select **Scheduling Parameters**.
4.  Locate the **Connect to Maps** field and set it to **Yes**.

![Connect to Maps](../media/MSO-Unit5-4.png)

5.  **Save and Close** the settings.

### Create Bookable Resources 

Before you can start scheduling items and assigning them to specific resources in your organization, you need to first create bookable resources in the application. A bookable resource could be an internal user, an external contact or account, or a piece of equipment. When you define a bookable resource, you can also provide details such as skills they have, where they start and end their day and so on.

In this first task we will be creating a bookable resource record for your user account.

1.  In **Dynamics 365**, click the arrow next to the **Dynamics 365** text, and select **Universal Resource Scheduling**.
2.  Click the **Site Map** Icon to expand the **Navigation**. From the menu that appears select **Resources**.
3.  Click **New** button to create a new **Bookable Resource**.
4.  Configure the Resource as follows:
    -   **Resource Type:** User
    -   **User:** *Your* User Record
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
12. **Save and Close** the bookable resource record. 

### Create a new work order using an incident type

Out of the box, Dynamics 365 for Field Service has the work order entity
enabled for use with the Resource Scheduling feature. In this task, we
will be creating a new work order that we can schedule using the
application.

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

### Schedule the work order using the schedule board

Universal Resource Scheduling provides several items that can be used to assist in scheduling resources for specific items. The two primary components that are used are the Schedule Board and the Schedule Assistant. The Schedule Board provides the ability to manually schedule items, and the assistant offers suggestions on resources based on factors like location, skills, and availability. In this task we will examine how you can use the schedule board to schedule items and a high level.
1.  Click the **Site Map** icon to expand the **Navigation**. From the menu that appears select **Schedule Board**.
2.  The Schedule Board provides several options that can be used to schedule items, such as a filter, and a map view.
3.  Expand the **Booking Requirements** pane.
4.  Select **Unscheduled work orders**.
5.  Locate the **work order** for Adventure Works (Sample) that you created in a previous task. Drag it to Allison Dickson on the schedule board. Notice that it the text will appear red until you find a time that falls within the time window promised.
6.  Release the mouse button and the item will be placed on the schedule board.
7.  Locate and select the work order for **Fourth Coffee (Sample)** under **Unscheduled work orders.** Click **Find Availability**.
8.  Dynamics 365 will analyze the requirements needed for this item and will factor in other items such as any skills required, work order & resource locations, and resource availability to create a list of suggested resources that would be able to work on this item.
9.  As you hover over the available time block for **Van Amundson**, a **Book** icon will appear. Click the **Book** icon to schedule Van for this work order.
10. Click the **Exit Search** Icon to return to the Schedule Board.
11. Locate a resource that has an opening at 2:00 PM either today or tomorrow. Starting at 2:00 PM **click**, **hold**, and **drag** until you have selected from **2:00 PM** to **4:00 PM**.
12. In the lookup requirements, select an open requirement record. Click the **Add** button to schedule the item.

### Working with the Map View

Another way that items can be scheduled is by using the map view on the Schedule Board. When you select the map view, resources will be color coded. Any unscheduled items, will appear on the map with a question mark. You can schedule these items by dragging them to a specific resource that you want to assign it to.

As you start assigning items to resources, the item will change to the color of the resource selected. Additionally, the map will begin to plot a route for the resource based on the location of the work orders assigned to them.

Additional items like traffic and road maps can be overlaid on the map to assist in scheduling.

>[!IMPORTANT]
> If you do have very many unscheduled work orders, navigate to the Work Order Entity can create 5 or 6 additional work orders. Select any of the existing incident types to ensure that skills
are populated as needed. 

1.  On the Schedule Board, click the **Map View**.
2.  To zoom into a specific service center, click on the Organizational Unit icon you want and click the zoom in button until you can see resources, and requirements on the map.
3.  To see Traffic in the area, click the **Show Traffic**
4.  Locate an item on the map that is unscheduled. (It will appear with a Red Exclamation Point) Drag the item to open time slot on Allison Dickson's schedule right before the work order you scheduled for her previously. Notice that a booking is created, and the Requirement has been changed to Allison's pin color.

5.  Locate another unscheduled item on the map.
6.  Hover over the unscheduled item. On the Tooltip that appears click **Find Availability**.
7.  Dynamics 365 will analyze the requirements needed for this item and will factor in other items such as any skills required, work order & resource locations, and resource availability to create a list of suggested resources that would be able to work on this item.
8.  As you hover over the available time block for **Any resource with availability**, a **Book** icon will appear. Click the **Book** icon to schedule the resource for this work order.

### Rescheduling Items

Many times, something happens that requires an item to either be rebooked all together at a different day and time or have maybe it just
required that a different resource be substituted for the item.

1.  On the schedule board, click the **filter** tab on the **Filter and Map** View.
2.  In **Territories** filter control, select **WA**. Ensure all other filter criteria is left blank and click the **Search** button.
3.  Locate the Fan not working work order for Joseph Gonsalves.
4.  **Right-click** the work order and from the menu that appears,  select **Rebook**.
5.  The **Schedule Assistant** will open. You should be presented with between 4 and 7 resources who have availability.
6.  Click the availability block for Efrain Schreiner. In the **Create Resource Booking** screen accept the defaults and click **Rebook & Close**.
7.  Locate the hard disk boot failure work order for Joseph Gonsalves.
8.  **Right-Click** the work order and from the menu that appears, select **substitute resource**, **Find substitution**.
9.  The **Schedule Assistant** will open. You may only be presented with 1 or 2 resources.
10. Hover over the availability block that is presented for Simon Raley. Click **Substitute**.
11. The booking will be reassigned from Joseph to Simon.
