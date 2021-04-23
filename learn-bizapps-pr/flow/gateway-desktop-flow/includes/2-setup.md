Creating and running automation systems in Power Automate requires you to have access to make a few changes to the environments in your tenant, and ensure you have the appropriate licenses and permissions. If you do not already have admin access to a valid tenant, you may want to take a few minutes and start a [free trial](https://www.microsoft.com/en-us/microsoft-365/enterprise/office-365-e3?activetab=pivot%3aoverviewtab/?azure-portal=true). In addition, you will need a Power Automate user plan with attended RPA license to complete this module. You can sign up for a [free trial](https://flow.microsoft.com/pricing/?azure-portal=true) if you don't already have this license.

If you completed the module Build your first Power Automate Desktop Flow, feel free to skip to the next unit.

## Create a trial environment with database

Once you are logged in to a valid tenant, navigate to the [admin center](https://admin.powerplatform.microsoft.com/environments/?azure-portal=true). We will need to create a trial environment with a database. Select **Environments** and choose your automatically created environment, the **default**.

If you are using an existing tenant rather than creating a trial for this exercise, you can use the default environment or create a new one to keep it separate from your existing solutions.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Environments list.](../media/environments.png)](../media/environments.png#lightbox)

Now that you are in your chosen environment, add a database by selecting **Add database**. In the subsequent dialogue box, feel free to specify the requested values, but you can keep the defaults and press **Add**. You may be prompted to sign in again before creating your database. Upon doing so, your database should provision appropriately.

> [!div class="mx-imgBorder"]
> [![Screenshot of the add database button.](../media/database.png)](../media/database.png#lightbox)

Creating your database may take up to one minute, but afterward you are good to continue to the next steps!

If you are using a trial environment, consider setting up a profile in your browser to prevent you from being signed out of your existing Microsoft Account.

## Software installation

The following exercises will require various software to be installed on your computer. The following steps will guide you through the download and installation of Power Automate Desktop, required extensions, and the Contoso Invoice App.

If you have already installed Power Automate Desktop, ensure you are running the latest available version.

### Power Automate Desktop

Navigate to [Power Automate](https://flow.microsoft.com/?azure-portal=true) and sign in with the account you used to create your environment and database. Once there, select **My Flows**, **Install**, and **Power Automate Desktop**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the install Power Automate Desktop feature.](../media/install-desktop.png)](../media/install-desktop.png#lightbox)

Once the download completes, select the file to open and run the installer. Choose **Next** and on the subsequent screen, check the final box and select **Install**. This will install the Power Automate Desktop and the browser extensions for Microsoft Edge and Google Chrome.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate Desktop setup page.](../media/installer-1.png)](../media/installer-1.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of the installation details and install button.](../media/installer-2.png)](../media/installer-2.png#lightbox)

Once installation is complete, select the link of your preferred browser and follow the instructions to enable the extension. Once the extension is enabled, you can launch the Power Automate Desktop App.

> [!div class="mx-imgBorder"]
> [![Screenshot of the successful installation message with launch button.](../media/installer-3.png)](../media/installer-3.png#lightbox)

After launching the app, sign in using the account, which you used to set up your environment and database.

## Contoso invoice app

One of the major benefits of using desktop flows is the ability to perform actions on desktop applications. For the flow you will create, you will use an invoicing application to explore the concepts and actions available to you in desktop flows. After completing the module, you can use what you have learned to run desktop flows on your own applications and automate existing processes.

To download the Contoso Invoice App, visit here and select download. After downloading, open the application and familiarize yourself with all the elements.

If you don't have a desktop app created to connect to a cloud flow, do so now by following this module or on your own.