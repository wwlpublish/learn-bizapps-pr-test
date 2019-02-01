Before an organization can begin to start scheduling items using Universal Resource Scheduling (URS), there are several components that will first need to be configured to ensure that items can be effectively
scheduled depending on the organization needs.

Organizations should consider items such as the following:

-   What type of items are we scheduling?
    -   Can resources be scheduled for multiple items in a single day (break fix, appointments, etc.), or do they tend to only work on one item for multiple days at a time (projects).

-   What does an unscheduled item look like?
    -   Can there be multiple status for an unscheduled item?
-   What does a scheduled item look like?
    -   Is there a difference between just being scheduled and working on it?
    -   What about items like breaks and travel time? How does that impact booking statuses?
-   Will you be leveraging GPS information?
    -   Where are resources dispatched from? (A central office, their home, it depends)
-   What factors can impact scheduling of a resource?
    -   Location? Skills or Certifications?

While the list above is by no means a complete list, it does help in identifying the types of items that need to be considered to ensure that when you are configuring URS settings, you are considering everything that could potentially impact how items are scheduled.

### Where to begin

The first thing you want to configure before you do anything else in URS is its mapping functionality. By default, URS does not connect to any specific mapping provider. This can be modified by going to **Settings**
\> **Administration** \> **Scheduling Parameters**. From scheduling parameters, you can control items like how often the schedule board will refresh (default 30 seconds), and the unit and radius that will be used by the schedule assistant when offering recommendations. For example, setting the default radius unit to miles and the default radius value to 20 would mean that when resources are suggested, only qualified resources within a 20-mile radius sill be suggested. You want to take some time and consider what is specifically needed here to ensure optimal success when configuring other components.

By default, the connect to maps field will be set to No. You will need to set this to yes to ensure that the schedule board, and schedule assistant will use maps to schedule items. By default, it will use Bing maps, but you can  configure it to work with any mapping provider, by providing a specific Map API Key value for the mapping provider you want to use in the Map API Key field. Additionally, organizations can configure a custom mapping entity to populate items like longitude and latitude if needed.


![Connect to maps](../media/URS-Unit2-1.png)

### Organizational units

Organizational Units are used to group different resources together in containers. Organizational units could be leveraged when you have resources that are all located in a specific location. For example, a software company might have resources that are in France, the United States, and Germany. An Organizational Unit could be created for each of these locations where resources are stored. This model is typically used when URS is going to be leveraged for more project-based scheduling.

Another option where Organizational Units are often leveraged, is as locations that resources might be dispatched out of. For example, an organization might have offices in Seattle, Tacoma, and Portland.
Organization Units could be created for each of those locations. When an Organizational Unit is going to be used to define a dispatching location, it needs to have valid Latitude and Longitude settings
defined. These can be specified on the Scheduling tab of the Organization Unit.

> [!NOTE] 
> The organizational unit entity, is not geo-coded like other entities. You will need to use a mapping provider (ex. Bing) to find the physical location address and copy the latitude and longitude
information to the organizational unit.

### Resource skills, roles, and proficiency models

Some items that are going to be scheduled may require the resource to have a certain role or that they possess a specific skill or certification to work on it. For example, to perform a security system install on a specific brand of security camera, the person being scheduled must be a certified installer and be highly skilled at installing that specific brand of security camera. To assist in these scenarios URS lets organizations define the following in the
application:

-   **Resource Roles**: Specifies a specific role(s) in an organization that can be associated with different resources. Roles can be added to specific recourses and schedulable items like a work order to ensure that only resources with that role are suggested as people to work on an item.
    -   Examples of common resource roles include: Developer, Solution Architect, technician, and functional consultant.
    -   A single resource can have multiple roles assigned to them. For example, a resource may have a developer and technician role assigned to them.

-   **Resource Skills**: They specify a specific skill or certification that can be associated with different resources. They are also referred to as characteristics in Field Service. Each characteristic will need to have a Characteristic Type defined. There are two options available:
    -   Skill:
    -   Certification: Resource Skills can also be used to support specific scenarios where resources may need to possess specific access to something, like a building or need a specific level of security clearance.

Examples of Resource Skills include:

-   A certification like A+, MSCE, etc.
-   A skill set like C\#, Azure, Exchange, etc.
-   Access or security clearance like Building 12 access, or level 1 security clearance.

It is very likely that a single resource might have multiple skills
assigned to them.

-   **Proficiency Models**: Are used in conjunction with resource skills to define how proficient someone is on an item. Proficiency models can be leveraged to define different types of scenarios.

  |Product Proficiency  | Security Clearance  |
  --------------------- |-------------------- |
  |Familiar             | Level 1 Clearance   |
  |Good                 | Level 2 Clearance   |
  |Skilled              | Level 3 Clearance   |
  |Highly Skilled       | Level 4 Clearance   |
  |Master               | Level 4 Clearance   |

### Booking statuses

Booking statuses are used to communicate the status of a booking. Organizations can create specific statuses to reflect their specific needs. For example, after an item has been scheduled it can fall into one of the following:

-   Scheduled
-   Traveling
-   In Progress
-   Completed

We can define each of these statuses in the application, additionally organizations can associate each status with a specific color, and image. The color and Image would then be displayed on the schedule board for any item that is currently in that status.

You should consider which types of items you want to use the schedule board for and which statuses those items could be in. You many create several different booking statuses to reflect those items. For example, if you wanted to display time off on the calendar, you would want to create booking statuses for common time of items like vacation, business events, of personal time. This will ensure that everything that needs to be shown is populating as intended.


![Scheduling Dashboard](../media/URS-Unit2-2.png)

### Requirement statuses

Requirement statuses are like booking statuses, but they are associated with the scheduling requirement. Typically, you will not need as many requirement statuses, because they do not have the same lifecycle. A
common example of requirement statuses might include:

-   **Active**: A requirement that has not yet been scheduled in the system
-   **Completed**: a requirement that has successfully been scheduled and has a related booking created.
-   **Canceled**: A requirement that no longer needs to be scheduled for some reason.

### Other considerations

Since every organization is unique, and may have their specific scheduling needs, there are other items that can potentially be
configured as needed. These Items include:

-   **Resource Groups**: Used to group together multiple resources that can be used to work on items.
-   **Resource Group Templates**: Used to create templates that can be used to quickly create and deploy resource groups that will be used most commonly.
-   **Fulfillment Preferences**: Help to specify how items can be scheduled. For example, a fulfilled preference, might define that when attempting to schedule an item, it should use intervals of 60 minutes, and that they should be scheduled at the top of every hour.
-   **Work Hour Templates**: Used to create templates that can be assigned to resources to define the hours that they are available to be scheduled for to work on items. For example, let's say that you have multiple technicians in a specific time zone that work from 8:00 AM to 5:00 PM. A work hour template can be created and associated with each of those resources.
-   **Priorities**: Used to note the priority of the requirement. Priorities can be taken into consideration to ensure that items with higher priorities are scheduled with items that are considered lower priorities.
-   **Business Closures**: Specifies when an organization is not open such as holidays.
