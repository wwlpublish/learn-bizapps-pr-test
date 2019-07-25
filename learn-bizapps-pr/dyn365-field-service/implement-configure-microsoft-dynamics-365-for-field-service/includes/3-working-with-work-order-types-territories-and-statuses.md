After you've defined your products and services, you can configure settings specific to Dynamics 365 for Field Service. A good one to begin with is work order types. 

There are several types of work orders, including
inspections, installations, preventative maintenance, or standard service calls. By clearly defining the types of work orders you'll provide, you'll optimize your reporting, scheduling, and pricing.

To define work order types, in Field Service, under **Field Service Settings**, select **Work Order Types**.

### Work Order Status

A typical work order goes through several different stages before it is considered closed and billed to a customer. For example, while a work order is open, it might be waiting to be scheduled, scheduled but not yet being worked on, scheduled and being worked on, or completed but waiting for final approval before it can be closed. Work order status defines the current state of the work order as it moves through its lifecycle.

Field Service contains the following work order status settings:

- **Open – Unscheduled:** The work order has been created but has not yet been scheduled in the system.
- **Open – Scheduled:** The work order has been scheduled and a resource has been assigned responsibility for completing the work.
- **Open – In Progress:** A field agent is actively working on the item.
- **Open – Completed:** The work has been completed and the work order might be waiting for final sign off.
- **Closed – Posted:** The work order is closed and billing can take place.
- **Closed – Canceled:** The work was not completed and the work order was canceled.

Work order status can be viewed and modified in the Field Service app by going to **Field Service Settings** > **Work Order Status**.

> [!IMPORTANT]
> We highly recommend that you **do not** customize Work Order Status settings.

Although it is possible to create new status settings, change existing status settings, and even remove status settings, it is rarely a good idea to do so. There are several workflows and other application functionality that are based on the previously mentioned status settings. Modifying or removing any of them can break this functionality. Additionally, if you create additional work order status settings, there may be additional modifications that are needed.

### Work Order Substatus

Although work order status provides a good overall look at the status of a work order, it does not always provide a complete picture. This is where work order substatus comes in. 

A work order's substatus provides additional details about the state of the work order. For example, a work order may have a status of *Open-unscheduled*. By adding a substatus, you can identify that the work order is unscheduled because you are waiting for parts to arrive, or still need a customer signature. Substatus can also be used to assist in closing work orders. A work order may have a status of *Open-completed* because it requires us to follow-up with a customer within the week to ensure that everything is still functioning as intended. This info can be included in the substatus.

You can also use a substatus to trigger scheduling processes. For example, you can ensure that a work order  waiting for parts will not display on the schedule board as an item waiting to be scheduled until its required parts have arrived.

Configure substatus settings by selecting **Field Service Settings** > **Work Order Substatus**. When you add a substatus you need to define the following:

- **Name:** Specifies the name of the substatus
- **System Status:** Defines the work order status that the substatus is associated with
- **Default Substatus:** Specifies if the substatus should be the default substatus for the associated work order status

> [!NOTE]
> When a substatus is defined as the default, it will be chosen automatically when the associated work order status is selected. It can be overwritten on the individual record as needed.

When you define a substatus, give some thought to how it will be used. For example, if you want only items with a substatus of *Parts received* to appear on the schedule board, you will need to customize the resource requirement view used to present items available for scheduling on the schedule board.


For more about view customizations, see [Create or edit a view](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-and-edit-views).

For more about status and substatus settings, refer to this video:

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Kh5e]

### Territories

Territories are used to break larger service areas into smaller areas. They can also be used as filtering criteria when attempting to schedule items. For example, let's say that an account is assigned a territory of Washington. Whenever a work order is created for that account, the work order will also have a territory of Washington. When attempting to schedule the work order by using the schedule board or schedule assistant, available resources can be filtered to include only those resources that belong to the Washington territory. 

To define territories, select **Field Service Settings**, and then, under **General Settings**, select **Territories**. After defining territories, you'll associate multiple record types with them.

These records types include:

- Work orders
- Accounts
- Resources

Resources can be associated with more than one territory. If you have resources that service multiple territories, you can add each territory to the resource to ensure that they display in search results when any of their territories are used.

### Postal Codes

To make the process of using territories easier, Field Service provides the ability to associate postal codes with service territories. When a postal code is used in a work order, the territory associated with the postal code will be added to the work order if no other territory exists for it. To define postal codes in the Field Service app, select **Field Service Settings**, and then, under **General Settings**,  select **Postal Codes**.
