In previous lessons, we learned about the premium experiences in AI Builder, which requires capacity, and then how to purchase such capacity.

In this unit, you will
-   Identify how to manage the AI Builder capacity: assign, unassign
-   Examine how you can check the AI Builder capacity assignment
-   Distinguish the different ways to perform AI Builder action: Environment with AI Builder capacity assigned, or AI Builder Trial license at user level.

Premium experiences like performing a Predict action on a prebuilt model, or launching a Training action on some custom model like Object Detection requires capacity to be available in the current environment.

What is an environment? Environment is a Power Platform concept, which defines a storage and working area with usually a Common Data Service database -- required for AI Builder to work correctly -- and Apps, AI Models, and Flows created on it. Tenants may use Environments to distinguish Prod environments from Dev environments for instance, and sometimes to separate area between Enterprise divisions. It's also called Organization in Dynamics namespace.

As we saw in previous lesson, when you purchase AI Builder Capacity Add-on, corresponding capacity is made available at tenant level. In order to make it available at Environment level, you need to assign it.

To do so, you can go to Power Platform Admin center, in the Analytics/Capacity section:

<https://admin.powerplatform.microsoft.com/analytics/capacity>

If your tenant is entitled to some Power Platform Capacity Add-on, like AI Builder Capacity Add-on, you will see an 'Add-ons' tab

![A screenshot of a computer description automatically 
generated](../media/image5.png)

In this section, you will be able to assign, and unassign AI Builder credits to your environments.

Clicking "Assign to an environment" button at the top of the page will open a side panel. In this panel, select the environment you want to modify, then enter the new number of AI Builder credits you want this environment to be assigned, and click Save.

The total of assigned AI Builder credits across environment cannot exceed the number of available AI Builder credits at tenant level.

So if you want to reassign some amount from one environment to the other, please set the new lower number of first environment before setting the new higher number of second environment.

![A screenshot of a cell phone description automatically generated](../media/image6.png)

If you assign more credits than remaining, you won't be able to save and an error message will warn you that 'Quantity cannot exceed the remaining'.

Once saved, the amount is directly assigned, and users can begin performing premium actions.

Goal of this assignment step is, for an admin, to correctly manage your capacity across your environments. You may want to limit the number of AI Builder credits that are used in dev, so most of it can be used in Prod environment. At any moment, you can purchase additional AI Builder Capacity Add-On, and distribute the additional AI Builder credits among existing environments.

The total number of assigned AI Builder credits can be seen in the first tab of Analytics/Capacity, in the Add-On part of the screen, at the bottom of the page:

![A screenshot of a cell phone description automatically generated](../media/image7.png)

Here, we can see that 910,000 AI Builder credits have been assigned out of the 1,000,000 which have been purchased.

When a given environment has no AI Builder credit assigned, by default, all premium actions are blocked. In that case, the only way to perform premium actions is to have an AI Builder Trial license. An AI Builder Trial license can easily be obtained, by clicking the 'Start trial' button in the Trial banner.

The Trial banner is displayed at the top of AI Builder pages, in Environments where there is no AI Builder credit assigned.

Starting a trial allows a user to perform premium actions in environments without AI Builder capacity. AI Builder trial is limited in time -- 30 days -- and is limited in capacity.

When a user with a trial is performing a premium action within an environment with AI Builder capacity, then the consumption is counted against the environment capacity.

**You are now able to identify how to manage the AI Builder capacity: assign, unassign. You also know how you can check the AI Builder capacity assignment. And you distinguish the different ways to perform AI Builder action: Environment with AI Builder capacity assigned, or AI Builder Trial license at user level.**
