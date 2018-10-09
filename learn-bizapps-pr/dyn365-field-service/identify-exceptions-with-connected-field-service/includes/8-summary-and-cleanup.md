In this module you have connected a real device to your deployment.  You have modified the template application to send alerts to the Dynamics 365 Connected Field Service add-on.  You have also used the advanced anomaly detection capabilities of Azure Stream Analytics to implement more complex dynamic rules.   And finally, you seen several of the extension points where you store detail telemetry as well as hook in your own custom processing of the device data stream. 

### Cleaning Up 

When you deployed the Connected Field Service add-on it created an Azure Resource Group in your subscription that contains all the components of the template.  If you are going to complete other learning in the near future you might want to wait to do the clean up until you have completed any of the other modules that require a Connected Field Service deployment. 

If you are done, and ready to clean up all you need to do is simply delete the resource group in Azure.  You can accomplish that in two ways, either via the Azure Portal or from the Azure Cloud Shell. 

**Via the Azure Portal**

N- avigate to the Azure Portal [https://portal.azure.com ](https://portal.azure.com )
- On the left side choose Resource Groups 
- Type your resource group in the filter by name or find it on the list 
- Select the Resource Group to open the detail page 
- After confirming it is the right Resource Group, select all the items in the group and click Delete 

**Via the Azure Shell**

Navigate to [https://shell.azure.com ](https://shell.azure.com )
- List your accounts using command az account list 
- Select your account using command: az account set -s “My Account Name” 
- Delete the resource group using command: az group delete -n “Your Resource Group Name”