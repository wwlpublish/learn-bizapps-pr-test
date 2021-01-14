After you have become familiar with your environments and resources, your next step is to consider governance processes for your apps. This step requires gathering additional information about your apps from your makers, audits from specific connectors, or app usage.

The breakdown of the governance components for the audit process is as follows:

-   Developer Compliance Center (canvas app)

-   Compliance Detail Request (flow)

Multiple governance components are provided in the CoE Starter Kit; each will require configuration to install. The installation instructions in this article have been segmented based on the set of components that should be grouped and installed together. Dependencies on other segments are outlined in each section.

## Import the solution

The Core Components solution is required for the Audit and Report Components solution, or any other component in the starter kit, to work.

1.  Follow the instructions that are detailed under Set up core components.

1.  Import the CenterOfExcellenceAuditComponents_x_x_x_xx_managed.zip file.

1.  Create a new connection to all connectors.

	> [!div class="mx-imgBorder"]
	> [![Import Center of Excellence audit components.](../media/import-audit-components-ss.png)](../media/import-audit-components-ss.png#lightbox)

1.  Update the Environment Variable values. Environment variables are used to store application and flow configuration data, meaning that you only have to set the value once for each environment and that it will be used in all necessary flows and apps in that environment.

	|     Name                             |     Current value                                                                                                                                                                                                                                                                                          |
	|--------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
	|     Auto Delete   On Archive         |     Determines   whether apps are deleted when they're archived in the following flow: Admin \| App Archive and Clean Up - Check Approvals and Archive.                                                                                                                                                  |
	|     Developer   Compliance Center    |     Leave this   blank on import and update the environment variable after the import has   finished by first navigating to the details page of the Developer Compliance   Center (canvas app) that is included with this solution and then copying the web link (to   launch the app) and pasting it into this variable.    |
	|     Production   Environment         |     Determines if   the environment is Production or Dev/Test. True (the default) will mean that   the approvals are sent to app/flow owners. False will send those approvals to   the admin email.                                                                                                        |

1.  Select the **Import without adding values to the Environment Variables** option because you will update the values later. For more information, see the following *Update environment variables* section.

Update environment variables
----------------------------

The step to update environment variables should be completed after you have imported the solution. Environment variables are used to store application and flow configuration data, meaning that you only have to set the value once for each environment and that it will be used in all necessary flows and apps in that environment.

All flows in this solution depend on all environment variables being configured.

Select **See Environment Variables** to set the values that are described in the following table.

|     Name                             |     Current value                                                                                                                                                                                                              |
|--------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Auto Delete   On Archive         |     Determines   whether apps are deleted when they're archived in the following flow: Admin \| App Archive and Clean Up - Check Approvals and Archive.     Value must be   Yes or No. A default value of No is provided.    |
|     Developer   Compliance Center    |     Go to   the details page of the Developer Compliance Center (canvas app) that is included   with this solution and then copy the web link (to launch the app) and paste it   into this variable.                                  |
|     Production Environment           |     Determines if   the environment is Production or Dev/Test. True (the default) will mean that   the approvals are sent to app/flow owners. False will send those approvals to   the admin email.                            |

## Initialize flow approval tables in your environment

The following flows use the built-in approval actions of Power Automate. In the background, the built-in approval actions use Dataverse. If you've installed the solution in a new environment, the approval tables must be initialized. The easiest way to accomplish this task is to create a "dummy" approval flow.

-   Admin

-   App Archive and Clean Up - Start Approval, Admin

-   Flow Archive and Clean Up - Start Approval, Admin

-   App Archive and Clean Up - Check Approval, Admin

-   Flow Archive and Clean Up - Check Approval, Collect audit log data

1.  Go to [flow.microsoft.com](https://flow.microsoft.com/?azure-portal=true).

1.  Select **+ New > Instant (From Blank)**.

1.  Select the **Manually trigger a flow** option as the trigger and then enter **Admin | Dummy Approval Flow** as the name.

	> [!div class="mx-imgBorder"]
	> [![Select Manually trigger a flow and then enter Admin and Dummy Approval Flow as the name.](../media/initial-flow-approval-tables-environment-ss.png)](../media/initial-flow-approval-tables-environment-ss.png#lightbox)

1.  Select **+ New Step** to add an approval action to the flow, and then search for and select **Create an approval**.

1.  Select a dummy title and then enter your email address in the **Assigned to** field.

	> [!div class="mx-imgBorder"]
	> [![Initialize the flow approval tables process.](../media/initialize-flow-approval-tables-ss.png)](../media/initialize-flow-approval-tables-ss.png#lightbox)

1.  In the upper-right corner, select **Test** and then select **I'll perform the trigger action**.

1.  Select **Save & Test**.

1.  Select **Run Flow**.

1.  Select **Solutions** in the left panel. You should now see two new flow approval solutions, which helps verify that the process has succeeded.

    > [!div class="mx-imgBorder"]
	> [![Two new flow approvals.](../media/two-flow-approvals-ssm.png)](../media/two-flow-approvals-ssm.png#lightbox)

## Activate the flows

This Governance Components solution contains flows that you will need to manually turn on when you are ready to use them:

-   Admin | App Archive and Clean Up - Start Approval

-   Admin | Approval Clean Up

-   Admin | Check Approvals

-   Admin | Flow Archive and Clean Up - Start Approval

-   Admin | Compliance detail request

-   Teams Admin | Ask for Business Justification when Microsoft Teams environment is created

-   Teams Admin | Weekly Clean Up of Microsoft Teams environments

