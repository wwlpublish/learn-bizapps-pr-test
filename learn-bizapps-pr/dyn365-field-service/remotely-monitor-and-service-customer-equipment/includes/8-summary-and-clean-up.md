## Summary

In this module you remotely managed IoT devices using the Dynamics 365 Connected Field Service solution. A number of actions are involved in monitoring and servicing remote devices. We explored some of these, including:

- Examine the relationship between customer assets and IoT devices.  
- Interact with devices using commands.
- Leverage some of the out-of-the-box actions to assist in automation. 
- Build business process flows that can be leveraged by Connected Field Service.  


<!--note from editor: Are the next steps mentioned in the following paragraph things that students are supposed to do on their own after the course?-->

The next steps are to gain a deeper understanding of interacting with devices. This includes understanding how device twins can be used to report and query information. You should also explore some of the additional features available for interacting with devices using commands. This includes items like device categories as well as command and property definitions.  

## Cleaning Up Your Environment

If you are done and ready to clean up your environment, you will need to remove all the items that you created in this exercise. During this exercise, you created an **IoTAlertProcesses** solution to store all the customizations, workflows, and business process flows that you created. This was done not only to make it easier to keep your changes together, but to also assist in the removal of these items upon completion of this module.  

When you remove an unmanaged solution from Dynamics 365, it only removes the container that groups the customizations together. Each customization needs to be manually removed from the system in a specific order. Rather than having to manually remove each process, relationship, and customization in a specific order, it is easier to remove all the items at once. This can be done by using a managed solution. When you remove a managed solution, it removes all the items included in the solution as well. This is the process that you will use here.  

**To fully remove all the items in the system, you must do the following (high level):**

- Export the **IoTAlertProcess** solution as an unmanaged solution. *(This will serve as a backup if you ever want it in the future, or if you have problems.)*
- Export the IoTAlertProcess solution as a managed solution. *(This will be installed back into your environment.)* 
- Delete the IoTAlertProcess unmanaged solution from your environment. *(This will remove the container to make importing the managed solution easier.)*
- Import the IoTAlertProcess managed solution into your environment. *(This will convert all the customizations to managed components.)*
- Delete the IoTAlertProcess managed solution from your environment. *(This will act as an uninstall and fully remove all of the changes we made from your environment.)*   

**Detailed Steps:**

1. In Dynamics 365, navigate to **Settings** > **Solutions**.
1. Select the **IoTAlertProcess** solution.
1. Select the **Export** button and follow the steps to export it as an unmanaged solution. Save the solution somewhere where it will be easy to find.
	- *Make sure all your customizations are published.*
	- *Ignore any dependency or missing components messages because you will just be importing it back into the same environment.*
	- *The file will export with a name of* ***IoTAlertProcesses_1_0_0_0.zip.***
1. After the export process is complete, select the **Export** button again and follow the steps to export the solution as a **Managed** solution.
	- *The file will export with a name of* ***IoTAlertProcesses_1_0_0_0_Managed.zip***
1. With the **IoTAlertProcesses** *(unmanaged)* solution still selected, click the **Delete** button to remove the unmanaged solution from your environment. 
	- ***Remember:*** *This will only remove the solution container; all customizations will remain.*
1. Select the **Import** button and follow the prompts to import the **IoTAlertProcesses_1_0_0_0_managed.zip** file into your environment. 
	- *Ignore any warning messages that appear.*
1. Ensure the **IoTAlertProcesses** *(managed)* solution is selected, and then click **Delete**. 

***All of the fields, form changes, workflows, and other customizations that you made are now fully removed from your environment.*** 

Optional: Remove Azure Resource Group

**IMPORTANT:** *Follow the steps below only if you are completely done with your Connected Field Service environment and do not plan to take any other modules or do anything else with it.*  

When you deployed the Connected Field Service add-on, it created an Azure Resource Group in your subscription that contains all the components of the template. If you are going to undertake other learning in the near future, you might want to wait on the cleanup until you have completed any other modules that require a Connected Field Service deployment.

If you are done and ready to clean up, all you need to do is delete the resource group in Azure. You can accomplish that either from the Azure portal or the Azure Cloud Shell.

**Via the Azure portal**

1. Navigate to the Azure portal ([https://portal.azure.com](https://portal.azure.com")).
1. On the left side of the portal, choose **Resource Groups**.
1. Enter your resource group in the filter by name or find it on the list.
1. Select the resource group to open the detail page.
1. After confirming it is the right resource group, select all items in the group and then select **Delete**.

**Via the Cloud Shell**

1. Navigate to the Cloud Shell ([https://shell.azure.com](https://shell.azure.com")).
1. List your accounts using command: az account list
1. Select your account using command: az account set -s “My Account Name”
1. Delete the resource group using command: az group delete -n “Your Resource Group Name”


