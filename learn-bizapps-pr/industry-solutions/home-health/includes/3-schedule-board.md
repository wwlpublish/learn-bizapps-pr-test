In this exercise, you will configure the schedule board for the **Bookable Resource** that you created in the previous task. The schedule board provides an overview of resource availability and bookings you can make. Before you use the schedule board, it is important to set up the views and filters to your preference. To use the schedule board booking functionality, geocoding, and location services, you need to turn on maps.

Here is an example of a configured **Schedule Board**:

> [!div class="mx-imgBorder"]
> [![Screenshot of a schedule board example.](../media/schedule-board.png)](../media/schedule-board.png#lightbox)

1.  Navigate to [https://make.powerapps.com](https://make.powerapps.com/).

1.  Open the **Resource Scheduling** app.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Resource Scheduling app.](../media/resource-scheduling.png)](../media/resource-scheduling.png#lightbox)

1.  Change the area in the bottom-left navigation drop-down from Resource Scheduling to **Settings.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of settings changed in the navigation.](../media/settings.png)](../media/settings.png#lightbox)

1.  Click **Administration.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the administration button.](../media/administration.png)](../media/administration.png#lightbox)

1.  Click **Scheduling Parameters.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the scheduling parameters button.](../media/scheduling-parameters.png)](../media/scheduling-parameters.png#lightbox)

1.  Change "**Connect to Maps**" to **Yes**. Then click **OK** to accept the terms.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of connect to maps marked as yes.](../media/connect-maps.png)](../media/connect-maps.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the terms of use ok button.](../media/terms.png)](../media/terms.png#lightbox)

1.  Click **Save & Close.**

1.  Open the **Home Health** app.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the home health app in the app list.](../media/home-health-app.png)](../media/home-health-app.png#lightbox)

1.  Click **Home Care** and open any **Home Care Work Order.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the active home care work orders.](../media/home-care.png)](../media/home-care.png#lightbox)

1. Click **Related** and then click **Characteristics.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of characteristics in the related menu.](../media/characteristics.png)](../media/characteristics.png#lightbox)

1. Click **+ New Requirement Characteristic.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new requirement characteristic button.](../media/new-requirement-characteristic-button.png)](../media/new-requirement-characteristic-button.png#lightbox)

12. Choose "**Spanish fluency**" for the **Characteristic** and a desired Work Order for the **Resource Requirement**. Click **Save & Close.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the characteristic set as spanish fluency.](../media/spanish-fluency-characteristic.png)](../media/spanish-fluency-characteristic.png#lightbox)

	> [!IMPORTANT]
	> Make sure the **Work Order** number populated in the **Resource Requirement** field matches the Work Order number on the **Field Service** tab.

1. Click **Schedule Board.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of schedule board in the menu.](../media/schedule-board-menu.png)](../media/schedule-board-menu.png#lightbox)

1. Click the **+** button in the upper right corner to create a new **Schedule Board tab.**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the plus button to create a new schedule board tab.](../media/plus-button.png)](../media/plus-button.png#lightbox)

1. Name the new Schedule Board tab "**My Schedule Board Tab**". Leave all defaults and click **Add**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot my schedule board tab.](../media/my-schedule-board-tab.png)](../media/my-schedule-board-tab.png#lightbox)

1. Click on the Scheduler Settings **gear**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the gear for scheduler settings.](../media/gear.png)](../media/gear.png#lightbox)

1. Change the Hours view to be closer to typical working hours, such as 6am to 6pm.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the time zone menu.](../media/time-zone.png)](../media/time-zone.png#lightbox)

1. Find the work order that you added the **Spanish fluency** characteristic to and click on the grid to highlight it. Click **Find Availability** to open the Schedule Assistant filter.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the find availability button.](../media/find-availability.png)](../media/find-availability.png#lightbox)

1. Notice that the other two Bookable Resources that you created that do NOT have the "Spanish fluency" characteristic are dropped from the search. Click the **Book** button on the Bookable Resource's schedule to schedule the work order.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the book button.](../media/book.png)](../media/book.png#lightbox)

1. The work order is now scheduled and has disappeared from the bottom grid. Click **Exit Search** to close the pane.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the exit search button.](../media/exit-search.png)](../media/exit-search.png#lightbox)

**Congratulations**! You gave configured a Schedule Board tab and scheduled a Home Health visit using the bookable resource that you created in the previous task in this exercise.

