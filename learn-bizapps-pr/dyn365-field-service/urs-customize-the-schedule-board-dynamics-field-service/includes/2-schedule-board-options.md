Each schedule board tab that is added has options that can be modified for it. Schedule board options can be modified by either double clicking on the schedule board tab you want to modify the settings for, or by clicking on the tab settings button. When you click on the tab settings button it will display the schedule board settings for the schedule board that is currently selected.

![Settings Icon](../media/csb-unit2-1.png)

Each schedule board tab has three areas that can be used to assist in the configuration of that specific board. These areas provide options from placement of objects to views that are used to render data on the
board. Those areas are:

-   **General Settings:** Defines items such as views used for board elements, placement of items on the board, and colors.
-   **Schedule Types:** Defines the views are used to display and filter items, such as bookings and requirements for each entity that is enabled for Universal Resource Scheduling.
-   **Requirements Panel:** Allows an organization to add additional requirement tabs to the requirements panel at the bottom of the schedule board.
    -   For example, you may create a panel tab that only shows unscheduled work orders where the work orders have a system sub-status of parts arrived.

While each schedule board tab is configured independently, there are default settings that can be defined. These settings are used for every schedule board tab unless otherwise specified. The default settings can
be accessed by clicking on the Open Default Settings button.

![General Settings](../media/csb-unit2-2.png)

### General settings

The general settings section contains five sections available that are used for board configuration.

Those sections are:

-   **Map Settings**: Defines settings related to the Map View placement and data available to assist in scheduling items.
-   **Custom Web Resource**: Defines a custom tab that can be linked to a web resource that can provide additional schedule board capabilities.
-   **Schedule Board Colors**: Defines the colors that are used to indicate how booked resources appear on the board.
-   **Schedule Assistant**: Defines settings that are used when the schedule assistant is used from the schedule board tab. These settings include:
    -   **Search For**: Defines the resources that will be searched based on the criteria provided. You can search only currently visible resources or all resources.
    -   **Unavailable Resources**: Defines if unavailable resources will be displayed in the search results.
    -   **Book Based On**: Defines how a resource should be booked for an item. You can choose to book based on estimated arrival or start of travel.
    -   **Availability Colors**: Defines the colors used to represent available, unavailable, and partially available resources.
    -   **Availability Icons**: Defines the icons used to represent available, unavailable, and partially available resources. (The Icons must be uploaded to Dynamics 365 as a web resource first)
-   **Other Settings**: Defines other settings that relate to the specific schedule board. These settings include:
    -   **Requirement Page Count**: Defines the number of requirement records that are returned per page.
    -   **Booking Alerts View**: Defines the Dynamics 365 view that will populate booking alerts displayed on the board.
    -   **Non-Working Hours Colors**: Defines the background color used on the board to represent hours a resource is not working.
    -   **Current Timeline Color**: Defines the color of the line that is used to indicate the current time on the schedule board.
    -   **Booking Alerts Template**: Defines the template used for  booking alerts.
    -   **Filter Layout Query**: Defines the types of controls available to use as filters on the board.
    -   **Retrieve Resource Query**: Controls the results that are returned when the search button is clicked.  
    -   **Resource Cell Template**: Controls what is displayed in the resource cell that is displayed on the schedule board.

    ![Map Settings](../media/csb-unit2-3.png)

### Schedule types

The schedule type section provides the ability to define which views will be used to populate various components on the schedule board, such as record details when a record is created. Each entity that is enabled for Universal Resource Scheduling has its own individual settings that can be modified.

The schedule type settings that can be defined include:

-   **Booking Tooltips View**: Defines the view that will be used to populate the contents of the tooltip that is displayed when a booking is hovered over on the schedule board.
-   **Booking Details View**: Defines the view that will be used display the record details in the details pane when a booking is selected.
-   **Schedule Assistant Requirement View**: Defines the view that will be used to populate requirements on the schedule assistant.
-   **Requirement Details View**: Defines the view that will be used display the record details in the details pane when a resource requirement is selected.
-   **Requirement Map Pin Tooltips View**: Defines the view that will be used to populate the contents of the tooltip that is displayed when a requirement is hovered over on the map view.
-   **Default Availability View**: Defines the view that is used to display resource availability. This can be set to either Grid or Board.
-   **Booking Template**: Defines the template that is used to display a booking on the schedule board.

    ![Schedule Types](../media/csb-unit2-4.png)

When you open the default settings, additional schedule type settings related to the schedule assistant are displayed. Like other items in the schedule type settings, these can be configured per entity that is enabled for the schedule board. The additional settings include:

-   Schedule Assistant Filter Layout: Controls only the types of controls that are available to use as filters on the board. The filter screen will change based on the items included in the Fetch XML query.
-   Schedule Assistant Resource Cell Template: *Used to control what is displayed in the resource cell that is displayed on the schedule board.
-   Schedule Assistant Retrieve Resource Query: This controls the results that are returned when the search button is clicked in the application.
-   *Schedule Assistant Retrieve Constraints Query: This retrieves any constraints from the resource requirement record and populates them to corresponding filter controls.

### Requirements panel

The requirements panel lets an organization add additional requirement tabs to the Requirements panel at the bottom of the schedule board.

![Requirements Panel](../media/csb-unit2-5.png)

> [!Note]
>  Modifying the views that are used in the schedule type settings and requirement panel tab involve making customizations to Dynamics 365 entity views. How to modify as well as which entities are used for schedule types and the requirements panel are covered in Using views with the Schedule Board.
