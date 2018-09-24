##Summary
In this module you remotely managed IoT devices using the Dynamics 365 Connected Field Service solution.  There are several items to go into monitoring and servicing remote devices.  

We explored some of these items including:

- Examine the relationship between customer assets and IoT devices.  
- How to interact with devices using commands.
- How to leverage some of the out of the box actions to assist in automation 
- How to build business process flows that can be leveraged by CFS.  
  
The next steps from here would be to gain a deeper understanding of interacting with devices.    This would include understanding how device twins can be used to report and query information.   You should also explore some of the additional feature available for interacting with devices using commands.  This would include items like device categories as well as command and property definitions.  

##Cleaning up you Environment
If you are done, and ready to clean up your environment we will need to remove all the items that we created in this exercise.  During this exercise, we created an **IoTAlertProcesses** solution to store all the customizations, workflows, and business process flows that we created.  This was done to not only make it easier to keep our changes together, but to also assist in the removal of these items upon completion of this module.  

When you remove an unmanaged solution from Dynamics 365 it will only remove the container that groups the customizations together.  Each customization would need to be manually removed from the system in a specific order.  Rather than having to manually removing each process, relationship, and customization is a specific order, it is much easier to remove all the items at once.  This can be done by using a managed solution.  When you remove a managed solution, it removes all the items included in the solution as well.    This is the process that we will be using.  

**To fully remove all the items in the system we must do the following: (High Level)**

- Export the **IoTAlertProcess** solution as an unmanaged solution. *(This will serve as a backup if you ever want it in the future, or if we have problems)*
- Export the IoTAlertProcess solution as a managed solution. *(This will be installed back into your environment)* 
- Delete the IoTAlertProcess unmanaged solution from your environment. *(This will remove the container to make importing the managed solution easier)*
- Import the IoTAlertProcess managed solution into your environment. *(This will convert all the customizations to managed components)*
- Delete the IoTAlertProcess managed solution from your environment. *(This will act as an uninstall and fully remove all of the changes we made from your environment)*   

**Detailed Steps:**

1. In Dynamics 365, navigate to **Settings > Solutions**.
1. Select the **IoTAlertProcess** solution.
1. Click the **Export** button and follow the steps to export it as an unmanaged solution.  *Save the solution somewhere where it will be easy to find.*
	- *Make sure all your customizations are published.*
	- *Ignore any dependency or missing components messages since we will just be importing it back into the same environment.*
	- *The file will export with a name of* ***IoTAlertProcesses_1_0_0_0.zip.***
1. After the export process is complete, click the **Export** button again and follow the steps to export the solution as a **Managed** solution.
	- *The file will export with a name of * ***IoTAlertProcesses_1_0_0_0_Managed.zip***
1. With the **IoTAlertProcesses** *(unmanaged)* solution still selected, click the **Delete** button to remove the unmanaged solution from your environment. 
	- ***Remember:*** *This will only remove the solution container; all customizations will remain.*
1. Click the **Import** button and follow the prompts to import the **IoTAlertProcesses_1_0_0_0_managed.zip** file into your environment. 
	- *Ignore any warning messages that appear.*
1. Ensure the **IoTAlertProcesses** *(managed)* solution is selected, click the **Delete** button. 

***All of the fields, form changes, workflows, and other customizations that we made are now fully removed from your environment.*** 

Optional: Remove Azure Resource Group

**IMPORTANT:** *You should only follow the steps below if you are completely done with you Connected Field Service environment and do not plan on taking any other modules or doing anything else with it.*  

When you deployed the Connected Field Service add-on it created an Azure Resource Group in your subscription that contains all the components of the template.  If you are going to complete other learning in the near future, you might want to wait to do the cleanup until you have completed any of the other modules that require a Connected Field Service deployment.

If you are done, and ready to cleanup all you need to do is simply delete the resource group in Azure.  You can accomplish that in two ways, either via the Azure Portal or from the Azure Cloud Shell.

**Via the Azure Portal**

1. Navigate to the Azure Portal [https://portal.azure.com](https://portal.azure.com")
1. On the left side choose Resource Groups
1. Type your resource group in the filter by name or find it on the list
1. Select the Resource Group to open the detail page
1. After confirming it is the right Resource Group, select all the items in the group and click Delete

**Via the Azure Shell**

1. Navigate to [https://shell.azure.com](https://shell.azure.com")
1. List your accounts using command az account list
1. Select your account using command: az account set -s “My Account Name”
1. Delete the resource group using command: az group delete -n “Your Resource Group Name”


