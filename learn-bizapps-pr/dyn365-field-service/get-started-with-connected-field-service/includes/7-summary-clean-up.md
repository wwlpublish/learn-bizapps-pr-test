## Summary and Clean Up

In this module you have completed the deployment of the Dynamics 365 Connected Field Service add-on.  You have also registered a simulated device and saw first hand how alerts are raised into Dynamics 365 for further evaluation.

The next steps from here would be to look at how you want to handle the IoT Alerts and customize the business process for your particular scenario.  You would also depending on your scenario need to customize some of the out of the box components to handle the actual telemetry your devices will be generating.

**Cleaning Up**

When you deployed the Connected Field Service add-on it created an Azure Resource Group in your subscription that contains all the components of the template.  If you are going to complete other learning in the near future you might want to wait to do the cleanup until you have completed any of the other modules that require a Connected Field Service deployment.

If you are done, and ready to cleanup all you need to do is simply delete the resource group in Azure.  You can accomplish that in two ways, either via the Azure Portal or from the Azure Cloud Shell.

**Via the Azure Portal**

-	Navigate to the Azure Portal [https://portal.azure.com](https://portal.azure.com "Azure Portal")
-	On the left side choose Resource Groups
-	Type your resource group in the filter by name or find it on the list
-	Select the Resource Group to open the detail page
-	After confirming it is the right Resource Group, select all the items in the group and click Delete

**Via the Azure Shell**

- Navigate to [https://shell.azure.com](https://shell.azure.com "Azure Shell")
- List your accounts using command az account list
-	Select your account using command: az account set -s “My Account Name”
-	Delete the resource group using command: az group delete -n “Your Resource Group Name”
