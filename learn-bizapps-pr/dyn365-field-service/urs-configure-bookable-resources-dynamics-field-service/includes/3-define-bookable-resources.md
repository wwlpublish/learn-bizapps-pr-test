Not all organizations use the same dispatching models when they schedule resources to conduct work. For example, a professional services company that specializes in break fix scenarios may primarily schedule internal people to conduct service work. Whereas a big box retailer may only use independent contractors to do things like install carpet, kitchen
cabinets, or appliances. You may also have companies that schedule consults with customers. In those scenarios, they may need to not only schedule someone, but also a room, and/or a machine to assist in the consult.

When creating resources in URS you can define a resource as any of the following:

-   **Generic**: Generally used as a place holder to define a type of resource that is needed until a specific named  resource can be used in its place.
-   **Contact**: Defines that resource is associated with a Dynamics 365 contact record.
-   **User**: Specifies the resource as an internal user mapped to a Dynamics 365 user record.
-   **Equipment**: Defines the resources as a specific piece of equipment.
-   **Account**: Defines that resource is associated with a Dynamics 365 account record.
-   **Crew**: Represents multiple resources that can be scheduled together for a specific item
-   **Facility**: Represents a facility that can be scheduled such as a building or room
-   **Pool**: Represents a pool of resources.

Depending on the type of resource you choose, different fields will appear in the resource record to all you to associate the resource with records like an account, user, or contact record. Each resource you define will have two tabs that can be used for configuration. *Those tabs are:* general & scheduling

After you save the resource for the first time, additional items will be available that you can associate the resource with such as characteristics (skills) and categories (roles). Additional tabs may be present for organizations that are using field service or project service automation.

### Scheduling tab

The scheduling tab defines the necessary items that define how resources are presented in the schedule board and what scheduling options are available.

One of the most important items that needs to be defined is the location information that will be used by the schedule board for the resource. The items that need to be defined are:

-   **Start location**: Defines where the resource begins there day. This is used to assist in route mapping for the resource.
-   **End location**: Defines where the resource begins there day. This is used to assist in route mapping for the resource.
-   **Organizational unit**: Defines the specific organization unit that the resource belongs to and will be schedule out off.

When you define a starting and ending location, you have three options that you can define:

-   **Organization unit address**: Uses the latitude and longitude associated with the Organizational Units that the resource belongs to.
-   **Resource Address**: Uses the latitude and longitude associated with the corresponding record based on the resource type:
    -   **Resource type - user**: Uses the latitude and longitude associated with the address defined on their Office 365 user record.
    -   **Resource type - contact**: Uses the latitude and longitude associated with the address defined on their Dynamics 365 contact record.
    -   **Resource type = account**: Uses the latitude and longitude associated with the address defined on their Dynamics 365 account record.

-   **Location Agnostic**: Does not have a specific location defined. Can be useful when resources don't have a clearly defined starting and ending location.

    ![Scheduling Tab Window](../media/URS-Unit3-1.png)

Additionally, you can specify if the resource is shown on the schedule board, or if they are available to be searched as a resource.

### Field Service tab

If your organization is using Dynamics 365 for Field Service, additional options will be available to define on the Field Service tab. These options include the resources hourly rate, and the warehouse associated with the resource. You might specify a warehouse for a resource when they have a specific truck that they drive each day. When a warehouse is
selected, we can ensure that inventory levels on the truck are sufficient for the products that will be used on work orders.

### Additional items to consider

When resources are being scheduled to work on items, there are often times additional considerations that need to be taken into account to find the best resource. This can include items such as what skills or certifications are required, or what territory is the item being scheduled in. Dynamics 365 provides additional items that can be defined
on the resource to make it easier to identify the ideal resource for a job.

-   **Characteristics:** Characteristics are another way of saying resource skills. You can define resource skills on the characteristic sub-grid on the resource record. When you add a new characteristic for a resource you need to define the following:
    -   **Characteristic**: Defines the skill or certification that a resource possesses.
        -   The characteristics available is based on the resource skills that have been defined for the organization.
    -   **Rating value**: Defines the level of proficiency that the resource has with that skill or characteristic.
        -   The drop-down will be populated will all ratings defined for all proficiency models.
        -   You can select the down arrow to see the specific proficiency model a rating is associated with.
-   **Category associations**: Lets you define what resource roles associated with a specific resource.
    -   Multiple resource roles / category associations can be defined for one resource.

    ![Field Service Tab Window](../media/URS-Unit3-2.png)

-   **Resource Territories**: Lets you define the specific territories that a resource belongs to. A single resource can be associated with multiple territories.

    ![Set Calendar Associates](../media/URS-Unit3-3.png)

-   **Work Templates**: Used to define the working hours that a resource is available to be scheduled within.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2KoUJ]

### Defining a resource's work hours

When you are scheduling resources on the schedule board, the resources working hours are used to help determine availability. Each resource that you create needs to have their working hours and time zone information defined to ensure that they are being displayed correctly and are not potentially being scheduled outside of times they are available. Resource working hours can be defined in one of two ways:

-   **Set Work Hours button**: Lets you manually define the work hours schedule for a resource. Schedules can be defined daily or weekly and applied moving forward.
    **Work hours can be set to**:
    -   Be the same for each day
    -   Vary by day
    -   None

Make sure that the time zone is set to the correct time zone for the resource.

![Additional Resource Territories](../media/URS-Unit4-1.png)

-   Apply a work hours template: Lets you associate the resource with an existing work hours template. Templates are based on an existing resource working hours.
    -   Work hour templates are applied by selecting the resource(s) you want to apply the template to and clicking the **set calendar** button.
    -   Work Hour Templates can be created under **settings** \> **work hour templates**.

Depending on the specific types of resources that you are creating, there may be additional items that need to be defined to ensure that they can be scheduled appropriately.
