# Exercise - run the Portal Checker

The purpose of this hands-on-lab is to see how the Portal checker can identify potential portal issues

## Learning objectives

At the end of these exercises, you will be able to accomplish the following:

* Run the portal checker
* Respond to the mitigation advice
* Re-run the portal checker to confirm the issue has been addressed

**Estimated time to complete this exercise**: 10 to 15 minutes

## Before we begin

### Prerequisites

For this exercise you will need to have the following in your environment:

* A Power Apps portal provisioned. If you do not have a Power Apps portal available, follow [Create Portal](https://docs.microsoft.com/powerapps/maker/portals/create-portal/?azure-portal=true) instructions to create one.
* Access to the Power Apps maker portal.

## Scenario

### High-level steps

In this exercise we will make a few settings changes to our portal metadata and then run the portal checker tool from the Power Apps portal admin center and evaluate the results. Once the issue has been addressed, we will re-run the portal checker to ensure that the issue is taken care of.

* Locate the **Site Setting** named `Header/OutputCache/Enabled` and update the value to **False**

* Refresh the Cache

* Run the Portal Checker

* Note warning message for Header Output cache

* Locate the **Site Setting** named `Header/OutputCache/Enabled` and update the value to **True**

* Refresh the Cache

* Run the Portal Checker

* Note message for Header Output cache

### Detailed steps

#### Launch Portal Management app

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true).
1. Make sure correct environment is selected in the environment selector in the top right-hand corner.
1. From the list of Apps, locate and open the Portal Management app (Type = Model-driven).
1. Select **Site Settings**.
1. Locate the **Site Setting** named `Header/OutputCache/Enabled`, update the `Header/OutputCache/Enabled` value to **False**, and press **Save**.
1. Leave the Portal Management app open.
1. From another browser tab or session, navigate to the [maker portal](https://make.powerapps.com/?azure-portal=true) and sign in.  
1. Locate your portal app and click on the ellipses (...) and select **Edit** to open the Portal Studio.
1. Press **Browse website** to clear the cache.
1. Close the website.
1. Navigate to the [maker portal](https://make.powerapps.com/?azure-portal=true) and sign in.  
1. Locate your portal app and click on the ellipses (...) and select **Settings**.
1. On the fly-out window to the right, choose **Administration**.
1. The Power Apps portals admin center will appear, choose **Run Portals checker**.
1. In the screen, press the **Run Portals Checker** button.
1. Note that the Header output cache has a warning, expand the message to get more details.
1. Leave the Portal Checker open.
1. Return to the Portal Management app.
1. Select **Site Settings**.
1. Locate the **Site Setting** named `Header/OutputCache/Enabled`, update the `Header/OutputCache/Enabled` value to **True**, and press **Save**.
1. From another browser tab or session, navigate to the [maker portal](https://make.powerapps.com/?azure-portal=true) and sign in.  
1. Locate your portal app and click on the ellipses (...) and select **Edit** to open Portal Studio.
1. Press **Browse website** (this will clear the cache).
1. Return to the Power Apps portals admin center, select **Run Portals checker**.
1. In the screen, press the **Run Portals Checker** button.
1. Note that the Header output cache issue has been resolved.

> [!div class="mx-imgBorder"]
> [![Portal Checker](../media/portal-checker-exercise.png)](../media/portal-checker-exercise.png#lightbox)
