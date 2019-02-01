Universal Resource Scheduling now provides the ability to handle different scheduling scenarios where multiple resources may need to be scheduled. There have been some enhancements made to the schedule board to assist in the scheduling process.

## Split View

When you are working with resource pools and crews, it is often easier to schedule items and make decisions if you know the actual resources that are in those crews and pools. To assist in this process, the schedule board contains a new option to view the resources that are associated with a pool or crew in split view. Split view can be accessed by right-clicking on either a resource pool or crew, and selecting view pool/crew resources in split view.


![Split View](../media/rso-unit-5-1.png)

## Working with Resource Pools

When you open a resource pool in split view, the individual resources in the pool will be displayed at the bottom. Because the resource pool is used as the place holder for the scheduled item, it will appear as a scheduled item for the pool. Once you have identified the specific resource that you want to move the booking to, you can right-click on the booking and select substitute resource. If you can see from the schedule board that a resource in the pool is available, you can manually select the resource. If you select to find a substitute, the schedule assistant will open and only offer members of the resource pool that match the skill/characteristics defined in the resource.

## Working with Crew Scheduling

When you open a crew in split view, the individual resources in the pool will be displayed at the bottom like with resource pools. The major
difference with crews, is that when a crew record is scheduled, a booking record is not only created for the crew, but a booking record
for each member of the crew is created and scheduled as well. If the booking needs to be moved, reassigned, or deleted, it should be done at
the crew level. This will ensure that the changes will flow to all the resources defined in the crew.

## Scheduling a Requirement Group

Since requirement groups are a separate entity from requirements, they need to be scheduled separately. When a requirement group is scheduled,
any requirements defined on the group will also be scheduled as well.

By default, the requirements panel on the schedule board is not configured to display requirement groups. If an organization has the need to schedule requirement groups, they will need to add any necessary requirement views to the requirements panel. It requires two steps to
add requirement groups to the panel.

-   Create and define the necessary view on the Requirement Groups entity.
-   Add the Requirement Group entity views to the Requirements Panel on the view.

Requirement Group entity views can be modified by going to **Settings** \> **Customizations** \> **Customize the system**. After you expand the
Requirement Group entity, you can edit or create the necessary views you want to use.

Once the views are ready, you need to add the resource requirement group views to the requirements panel. This is done by selecting the tab
settings button for the schedule board tab you want to modify.


In the Requirements panel, you will need to switch the view to display requirement group views. When it is displaying requirement group views,
select the view you want to use and provide a name. Only published public views can be used in the requirements panel. After you click the
add button and apply the new requirement group view, it will display on the requirement panel.

![Requirements panel](../media/rso-unit-5-4.png)


