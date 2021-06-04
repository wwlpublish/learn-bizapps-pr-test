Microsoft Vaccination Management uses several capabilities of the Microsoft Power Platform including Power Apps (model-driven apps and canvas apps), Portals, Power BI, and Power Automate.

## Capabilities

Microsoft Vaccination Management has the following capabilities:

- Vaccination Management App

  - The Vaccination Management App is a model-driven Power App that is used by vaccination program administrators to set up and manage eligibility phases, vaccines, doses, and schedules. Vaccination program administrators can also see who has registered, review vaccine inventory, view basic reports on appointments, and see the outcomes of vaccinations.

  - It is composed of three main areas:

    - Reference Data

      - Vaccination program administrator creates and populates data that includes information about vaccines, locations of vaccination sites, and demographics data about registered residents.

    - Management

      - Vaccination program administrator creates and populates data that includes information about vaccines and their manufacturer, vaccination providers and their schedules, and vaccination sites and event codes.

    - Registration

      - Data for Eligibility, Resident, and Appointment is entered by residents in the Registration and appointment scheduling portal.

      - -Data for Vaccination is entered by vaccination frontline volunteers and nurses in the Frontline worker app.

- Registration and appointment scheduling portal

  - Microsoft Vaccination Management provides residents with an online portal where they can register to check if they're eligible for the COVID-19 vaccination. Depending on the outcome, residents can do one of the following steps:

    - If eligible, depending on configuration, the resident can be notified to make an appointment or proceed to schedule an appointment for getting the vaccination.

    - If not yet eligible, the resident can preregister to be notified through email when they become eligible for the vaccination.

- Frontline Worker App

  - The Frontline worker app is a Power Apps Canvas App used by workers at vaccination sites to distribute and administer vaccinations safely and effectively. With the Frontline worker app, these critical workers have the information they need to check in patients who have registered and booked an appointment, with the option to use touch-free QR code scanning. The app lets the vaccinator manage the details of the vaccine, including the dose number and vaccine batch, and lets the vaccinator note post-vaccine reactions.

- Vaccination Management Dashboard

  - The Vaccination management dashboard enables healthcare program leaders to gain insights and establish situational awareness about their vaccination program. You can track cumulative and daily vaccinations, view registrations, check on appointments, and monitor KPIs at the site level.

## Architecture

The following entity relationship diagram illustrates the tables and their relationships in Microsoft Vaccination Management. System-generated tables, relationships and columns, such as Created By and Modified By, aren't displayed in the diagram.

> [!note]
> This diagram represents MVM 1.1 architecture and not the architecture for the latest MVM 1.2 release. This diagram will be updated again when MVM 1.3 is released.

> [!div class="mx-imgBorder"]
> [![Entity relationship diagram that illustrates the tables and their relationships in Microsoft Vaccination Management.](../media/entity-relationship-diagram.png)](../media/entity-relationship-diagram.png#lightbox)

For more information, see [Microsoft Vaccination Management Foundation tables](/dynamics365/industry/vaccination-management/extend/?azure-portal=true#microsoft-vaccination-management-foundation-tables) on docs.microsoft.com.

## Solution layering

Let's understand how each capability is layered and packaged as a solution.

Each of the MVM capabilities follows the same structure and layering. The base is the Vaccination Management Package, which has a set of solutions and configuration data. On top of that layer rests the Vaccination Management Integration Package, which includes the MVM data model. Finally, the Vaccination Management Dashboard and sample data packages rest on top of the other layers.

Each layer shown here spits out some components of the Healthcare CDM and the MVM Data model on the target tenant.

> [!div class="mx-imgBorder"]
> [![Diagram of solution layering used in M V M.](../media/solution-layering.png)](../media/solution-layering.png#lightbox)

## Personas

The following security roles included in Microsoft Vaccination Management are set up for test and demo purposes. They must be reviewed and understood thoroughly before moving to a production environment or when importing sensitive data.

- Vaccination Call Center Agent

  - For users in your contact center who will be accessing the Vaccination call center app to help residents check their eligibility and make and manage their appointments.

- Vaccination Frontline Nurse

  - For users who will be using the Frontline worker app to administer and record the vaccination of residents.

- Vaccination Frontline Volunteer

  - For users who will be using the Frontline worker app to check in residents at the location or clinic. These users can't use the vaccination section of the app to record administration of vaccination to a resident.

- Vaccination Program Administrator

  - For users who will be configuring the Vaccination management app and will have access to all of the app's capabilities.

- Vaccination Provider Administrator

  - For users who are responsible for the provider scenarios, including managing locations, schedules, and vaccine batches in the Vaccination management app. These users can't delete or edit certain areas of the application, such as eligibility phases.
