## Introduction

The Care Management app allows healthcare professionals to manage information and events as it pertains to patient healthcare in a central location.

Information that appears in the app can be integrated with EMR (electronic medical record) systems to allow a full and complete view of patient information.

The Care Management app is broken down in the following key areas.

- Administration

- Care Management

- Clinical Data

The Care Management app is a model-driven Power App that can be configured, modified, or extended as required by a particular medical organization's requirements. The core Care Management app functionality uses tables from the [medical records Common Data Model](https://microsoft.github.io/CDM/SchemaViz.html?initialManifest=manifests/electronicMedicalRecordsAccelerator.manifest.cdm.json&simpleChrome=true&azure-portal=true).

## Administration area

A practitioner would use the administration area to add and update key information into the Care Management app such as People, Organizations, and Locations.

### Health analytics

Users of the app can get a high-level view of the care plan details and upcoming appointments and tasks by viewing the Care Coordinator dashboard. Other dashboards can be configured to combine different assets from the app to allow easy and fast access to critical decision-making information.

### People

The people table is an extension of the Common Data Model Contact table.

People rows represent patients and medical practitioners.

As patients, the people table can contain basic contact information and key medical details such as age and gender. The people row is critical to viewing and editing related details such as medical conditions, care team, care plans, and other medical information. The timeline control allows for fast viewing of conditions, medication, appointments, procedures, allergies, claims, and coverages.

> [!div class="mx-imgBorder"]
> [![Screenshot of a contact record of a patient.](../media/1-1-contact-record.png)](../media/1-1-contact-record.png#lightbox)

As medical practitioners, the people table can provide information qualifications and show links to related patients, upcoming appointments, and interactions.

> [!div class="mx-imgBorder"]
> [![Screenshot of grid view of available patient contact records.](../media/1-2-active-patients.png)](../media/1-2-active-patients.png#lightbox)

### Organizations

The organizations table is an extension of the Common Data Model Account table.

In the Care Management app, Organization rows represent households, medical organizations, insurance companies, and other organizations related to care management.

Care Management users can view location information and related practitioners and contact persons. More related information such as assets, locations, and other medically related data can be accessed from the organization rows.

### Locations

Organizations may have one or more locations that have unique addresses where specific medical practitioners can be associated.

## Care management area

The care management area provides a place to track the progress of care management strategies as it relates to specific patients.

### Care plans

A care plan is a plan determined by a medical professional or team of professionals as to a strategy and guide to treating a specific patient or patient condition.

The Care Plan table lets you document the specific care plan for a patient with timelines and relationship to goals, activities, care team, and links to relevant medical information.

### Care plan activities

A care plan activity is a specific action related to following a care plan. For example, prescribing a specific medication to treat a condition defined in the care plan. In the Care Management app, the care plan activities can be created and tracked against specific care plan rows and goals. Users of the Care Management app can view a series of activities in one specific location.

### Care plan goals

A care plan goal is a specific targeted outcome of following a care plan. The Care Management app provides the ability for medical practitioners to define care goals and link them to a specific care plan row related to a patient. Care plan activities can be linked to goals to measure the progression and results towards achieving the wanted outcomes of the care plan goals.

> [!div class="mx-imgBorder"]
> [![Screenshot of care plan record on the Plan details tab.](../media/1-3-care-plan.png)](../media/1-3-care-plan.png#lightbox)

## Clinical data area

The clinical data area allows medical practitioners to record various interactions and events as they relate to treating and caring for patients.

### Observations

An observation row allows a medical practitioner to record details about an assessment of a patient's condition or to log specific data points resulting from a medical test.

### Encounters

An encounter row can be added for each interaction between a patient and a healthcare practitioner to record dates and times of the interaction. The encounter can be linked to other information that is tracked in the Customer Care app such as observations and procedures.

### Procedures

A procedure row will allow a medical practitioner to record specific action while delivering a healthcare action. The procedure row can track the time, date, actions, and location of the procedure.

> [!div class="mx-imgBorder"]
> [![Screenshot of a procedure record.](../media/1-4-procedure.png)](../media/1-4-procedure.png#lightbox)

### Appointments

An appointment row specifies a meeting between a patient and a medical practitioner for a specific diagnosis or treatment. The appointment could be in-person or virtual over Microsoft Teams. Appointment management ensures that the practitioner has an appropriate to manage their patient caseloads.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/]
