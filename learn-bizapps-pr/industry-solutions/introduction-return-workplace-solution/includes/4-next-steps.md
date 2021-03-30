The Return to Workplace apps require their own environment for deployment. The Return to Workplace solution can be obtained and deployed from [AppSource.](https://appsource.microsoft.com/en-us/product/dynamics-365/msemr.pprtwsoln)

> [!div class="mx-imgBorder"]
> [![Screenshot from Microsoft AppSource page where you can get the solutions.](../media/appsource.png)](../media/appsource.png#lightbox)

For the more experienced Dynamics 365 or Power Platform consultant, the steps should be easy to follow. From a high-level you should complete the following:

1.  Create a Dataverse environment that is unique for this purpose.

1.  Obtain and install the solution from AppSource.

1.  Configure and Publish Power BI dashboards.

1.  Schedule report refresh.

1.  Embed the Power BI report in the model-driven app.

1.  Publish a theme (optional).

1.  Share the canvas app with users.

1.  Set the security roles.

1.  Enable flow.

1. Deploy the portal.

If you are looking for detailed steps to complete these tasks, you can find them at [Microsoft docs](https://docs.microsoft.com/dynamics365/industry/return-to-workplace/deploy/?azure-portal=true).

For deployments in the US Government cloud, there are a few variations in the above steps. The details can be found on the [docs](https://docs.microsoft.com/dynamics365/industry/return-to-workplace/deploy?azure-portal=true#appendix-deploy-the-app-and-publish-power-bi-dashboard-us-government-customers-only) page.

Additionally, the expected extensions and platform capabilities are still available to you as a maker in the environment. Extend the configuration as needed but be mindful of the impact to the solutions you have deployed. Ideas on functionality you could extend include:

-   Customizing the information in the notifications

-   Adding more details or widgets to the dashboards

-   Adding more notifications

-   Customizing views

-   Modifying cosmetic details in Power Automate flows such as the "from" address on certain notices sent by the system

-   Automating more of the process such as the Employee Cases and the actions from record changes as triggers

Ensure you are following best practices including using solutions and following proper ALM practices when building on the Return to Workplace solution.