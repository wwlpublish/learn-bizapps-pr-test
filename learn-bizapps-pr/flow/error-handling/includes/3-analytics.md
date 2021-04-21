Power Automate has built-in analytics available for every flow. Analytics includes actions, usage, and errors.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Automate with the Analytics button highlighted.](../media/flow-analytics.png)](../media/flow-analytics.png#lightbox)

The **Actions** analytics provides an overview of all the action requests by day. The graph provides important information about how many of these actions are billable. You have the flexibility to change the range to view the last 30, 14, or 7 days.

> [!div class="mx-imgBorder"]
> [![Screenshot of Analytics with the Actions tab selected.](../media/actions.jpg)](../media/actions.jpg#lightbox)

The **Usage** analytics provides a detailed breakdown of all the flows that have run in the range you selected. These visuals provide a good overview of the total number of flows that have run and how many have failed versus run successfully. You have the flexibility to change the range to view the last 30, 14, or 7 days.

> [!div class="mx-imgBorder"]
> [![Screenshot of Analytics with the Usage tab selected.](../media/usage.jpg)](../media/usage.jpg#lightbox)

The **Errors** analytics provides comprehensive details of all the errors you flow has faced in the range you selected. **The Error details** visual provides important details that can help isolate the root cause of the failure.

> [!div class="mx-imgBorder"]
> [![Screenshot of Analytics with the Errors tab selected.](../media/errors.jpg)](../media/errors.jpg#lightbox)

## Built-in errors dashboard

Built-in dashboards are available in Power Automate for both environment admins and flow makers.

Environment admins can access analytics for Power Automate in the Microsoft Power Platform admin center. The reports provide insights into runs, usage, errors, types of flows created, shared flows, and details on connectors associated with all the different flow types like automated flows, button flows, scheduled flows, approval flows, business process flows. These reports are not available for the UI flows type.

To access these reports:

1. Go to the navigation bar on the left side.

1. Select Analytics.

1. Select Microsoft Power Automate.

1. View the reports on the right side.

To select the correct environment, select **Change Filters**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Platform admin center on the Analytics Power Automate page Errors tab with the Change filters option highlighted.](../media/filters.png)](../media/filters.png#lightbox)

The out-of-box analytics features available include:

- Run

- Usage

- Created

- Shared

- Connectors

Below is a screenshot of how the **Error** analytics can be because it gives you an overview of all the errors you are getting in that environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Cloud flows tab showing errors by error type.](../media/cloud-flows.png)](../media/cloud-flows.png#lightbox)

The flow level analytics has its own Error section that provides deep insight for that specific flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Errors tab with the Error details table showing the links in the Last Error Detail column highlighted.](../media/flow-level-error.jpg)](../media/flow-level-error.jpg#lightbox)

In the screenshot above, in **Error** details, you can see the **Last Error Detail** column. Hovering over it will provide you a direct link to the failed run and its details.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Last Error Detail link hovered and showing the link address.](../media/error-details.jpg)](../media/error-details.jpg#lightbox)

If you select it, you'll have to confirm the navigation because it will open another tab in your browser and take you there.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Confirm Navigation dialog.](../media/confirm-navigation.jpg)](../media/confirm-navigation.jpg#lightbox)

After you've selected OK and the new browser tab has opened, below is what you will see. You get to see which step failed and what the reason for the failure was. Additionally, it provides links to the Power Automate community where any questions asked for a similar issue can help you troubleshoot.

> [!div class="mx-imgBorder"]
> [![Screenshot of the error details in the browser showing which flow run failed and other details about the error.](../media/flow-level-error-details.jpg)](../media/flow-level-error-details.jpg#lightbox)

In the above scenario, the flow failed at the HTTP action and thanks to the Error details we know that the error is because of insufficient privileges.

> [!div class="mx-imgBorder"]
> [![Screenshot of the H T T P action dialog.](../media/http-action.png)](../media/http-action.png#lightbox)

As you can see above, the HTTP action is making a GET call to Microsoft Graph and the current user who is running this flow doesn't have access to do so. After the user was provided the correct access level to Microsoft Graph, the flow ran successfully.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow with the message Your flow ran successfully.](../media/success.png)](../media/success.png#lightbox)
