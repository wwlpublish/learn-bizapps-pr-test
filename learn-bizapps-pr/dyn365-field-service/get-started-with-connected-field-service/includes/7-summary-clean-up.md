In this module, you deployed the Connected Field Service add-on. You also registered a simulated device and saw firsthand how alerts are raised in Microsoft Dynamics 365 for further evaluation.

The next steps are to consider how you want to handle the Internet of Things (IoT) Alerts and customize the business process for your specific scenario. Depending on your scenario, you might also need to customize some of the out-of-box components to handle the actual telemetry that your devices will generate.

### Cleaning up

When you deployed the Connected Field Service add-on, it created a Microsoft Azure resource group in your subscription. This resource group has all the components of the template. If you're going to complete other learning soon, you might want to wait to do the cleanup until after you've finished any of the other modules that require a Connected Field Service deployment.

If you've finished and are ready to clean up, you just have to delete the resource group in Azure. You can do this via either the Azure portal or Azure Cloud Shell.

**Via the Azure portal**

1. Open the Azure portal ([https://portal.azure.com](https://portal.azure.com "Azure Portal")).
2. In the left pane, select **Resource groups**.
3. Enter the name of your resource group in the filter, or find it in the list.
4. Select the resource group to open the details page.
5. After you've confirmed that it's the correct resource group, select all the items in the group, and then select **Delete**.

**Via Cloud Shell**

1. Go to [https://shell.azure.com](https://shell.azure.com "Azure Shell").
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
