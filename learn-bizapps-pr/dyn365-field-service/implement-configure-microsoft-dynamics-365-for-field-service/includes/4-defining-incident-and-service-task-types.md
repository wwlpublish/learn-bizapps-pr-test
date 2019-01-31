Many organizations have a set of standard ticket types for services they perform. Often, these standard tickets contain products, procedures, and services that do not vary much.

For example, let's say that a company services magnetic resonance imaging (MRI) equipment, and technicians are regularly dispatched to conduct MRI inspections. A standard MRI inspection might contain the following:

- **Products**
  - 1 Lithium battery
  - 2 Gradient coils

- **Services**
  - MRI sanitation

- **Tasks**
  - Measure energy usage: 30 minutes
  - Replace battery: 15 minutes
  - Replace gradient coils: 30 minutes
  - Collect customer signature: 15 minutes

To simplify the creation of a work order, standard products, services, and tasks of an MRI inspection can be quickly added to a work order by using incidents. Incidents are templates used to populate work orders.

### Defining Incident Types

To define the incident types you'll need, in Microsoft Dynamics 365 for Field Service select the ellipsis (...), select **Field Service Settings**, and then select **Incident Types**.

Define the following info:

- **Default work order type:** The type of work order to be executed (Inspection, break fix, preventative maintenance, etc.)
- **Skill / Characteristics:** The skills or certifications that a resource must have to work on this type of item
- **Tasks to be performed:** A to-do list that specifies each task to be performed and its duration (The total time for all tasks is rolled up to the work order and will populate the estimated duration field on the work order.)
- **Required products:** Each product and its quantity that will be needed to work on the ticket (Only products with a Field Service type of *Inventory* or *Non-inventory* can be added as products.)
- **Required services:** Each service that will be conducted as part of the ticket (Only items with a Field Service type of *Service* can be added as services.)

For more info about incident types, refer to this video:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2Kmlw]

### Creating Service Tasks

A service task is a task that needs to be completed on a work order. Service tasks can be added manually to a work order, or they can be automatically populated by attaching them to an incident type. When an incident type containing the service task is added to a work order, the service task will be added too. 

To create a service task, in Field Service settings, under **Work Order**, select **Service Task**. 

When a service task is created it will include the following:

- **Name:** Specifies the name of the task
- **Estimated Duration:** Defines the estimated amount of time the task generally takes (rolls up to populate the total estimated duration of the work order)
- **Description:** Provides additional details about the task

As service tasks are created, they can be referenced across multiple incidents or work orders. For example, if every work order a technician does ends with them collecting a customer signature, you can
define the *Collect customer signature* service task once, and simply add it where needed.

### Working with Multiple Incidents

A single work order can contain multiple incidents, and each populates the work order with products, services, and tasks. If any automatically populated items are unnecessary to a work order, they can be manually removed.