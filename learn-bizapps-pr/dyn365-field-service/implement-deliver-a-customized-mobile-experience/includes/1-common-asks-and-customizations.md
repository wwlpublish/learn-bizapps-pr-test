There are many advantages that Microsoft Dynamics for Field Service Mobile provides to technicians who are using it in the field. These advantages can range from items as simple as just being able to work with a scheduled booking and work order on the same screen, to more advanced items like being able to leverage virtual or augmented reality. Obviously virtual and
augmented reality are standard out of the box features, but with some configuration and customizations, they can be accomplished with the mobile application.

When the application is first deployed using the Field Service mobile project template, it will contain a basic user interface that is a great starting point for organizations as they are first deploying and getting started with it. However, most organizations, will have specific needs based on what their technicians are need and are doing in the field.
When an organization is first starting to deploy the mobile application. It is important they gather information from their technicians and identify what they need and will be doing with the application.

### Discovery questions
Every organization will be different, but some simple discovery questions such as the ones noted below can greatly assist in determining what an organization might need from the mobile application.

-   Does a technician need to accept a work order?

-   What information should the technician have when they are on site?

    -   What information do they need to capture from the customer?

    -   What actions are they performing on site?

-   Should technicians in the field be able to create their own work orders?

    -   Should they be able to self-schedule those items, or should that be handled by a dispatcher?
	    -   How does a technician cancel a job and how is it rescheduled?

There are countless other questions that could help to identify the needs of technicians. By understanding this data, we can more effectively tailor the mobile application to fit their needs. For example, by default to complete a service task associated with a work order, a technician must open each task and update the percentage of the task manually. Some work orders may have 10, 15, or more tasks on them. Something as simple as adding a check box to the task list that allows
technicians to simply mark a task as completed could save technicians hours of time over the course of a year.

When looking at the technician experience consider items such as:

-   How will technician be receiving and viewing their work order agendas?

-   How will they be Interacting with work order related data like tasks, products, services, notes, camera, etc.?

-   What data or user input will be needed for reporting both real time and retrospective reporting purposes?

-   How will technicians be utilizing customer and/or equipment history?

-   What data is needed for collaboration in the field?

-   Are there any mixed or augmented reality needs today or possibly in the future?

Below is a list of common configuration and customization changes that are often requested by customers using the mobile application.

-   Make field technicians accept work orders

-   Hide fields based on conditions

-   Make fields mandatory

-   Add yes/no completed toggle to Work Order service tasks

-   Add barcode scanning for field input and view lookup

-   Edit time slot on mobile schedule board

-   Custom commands

-   Replicate warnings and validation on desktop

    -   Ex: validating inventory before adding Work Order product

-   Time entry

-   Replace Work Order service task views and forms with HTML page

### Syncing data

One of the first things that should be addressed, is determine what data is available to which technicians when they are in the field. Sync filters are used to define the data will remain in the Field Service mobile application after synchronization.

There are two types of synchronization: initial (full) sync, and
incremental sync.

-   **FULL SYNC:** Performed when the app is used for the first time after install or when it does not have any data in offline local database.

    -   The app will download data from the server depending on the sync filter, so the sync filter is used to define what data is being downloaded to the Mobile app's local database.

-   **INCREMENTAL SYNC**: Field Service Mobile app downloads all records (that the user has permission for) that were created or updated since the last synchronization. Then the sync filters are used to only keep the records that follow the sync filters in the local database.

For more on sync filters, see [Setting up a Sync Filter](https://www.resco.net/woodford-user-guide/#__RefHeading__5817_1627906509).

The intent of this module is to help identify the different scenarios and tools that are available to assist in deploying the field service mobile application. Since the Field Service Mobile application is based on the Resco Woodford Mobile CRM solution and they have a complete set of training material available, we will refer to the tools and training available
through Resco for detailed instructions.
