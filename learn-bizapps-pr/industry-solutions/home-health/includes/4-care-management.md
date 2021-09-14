In this exercise, you will learn about the Field Service Mobile app and how to use care management components from the perspective of a nurse or a physical therapist who is out in the field working with a patient. This exercise goes through the installation process, shows how to set up Home Health users and security profiles, and demonstrates how to use the app to complete work orders.

[The Dynamics 365 Field Service Mobile app](/dynamics365/field-service/mobile-power-app-overview/?azure-portal=true) is designed and optimized for mobile health workers to view Dynamics 365 Home Health work orders and patient information. This mobile app is built on Microsoft Power Platform and is customizable to your business needs with the same admin console as all Dynamics 365 business apps.

Field Service Mobile app is available natively for Apple iOS and Google Android phones and tablets, and it offers technicians many capabilities that they need to perform on-site customer service, such as:

-   A calendar view of assigned jobs

-   Support for picture, video, and asset barcode scanning

-   Customer signature capture

-   Offline capabilities so that mobile health workers can continue viewing and recording work in areas without internet

The following screenshot shows a calendar view of scheduled work orders.

> [!div class="mx-imgBorder"]
> [![Screenshot of a calendar view of the scheduled work orders.](../media/calendar.png)](../media/calendar.png#lightbox)

## Task 1: Assign security roles to Field Service mobile users

In this task, you will assign the **Field Service - Resource** role to Home Health workers.

1.  Go to [https://make.powerapps.com](https://make.powerapps.com/?azure-portal=true).

1.  Go to **Apps** to select the **Field Service Mobile** app*, select the **gear icon** in the upper-right corner, and then go to **Advanced settings**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Field Service Mobile app.](../media/field-service-mobile.png)](../media/field-service-mobile.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Advanced settings.](../media/advanced-settings.png)](../media/advanced-settings.png#lightbox)

1.  Select **Settings** and then select **Security**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Security option under system settings.](../media/system-security.png)](../media/system-security.png#lightbox)

1.  Select **Users**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Users feature.](../media/users-feature.png)](../media/users-feature.png#lightbox)

1.  Change the view to show **Enabled Users**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Enabled Users view.](../media/enabled-users.png)](../media/enabled-users.png#lightbox)

1.  Find and select the user to whom you want to assign the **Field Service Mobile - Resource** role and then select **Manage Roles**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Manage Roles feature.](../media/manage-roles.png)](../media/manage-roles.png#lightbox)

1.  Scroll down to select the **Field Service - Resource** security role and then select **OK**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Field Service - Resource security role.](../media/manage-user-roles.png)](../media/manage-user-roles.png#lightbox)

Congratulations, you have assigned the Field Service - Resource role to a Field Service Mobile Home Health user in Microsoft Cloud for Healthcare.

## Task 2: Download the Field Service Mobile app and sign in

In this task, you will download the Field Service Mobile app to an iOS or Android device and then sign in.

1.  Go to the app store on your iOS or Android device and search for **Dynamics 365 Field Service**.

1.  Download the **Field Service (Dynamics 365)** app, as shown in the following screenshot. It's the mobile app that is built on Microsoft Power Platform.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Dynamics 365 Field Service app download.](../media/field-service-app.png)](../media/field-service-app.png#lightbox)

1.  Launch the app and then **sign in** with the Microsoft Cloud for Healthcare username and password for the user whom you assigned the **Field Service - Resource** security role to in the previous task.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Field Service Mobile app sign-in screen.](../media/sign-in.png)](../media/sign-in.png#lightbox)

Congratulations, you have downloaded and signed in to the Field Service Mobile app as a Home Health user in Microsoft Cloud for Healthcare.

## Task 3: Use the Field Service Mobile app to manage Home Health work orders

In this task, you will assign a Home Health work order to your Home Health bookable resource. Next, you will view and update the work order in the Field Service Mobile app and then view those changes in the Microsoft Cloud for Healthcare Home Health app.

1.  Go to [https://make.powerapps.com](https://make.powerapps.com/?azure-portal=true).

1.  Open the **Home Health** app.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Home Health app.](../media/home-health-app-selected.png)](../media/home-health-app-selected.png#lightbox)

1.  Go to **Home Care** and open the unscheduled **Home Care Work Order 00020** for the Contoso, Ltd. household (opening any unscheduled Home Care work order is acceptable).

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Home Care option in the Home Health screen.](../media/home-care-work-order.png)](../media/home-care-work-order.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Active Home Cares screen.](../media/active-home-cares.png)](../media/active-home-cares.png#lightbox)

1.  Scroll down to the **Primary Incident** section and set the **Primary Incident Estimated Duration** option to **1 hour** (this setting will ensure that the work order appropriates time on the resource's calendar after it's been scheduled).

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Primary Incident Estimated Duration menu.](../media/duration.png)](../media/duration.png#lightbox)

1.  Select **Save & Close**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Save & Close button.](../media/save-close-button.png)](../media/save-close-button.png#lightbox)

1.  Go to the **Schedule Board** and select **Unscheduled Work Orders**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Unscheduled Work Orders option in the schedule board.](../media/unscheduled.png)](../media/unscheduled.png#lightbox)

1.  Drag the Home Health work order onto the schedule board to assign it to your bookable resource.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Home Health work order moved onto the schedule board.](../media/drag-drop.png)](../media/drag-drop.png#lightbox)

1.  On your mobile device, sign in to the Field Service Mobile app as your bookable resource user. If you encounter a message that states, "Contact your administrator for access to your organization's mobile apps," select the menu icon in the upper left and set the **Show non-production apps** toggle to **Yes** (because the list shows production apps by default).

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Show non-production apps setting.](../media/non-production-apps.png)](../media/non-production-apps.png#lightbox)

1.  In the list of environments, find the Microsoft Cloud for Healthcare environment that you have been working in. From that environment, you will find the Home Health work order in the calendar view, shown in an **In Progress** state.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the state set as In Progress.](../media/in-progress.png)](../media/in-progress.png#lightbox)

1. Select to open the work order. Notice that the **Booking Status** shows as **In Progress**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Booking Status shown as In Progress.](../media/booking-status.png)](../media/booking-status.png#lightbox)

1. Update the **Booking Status** from **In Progress** to "**Completed** to close the work order and then select **Save**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Booking Status set as Completed.](../media/completed.png)](../media/completed.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Saving message.](../media/saving.png)](../media/saving.png#lightbox)

1. Return to the **Home Health** app, select **Home Care** on the site map, and then find your work order. Notice that the **System Status** has been updated to **Open - Completed**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Home Care on the site map.](../media/home-care-work-order.png)](../media/home-care-work-order.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the System Status displayed as Open - Completed.](../media/open-completed.png)](../media/open-completed.png#lightbox)

Congratulations, you have assigned a Home Health work order to a Home Health bookable resource, updated the work order in the Field Service Mobile app, and then viewed those changes in the Home Health app in Microsoft Cloud for Healthcare.

