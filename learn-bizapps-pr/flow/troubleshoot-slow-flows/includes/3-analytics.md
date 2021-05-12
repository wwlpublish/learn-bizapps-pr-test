As the Power Automate flow consumption increases, it's important to monitor the health of these flows. Analytics is available at the flow level and the environment level.

## View analytics at the flow level

The flow level analytics can be accessed from two locations. One is from the list of flows you have access to.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Cloud flows tab with the ellipsis button for a flow in the list selected and the Analytics option highlighted.](../media/image-14.png)](../media/image-14.png#lightbox)

The second is in the flow settings.

> [!div class="mx-imgBorder"]
> [![Screenshot of the details for a flow with the Analytics button highlighted.](../media/image-15.png)](../media/image-15.png#lightbox)

The flow level analytics provides information such as Actions, Usage, and Errors. Each of them is a Power BI report and the data presented is in the range of last 7, 14 and 30 days.

Here's an example of what the flow **Actions** analytics looks like. It presents the total number of billable actions that have run so far.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Actions tab showing a graph of the last 30 days. The ellipsis button is selected and Sort ascending is set to AggregationDate.](../media/image-16.png)](../media/image-16.png#lightbox)

Here's an example of what the flow **Usage** analytics looks like. This one gives you a breakdown of the total number of runs you had in a day and how many of them were successful and failed. This report only provides numbers.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Usage tab showing graphs of runs by day, number of runs, and flow runs trend.](../media/image-17.png)](../media/image-17.png#lightbox)

The **Errors** also provide you a total count by day, in addition to details. Details such as what are the error types and details of that error.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Errors tab showing graphs of errors by day and errors by type, and a list of error details.](../media/image-18.png)](../media/image-18.png#lightbox)

## View analytics at the environment level

Admins with the following roles and a license can view the reports in Power Automate analytics:

- Environment Admin - can view reports for the environments that the admin has access to.

- Power Platform admin - can view reports for all environments.

- Dynamics 365 admin - can view reports for all environments.

- Microsoft 365 Global admin - can view reports for all environments.

The reports provide insights into runs, usage, errors, types of flows created, shared flows, and details on connectors associated with all the different flow types like automated flows, button flows, scheduled flows, approval flows, business process flows. Each of them is a Power BI report and the data presented is in the range of last 7, 14 and 28 days.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Platform admin center on the Power Automate page with Change filters selected to open the Filters dialog.](../media/image-19.png)](../media/image-19.png#lightbox)

By default, you see the Runs report. It provides a view into the daily, weekly, and monthly run data of all flows in an environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Runs tab showing graphs of daily, weekly, and monthly runs.](../media/image-20.png)](../media/image-20.png#lightbox)

This report provides insights into the different types of flows in use, the trends, and the flow creator's names.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Usage tab showing graphs of types of flows in use and use trend, and a list of cloud flows in use.](../media/image-21.png)](../media/image-21.png#lightbox)

This report provides insights into the types of flows created, trends, and details like the created date and the creator's email address.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Created tab showing graphs of types of flows created and creation trend, and a list of cloud flows created.](../media/image-22.png)](../media/image-22.png#lightbox)

This report provides insights into recurring error types and details like the error count, creator's email address, last occurred time, and the creator's email address for each flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Errors tab showing a graph of errors by type and a list of errors by cloud flows.](../media/image-23.png)](../media/image-23.png#lightbox)

This report provides details on the flows shared and trends in the environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Shared tab showing graphs of types of flows shared and flows share trend, and a list of flows shared.](../media/image-25.png)](../media/image-25.png#lightbox)

This report provides details on connectors and their associated flows. Metrics like the number of calls from each flow per connector, flow runs, and the flow creator's email address are available for both standard and custom connectors.

> [!div class="mx-imgBorder"]
> [![The Connectors tab showing graphs of connectors by flow runs and calls, and lists of connector usage across flows and flows using connectors.](../media/image-26.png)](../media/image-26.png#lightbox)
