The Home Health app is an extension of the [Dynamics 365 Field Service](https://docs.microsoft.com/learn/modules/dynamics-365-for-field-service/?azure-portal=true) app. This app allows healthcare professionals to schedule healthcare resources for home visits with patients. Administrators can also follow up with patients for appointment reminders and surveys and track medical cases.

The Home Health app is a model-driven Power App that can be configured, modified, or extended as required by a particular medical organization's requirements.

## Home Health

### People

The people table is an extension of the Contact table from the Common Data Model. In the Home Health app, the people table contains core contact information and health and medical information about patients. The people table also can contain information about medical practitioners operating from the medical organization.

The information is stored in Dataverse and is accessible to other Microsoft Cloud of Healthcare apps. It can also be integrated to other Electronic Medical Record systems using the FHIR Sync Agent.

> [!div class="mx-imgBorder"]
> [![Screenshot of the People form showing Patient information.](../media/3-1-people.png)](../media/3-1-people.png#lightbox)

### Cases

The cases table is an extension of the Dynamics 365 Customer Service app's case management feature that has been configured for medical and healthcare-related cases. Along with capturing the main details about the case, it can be linked to the Care Team, Care Plan, and other data tracking aspects from other Microsoft Cloud for Healthcare apps such as Care Management app. At home appointments can be scheduled or "booked" to a case, using the Dynamics 365 Field Service capabilities.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the Home Health case form tracking a medical condition.](../media/3-2-case.png)](../media/3-2-case.png#lightbox)

### Home Care

The Home Care table is an extension of the Dynamics 365 Field Service Work Order feature that is tailored to capture the details and requirements of home care visits. The Home Care form surfaces medical information about the patient, preferred times and visits, the Care Team, and Care Plan information that is managed from the Microsoft Cloud for Healthcare Care Management app.

### Schedule board

The Home Health app uses the Universal Resource Scheduling board and further extends the key Microsoft Dynamics 365 Field Service features such as viewing the team's schedule and bookings and managing and allocating resources to Home Care work orders.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Home Health Schedule board showing a series of bookings allocated to healthcare resources.](../media/3-3-schedule.png)](../media/3-3-schedule.png#lightbox)

The healthcare practitioners that are to be scheduled for home-based visits are tracked as Bookable Resources in the Home Health app. Information such as working hours, locations, characteristics, and categories can be tracked against the bookable resource to allow scheduling.

Healthcare practitioners can access their schedule using the mobile app and can also update the status of the visit and other patient information.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/]
