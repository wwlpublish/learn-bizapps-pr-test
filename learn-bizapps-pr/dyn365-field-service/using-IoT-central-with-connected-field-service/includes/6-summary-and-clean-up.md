In this module you have created an application with IoT Central and connected it to your Dynamics 365 for Field Service using the Connected Field Service add-in.  Azure IoT Central abstracts many of the more technical aspects of building an IoT solution.  Using the portal, you are able to build an IoT solution similar to how you would customize Dynamics 365.  Using both together you can rapidly bring device telemetry and interaction into the Dynamics 365 solution.  By using Azure IoT Central you can get your solution shipped quicker.

In the near-term roadmap of the Connected Field Service add-on, expect to see more integration with Azure IoT Central. 

## Cleaning Up ##

The trial you created of Azure IoT Central will simply expire at the end of the trial with no further action required.  If you want to re-create your trial from the beginning you can delete your existing trial at any time.  Currently you are only allowed one active trial at a time in an Azure subscription. 

When you deployed the Connected Field Service add-on it created an Azure Resource Group in your subscription that contains all the components of the template.  If you are going to complete other learning in the near future you might want to wait to do the cleanup until you have completed any of the other modules that require a Connected Field Service deployment.

If you are done, and ready to cleanup all you need to do is simply delete the resource group in Azure.  You can accomplish that in two ways, either via the Azure Portal or from the Azure Cloud Shell.

**Via the Azure Portal**

* Navigate to the [Azure Portal](https://portal.azure.com)
- On the left side select **Resource Groups**
- Type your resource group in the filter by name or find it on the list
- Select the **Resource Group** to open the **Detail** page
- After confirming it is the right Resource Group, select all the items in the group and click **Delete**

**Via the Azure Shell**

- Navigate to <https://shell.azure.com>
- List your accounts using command: az account list
- Select your account using command: az account set -s “My Account Name”
- Delete the resource group using command: az group delete -n “Your Resource Group Name”
