Vaccination management is a model-driven app from Power Apps that is used by the healthcare administrator to set up and manage phases, vaccines, doses, and schedules. The healthcare administrator can also review who has registered and the vaccine inventory. Additionally, they can view basic reports on the daily schedule and activities and the outcomes of vaccinations.

In this exercise, you will be playing the role of a site/location manager and will learn how to complete the following tasks:

- Set up vaccine manufacturer details.

- Record the vaccine details along with its dosage, storage, and immunization education details.

- Set up provider details.

- Set up vaccination site details and then associate the vaccinators to a site.

- Create schedules and have slots created automatically.

- Record vaccination shipments.

## Task 1: Create manufacturer

In this task, you will create a vaccine manufacturer record. This record will enable you to introduce a new vaccine manufacturer into the system.

1.  In the left pane, select **Manufacturer** and then you can view the list of active manufacturers.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Manufacturer in the left pane.](../media/manufacturer.png)](../media/manufacturer.png#lightbox)

1.  On the **Manufacturer** form, select the **+ New** button.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the +New button to create a new manufacturer record.](../media/new-manufacturer.png)](../media/new-manufacturer.png#lightbox)

1.  On the new manufacturer form, enter the following values and then select the **Save** button.

	- **Account Name** - Provide the vaccine manufacturer's name (for example, **Contoso Pharmaceuticals**)
	
	- **Account Type** - Select the type as **Manufacturer**
	
	- **Manufacturer Code** - Provide the manufacturer's code (for example, **1001**)
	
	- **Phone** - 425-555-0100
	
	- **Fax** - 425-555-0100
	
	- **Website** - `https://www.contoso.com/`
	
	- **Ticker Symbol** - CONTOSO
	
	- **Address 1:Street 1** - 3422 DELASKO Lane
	
	- **Address 1:City** - Elko New Market
	
	- **Address 1:State/Province** - MN
	
	- **Address 1:ZIP/Postal Code** - 99887
	
	- **Address 1: Country/Region** - US

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a manufacturer record with details populated.](../media/account-information.png)](../media/account-information.png#lightbox)

## Task 2: Create a vaccine type

In this task, you will create a vaccine type, which will enable you to create new a vaccine record along with its dosage, storage, and education details.

1.  In the left pane, select **Vaccine type** and then you can view the list of active vaccines.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Vaccine type in the vaccine menu.](../media/vaccine-type.png)](../media/vaccine-type.png#lightbox)

1.  On the **Vaccine type** form, select the **+ New** button.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the +New button to create a new vaccine type record.](../media/new-vaccine-type.png)](../media/new-vaccine-type.png#lightbox)

1.  On the new vaccine form, enter the following values and then select the **Save** button.

	- **Name** - Contoso Covid Vaccine
	
	- **Manufacturer** - Contoso Pharmaceuticals
	
	- **Code(CVX)** - Choose the **210** record that you created in the previous exercise
	
	- **GTIN** - Provide the GTIN code of the vaccine (for example, **1234567890**)
	
	- **NDC Code** - The National Drug Code is the number that identifies a vaccine/drug (for example, **12345-678-09**)
	
	- **Standard Dose Range High** - Provide the higher standard dosage range (for example, **0.3**)
	
	- **Standard Does Range Low** - Provide the lower standard dosage range (for example, **0.3**)
	
	- **Standard Dose Range Unit** - Provide the unit of measure for the dose range value (for example, **mL**)
	
	- **Standard Dose Quantity** - Provide a value for the standard dosage quantity (for example, **1**)
	
	- **Period to Next Dose** - Provide a value for the wait time for the next dose (for example, **21**)
	
	- **Period to Next Dose (string)** - Enter the wait time for the next dose in words (for example, **Twenty-one days**)
	
	- **Storage Temperature** - Enter the temperature at which the vials need to be frozen (for example, **40**)
	
	- **Storage Temperature Unit** - Select the temperature unit (for example, **Fahrenheit**)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a vaccine type record with details populated.](../media/general-details.png)](../media/general-details.png#lightbox)

Congratulations, you have successfully created a new vaccine manufacturer in the **Vaccine Site Management** app.

## Task 3: Create a provider

In this task, you will create a provider record. A provider is an organization that manages a vaccination site. The provider record will enable you to introduce new providers into the system.

1.  In the left pane, select **Provider** and then you can view the list of active providers.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Provider under Program in the left pane.](../media/provider.png)](../media/provider.png#lightbox)

1.  On the **Provider** form, select the **+ New** button.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the +New button to create a new provider.](../media/new-provider.png)](../media/new-provider.png#lightbox)

1.  Set the **Account** form type to **Organization**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Account form set to the Organization type.](../media/organization.png)](../media/organization.png#lightbox)

1.  On the new provider form, make sure that the view is set as **Organization**, enter the following values, and then select the **Save** button.

	- **Account Name** - Lamna Healthcare Company
	
	- **Account Type** - Organization
	
	- **Account Number** - 1001
	
	- **Phone** - 425-555-0100
	
	- **Fax** - 425-555-0100
	
	- **Website** - `http://www.lamnahealthcarecompany.com/`
	
	- **Address 1:Street 1** - 3422 DELASKO Lane
	
	- **Address 1:City** - Elko New Market
	
	- **Address 1:State/Province** - MN
	
	- **Address 1:ZIP/Postal Code** - 99887
	
	- **Address 1: Country/Region** - US

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the new account record with details populated.](../media/new-account-details.png)](../media/new-account-details.png#lightbox)

Congratulations, you have successfully created a vaccination provider in the **Vaccination Site Management** app.

## Task 4: Create vaccination site details and associate vaccinators

In this task, you will create vaccination site details and associate vaccinators/frontline workers to a site so that these users can be selected on the canvas app for the respective site. This task will enable you to introduce new providers into the system.

1.  In the left pane, select **Vaccination Site** and then you can view the list of vaccination sites.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Vaccination Site under Program in the left pane.](../media/vaccination-site.png)](../media/vaccination-site.png#lightbox)

1.  On the new **Vaccination Site** form, enter the following values and then select the **Save** button.

	- **Name** - Provide a name for the site (for example, **Lamna - Redmond**)
	
	- **Provider** - Select a provider (for example, **Lamna Healthcare Company**)
	
	- **Location Number** - Provide a unique location number (for example, **1234**)
	
	- **Timezone** - Select a time zone and it will be used in the **Frontline worker** app, for example, **(GMT-08:00) Pacific Time (US & Canada)**
	
	- **Street 1** - 8582 PALMITER Court
	
	- **City** - Redmond
	
	- **Country/Region** - US
	
	- **State/Province** - WA
	
	- **ZIP/Postal Code** - 98052
	
	- **Latitude** - 47.6701
	
	- **Longitude** - 122.1182
	
	- **Timezone** - (GMT-8:00) Pacific Time (US & Canada)
	
	- **Timezone IANA** - America/Tijuana

	> [!div class="mx-imgBorder"]
	> [![Screenshot of vaccination site general details.](../media/site-details.png)](../media/site-details-large.png#lightbox)

1. After you have saved the record, the controls in the **Vaccinators** group will be visible. Select the **Add Existing Vaccination Performer** button to associate an existing user to a vaccination site.

	> [!div class="mx-imgBorder"]
	> [![Screensot of the Site Staff window with the Add Existing Vaccination Performer button.](../media/site-staff.png)](../media/site-staff.png#lightbox)

1. On the pop-up window, search for the name of any performer who has already been created. Select the performer name and then select the **Add** button.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the search menu for performers with the +New Vaccination Performer button.](../media/performer-search.png)](../media/performer-search.png#lightbox)

Congratulations, you have successfully created a vaccination site in the **Vaccination Site Management** app.

## Task 5: Create a schedule and slots

In this task, you will learn how to create new schedules and automatically create slots. After the slots have created, they will be displayed in the schedule record.

1.  On the left site map, select **Schedules** and then select **+ New**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Schedules under Program on the left pane.](../media/schedules.png)](../media/schedules.png#lightbox)

1. On the new schedule record, fill in the following information:

	- **Name** - Lamna Vaccine Event
	
	- **Location** - Contoso - Redmond
	
	- **Enable Schedule Builder Automation** - Yes
	
	- **Dose** - Dose 1
	
	- **Vaccine** - Contoso Covid Vaccine
	
	- **Start Date** - Yesterday
	
	- **End Date** - Tomorrow
	
	- **Start Time** - 08:00
	
	- **End Time** - 18:00
	
	- **Slot Interval** - 30 minutes
	
	- **Slots Per Interval** - 5
	
	- **Monday - Saturday** - Yes

	> [!IMPORTANT]
	> Be sure to check off at least one day prior to saving the record for the first time; otherwise no slots will be created.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of vaccine event record general details.](../media/event-record.png)](../media/event-record-large.png#lightbox)

1. Select **Save & Close**. The Schedule Builder will then process and create the slots for the schedule record.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Schedule Builder Status set to Processing.](../media/processing-status.png)](../media/processing-status.png#lightbox)

Congratulations, you have successfully created a slot schedule for a vaccination site in the **Vaccination Site Management** app.

## Task 6: Create a batch

In this task, you will create a batch of newly received vaccine doses to be made available to residents.

1.  On the left site map, go to **Batches** under the **Vaccine** section and then select **+ New**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Batches under Vaccine on the left pane.](../media/batches.png)](../media/batches.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the +New button.](../media/new-batches.png)](../media/new-batches.png#lightbox)

1.  Create a new Vaccine Batch record by entering in the following information:

    **Medication ID**: Contoso Covid Vaccine

    **Batch Expiration Date**: Two weeks from now, 8:00 PM

    **Batch Lot Number**: 85

    **Dose Quantity**: 10

    **Dose Quantity (string):** 10

    **Location**: Contoso - Redmond

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a batch record with the Save & Close button.](../media/batch-record.png)](../media/batch-record.png#lightbox)

Congratulations, you have successfully created a vaccine batch in the **Vaccination Site Management** app.

## Task 7: Open a vaccine phase for booking

To address the situation of when demand for appointments is greater than the availability of appointment slots, vaccination program administrators can set a phase to allow or not allow eligible residents to make an appointment.

-   If **Book During Registration** is set to **Yes**, when currently eligible residents are registering, they can continue and directly book a vaccination appointment.

-   If **Book During Registration** is set to **No**, currently eligible residents can't book an appointment when registering. Eligible residents are presented with a screen that informs them that they are eligible. If they provide their contact information, they will be notified in email about when and how to make an appointment.

To make access to vaccination appointments more equitable, a vaccination program administrator can specify that the selection of eligibility is random. This approach uses a lottery method to select which eligible residents are sent email invitations. The default selection method is first in, first out (FIFO).

In this task, you will open a vaccine phase for registration and booking.

1.  Select **Reference data** from the lower-left site map.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Reference data on the left site map.](../media/reference-data-selected.png)](../media/reference-data-selected.png#lightbox)

1.  On the left site map, select **Phases** and then open the **Phase 2** record.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Phases under Vaccine on the left pane.](../media/phases.png)](../media/phases.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of active vaccine phases.](../media/active-phases.png)](../media/active-phases.png#lightbox)

1.  Change the **Booking open** field from No to **Yes**. This action will lock the field after it's been changed so that it can't be changed back. All future vaccine eligibility records will now be tracked against this phase. Select **Save & Close** to close the record.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a phase 2 record with the Booking Open field set to Yes.](../media/booking-open.png)](../media/booking-open-large.png#lightbox)

Congratulations, you have opened a vaccine phase for registration and booking in the **Vaccination Site Management** app.

