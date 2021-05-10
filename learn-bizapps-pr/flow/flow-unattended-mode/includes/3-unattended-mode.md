A cloud flow runs in the cloud and accesses services via API. Cloud flows are required to trigger the unattended desktop flow. To begin creating your cloud flow, open [Power Automate](https://us.flow.microsoft.com/?azure-portal=true) and select **My flows** and then **Cloud flows**.

> [!div class="mx-imgBorder"]
> [![Screenshot of cloud flows in the flow window.](../media/cloud-flows.png)](../media/cloud-flows.png#lightbox)

Next select **New flow** and then **Instant cloud flow**.

> [!div class="mx-imgBorder"]
> [![Screenshot of new flow menu with instant cloud flow selected.](../media/instant-cloud-flow.png)](../media/instant-cloud-flow.png#lightbox)

Name your flow. Here we have used the name Manual trigger Desktop flow to enter invoice. Choose **Manually trigger a flow**, then select **Create**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow name field and manually trigger a flow selected.](../media/name-flow.png)](../media/name-flow.png#lightbox)

Once the screen changes to the flow builder, select **New step** and then search for and select **Run a flow built with Power Automate Desktop**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Run a flow built with Power Automate Desktop action selected.](../media/run-desktop-flow-action.png)](../media/run-desktop-flow-action.png#lightbox)

If you have not already configured your gateway connection, use the dropdown under Gateway name to select the appropriate gateway.

If you don't see your gateway, you may need to delete this step and recreate it in order to refresh the list. If your gateway still does not appear, you may need to restart the gateway on your PC and retry.

The next two fields request your credentials to log into your computer. If you are unsure what to put in the Domain and username field, you can open a Command Prompt window by opening Start, typing CMD and pressing enter. Once the command prompt opens, type **Set user** and press Enter.

Several lines of code will appear. Take the user domain and the username and separate them by a backward slash as seen below. Select **Create**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the name, domain, user name, and password details.](../media/user-domain-user-name.png)](../media/user-domain-user-name.png#lightbox)

Once you have connected to your desktop, Power Automate will prompt you for information specific to your desktop flow. Use the dropdown to select the name of your desired flow, in this case Invoicing, and choose **Unattended - Runs in the background without signing in** for your Run Mode.

Once you have selected your desktop flow, any requested input variables will be added for you to fill in. You can use dynamic content from the trigger or other steps in your cloud flow to populate these variables. Here, we will just put placeholders since we are only testing the unattended flow. Select **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the unattended flow placeholder information.](../media/unattended-flow-placeholders.png)](../media/unattended-flow-placeholders.png#lightbox)

That's it! You have created the unattended desktop flow. Now, let's test it!
