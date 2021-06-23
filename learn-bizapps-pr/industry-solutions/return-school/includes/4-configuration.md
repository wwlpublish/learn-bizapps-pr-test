The Return to School apps require their own environment for deployment. You can obtain and deploy the Return to the Workplace solution from [Microsoft AppSource](https://appsource.microsoft.com/product/dynamics-365/msemr.pprtwsoln/?azure-portal=true).

For the more experienced Microsoft Dynamics 365 or Microsoft Power Platform consultant, the steps should be simple. From a high-level, you should complete the following steps:

1.  Create a Microsoft Dataverse environment that is unique for this purpose.

1.  Create a portal.

1.  Obtain and install the solution from AppSource.

1.  Configure and publish the **Return to School** dashboard.

1.  Set the security role.

1.  Enable flows.

1.  Set up the portal URL environment variable.

For more information, see [Deploy Microsoft Return to School](https://docs.microsoft.com/dynamics365/industry/return-to-school/deploy/?azure-portal=true).

Additionally, the expected extensions and platform capabilities are still available to you as a maker in the environment. Extend the configuration as needed but be mindful of the impact to the solutions that you have deployed.

Ideas on functionality to extend:

-   Editing the portal to include your school colors or mascots

-   Automating the creation of passes to be used for appointments

-   Customizing the information in the notifications

-   Adding notifications for administrators to track building traffic

-   Adding notifications for janitorial staff to plan for cleaning facilities

-   Adding notifications for visitors for appointment and follow-up reminders

-   Modifying cosmetic details in Power Automate flows such as the **From** address on certain notices that are sent by the system

Ensure that you are following best practices, including using solutions and following proper ALM practices when building on the Return to School solution.

