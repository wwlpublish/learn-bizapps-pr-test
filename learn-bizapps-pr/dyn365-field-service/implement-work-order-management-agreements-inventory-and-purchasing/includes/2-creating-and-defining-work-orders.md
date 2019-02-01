There are multiple ways to create work orders in Microsoft Dynamics 365 Field Service. This flexibility accomodates the various needs of organizations.

Work orders can be created:

- As part of a defined service selling process.
- As an escalation for a case that could not be resolved remotely.
- By a customer manually requesting or scheduling service from a portal.
- Automatically, based on a service agreement or schedule.

### Manual work order creation

In many instances, work orders are created manually by dispatchers who receive the work order request from customers. A dispatcher can enter relevant information such as customer name, location of service, service preferences, etc.

When manually creating a work order, you'll need to enter information on several tabs. These include:

- **Summary:** Contains general overview information about the work order such as the status, customer, type of work order, and pricing information
- **Settings:** Includes detailed information that determines how the item is scheduled such as the priority, territory, and service preferences 
- **Products:**  Lists all products that are included in the work order
- **Services:** Defines the services included on the work order
- **Service Tasks:** Defines any tasks that a technician will perform as part of work order
- **Address:** Displays the physical address for the service account specified on the work order
- **Location:** Latitude and longitude information

![Work Order Window](../media/WO-Unit1-2.png)

### Converting from an opportunity

Many organizations sell service-based items. For example, a store that sells appliances or furniture often has installation services associated with them. Your organization can use the sales capabilities of Dynamics 365 to manage these sales opportunities, especially for longer-running scenarios. To convert an opportunity to a work order, on the opportunity record, select **Convert to Work Order**. To make sure an opportunity can be converted, you'll first need to define the following.

- **A work order type**: On the **Field Service** tab of the opportunity, for **Work order type**, enter a type.
- **A sales tax code**: On the account record of the opportunity, enter a default sales tax code. If the account is tax exempt, note that on the account record as well.

### Converting from a case

There will be times when call centers or the help desk are unable to solve cases remotely. In these instances, it might be necessary to dispatch a technician to solve the problem. For example, a customer might have an Internet of Things (IoT)-enabled temperature sensor in a server room. When the temperature sensor triggers an alert, a case is created
in Dynamics 365. If the agent working on that case cannot resolve it, a technician might be dispatched to run additional testing on the sensor.

Like opportunities, cases can be converted to work orders. To ensure a case can be converted you'll first need to define the following:

- **An incident type**: On the **Field Service** tab of the case, define the incident type. This will ensure that necessary products, services, and tasks, are populated to the work order. 
- **A sales tax code**: On the account record of the opportunity, enter a default sales tax code. If the account is tax exempt, note that on the account record as well.

### Other considerations for creating work orders

There are additional ways to create work orders. You might consider:

- **Agreements**: Agreements provide the ability to autogenerate work orders on a defined schedule. They are commonly used when organizations have maintenance agreements for specific pieces of equipment. For example, every three months a work order is created to have a technician come out and inspect an MRI machine.
    - When looking to generate work orders from agreements, consider things such as:
    - What types of agreements will you need?
    - How often should work orders be generated?
    - Should they be scheduled as well?
    - What information is needed?
        - Products, services, tasks, skills, etc.

- **A portal**: A customer might want to request service or schedule work orders from a portal. Before allowing work order creation from a portal you should consider the following:
  - Who will be creating the work orders?
      - Is the customer simply placing a request and the actual scheduling will be done internally?
      - Is the customer actually scheduling the work order?
  - What information is required to allow this?

- **Connected Field Service (CFS)/Internet of things (IoT)**: Because more IoT-enabled devices are in use, organization are using them to change their service models. Before allowing the creation of work orders from IoT-enabled devices, consider:
  - What type of devices will be used?
      - How will those devices be registered?
      - What information will be needed from the devices?
  - What types of exceptions will generate alerts?
      - What types of alerts will be used to generate work orders?
      - How will those be captured?

For more about creating and defining work orders, refer to this video:
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2KjKo]