Patient Outreach is an extension of the [Dynamics 365 Marketing](https://docs.microsoft.com/learn/modules/dynamics-365-for-marketing/?azure-portal=true) app that has been extended and tailored to health care scenarios. The app allows healthcare organizations to communicate targeted medical and health-related information to specific patient communities. The app runs from a centralized Dataverse environment that is also accessed from other Microsoft Cloud for Healthcare apps.

The Patient Outreach app is broken down in the following key areas.

- Customers

- Marketing Execution

- Event Management

- Lead Management

The Patient Outreach app is a model-driven Power App. It can be configured, modified, or extended as required by a particular medical organization's requirements.

## Customers

The customer section groups together information about related medical organizations, patients, medical practitioners, and other stakeholders.

### Accounts

The Account table holds information about households, medical centers, insurance companies, and other related organizations or groups as they related to healthcare management. The accounts table is part of the [Common Data Model](https://docs.microsoft.com/common-data-model/?azure-portal=true) and is extended specifically for healthcare applications.

### Patients

The Patients table is actually the Common Data model contacts table that has been extended and tailored for the Microsoft Cloud for Healthcare applications. Key information stored about a patient can be the standard contact information but also links to specific treatments, the care teams, and medical information such as allergies, medications, conditions, and other key information. This information can be used to help you build specific segments for targeted communications.

> [!div class="mx-imgBorder"]
> [![Screenshot of Patient row in Patient Outreach app.](../media/4-1-patient.png)](../media/4-1-patient.png#lightbox)

### Segments

A segment extends the Dynamics 365 marketing segments to allow healthcare practitioners to build up lists of patients to target for specific healthcare-related communications. These are based on information such as pre-existing medical conditions or issues, or other information tracked for patients. A dynamic segment will automatically add or remove patients depending on the criteria specified when creating the segment.

The Patient Outreach app has prebuilt patient segments based on Healthcare Effectiveness Data and Information Set (HEDIS) industry standard.

### Subscription list

A subscription list allows patients to "subscribe" to specific information outreach or communications as they relate to receiving health care related information.

## Marketing execution

### Patient journeys

A patient journey is an outline or a communication plan to provide information to a group of patients that are grouped together in a segment. The patient journey can also begin some actions and follow-ups depending on the interaction of the patients with the communications (for example, clicking a link or opening an email).

> [!div class="mx-imgBorder"]
> [![Overview of a patient journey, the example of a Breast cancer screening journey is triggered when a patient is added to a segment.](../media/4-2-journey.png)](../media/4-2-journey.png#lightbox)

### Marketing emails

The marketing email section provides a "what you see is what you get" (WYSIWYG) email designer for users of the app to create healthcare-related communication email templates for use in customer journeys.

### Social activities

A healthcare organization may want to convey information to the public and patients via social activities. The social activities section provides a view of current social activities and sentiment.

## Event management

### Event

The event table tracks information about in-person and virtual events. In a healthcare scenario, this could mean events like information sessions, training, and gathering patients (for example, a flu-shot event).

> [!div class="mx-imgBorder"]
> [![Screenshot showing the event management form for the Patient Outreach app.](../media/4-3-event.png)](../media/4-3-event.png#lightbox)

### Event registrations

The event registrations track a contact's specific engagement to an event. The registration will provide information such as the registration ID, sessions of interest and other key information that will roll up to allow staff to better management events.

## Lead management

The lead management section is typically geared toward sales engagement scenarios but can be used in a healthcare scenario to recruit potential patients, volunteers, and public to engage with a healthcare organization's services and programs.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCyT7]
