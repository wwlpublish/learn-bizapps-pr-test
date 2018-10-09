## Summary

In this module, you created an application by using Microsoft IoT Central and connected it to Microsoft Dynamics 365 for Field Service by using the Connected Field Service add-on. Microsoft IoT Central abstracts many of the more technical aspects of building an Internet of Things (IoT) solution. The process of building an IoT solution in the portal resembles the process of customizing Microsoft Dynamics 365. By using both together, you can quickly bring device telemetry and interaction into the Dynamics 365 solution. By using Microsoft IoT Central, you can release your solution more quickly.

On the near-term roadmap for the Connected Field Service add-on, expect to see more integration with Microsoft IoT Central.

### Cleaning up

The trial of Microsoft IoT Central that you created will just expire at the end of the trial period. No further action is required. If you want to re-create your trial from the beginning, you can delete the existing trial at any time. Currently, you can have only one active trial at a time in a Microsoft Azure subscription.

When you deployed the Connected Field Service add-on, it created an Azure resource group in your subscription. This resource group has all the components of the template. If you're going to do other learning soon, you might want to wait to do the cleanup until after you've finished any of the other modules that require a Connected Field Service deployment.

If you've finished and are ready to clean up, you just have to delete the resource group in Azure. You can do this via either the Azure portal or Azure Cloud Shell.

**Via the Azure portal**

1. Open the Azure portal ([https://portal.azure.com](https://portal.azure.com)).
2. In the left pane, select **Resource groups**.
3. Enter the name of your resource group in the filter, or find it in the list.
4. Select the resource group to open the details page.
5. After you've confirmed that it's the correct resource group, select all the items in the group, and then select **Delete**.

**Via Cloud Shell**

1. Go to [https://shell.azure.com](https://shell.azure.com).
2. List your accounts by running the following command.

    ```
    az account list
    ```

3. Select your account by running the following command.

    ```
    az account set -s "My Account Name"
    ```

4. Delete the resource group by running the following command.

    ```
    az group delete -n "Your Resource Group Name"
    ```
