## Summary and cleanup

In this module, you connected a real device to your deployment. You changed the template application to send alerts to the Microsoft Dynamics 365 Connected Field Service add-on. You also used the advanced anomaly detection capabilities of Microsoft Azure Stream Analytics to implement more complex, dynamic rules. And finally, you saw several of the extension points where you can not only store detail telemetry but also hook in your own custom processing of the device data stream.

### Cleaning up

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
