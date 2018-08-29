In [powerapps.com](https://powerapps.com), you can use a sample app to explore design possibilities. You'll also discover concepts that you can apply as you develop your own apps. Each sample app uses fictitious data to showcase a real-world scenario. 

Be sure to check out documentation specific to each sample app for more details. 

![Fundraiser Sample App](../media/fundraiser-app1.png)


## Get sample apps

In order to play or edit model-driven sample apps, the apps must first be provisioned in a Common Data Service database. First create a trial environment and database and be sure to check **Include sample apps and data**.

![Create database](../media/create-database1.png)


> [!IMPORTANT]
> This option installs all available sample apps in your database. Sample apps are for educational and demonstration purposes and we do not recommend installing them in production databases. 

## Customize a sample app

1. Sign in to [powerapps.com](https://powerapps.com) and chose **Model-driven** for the design mode. 

    ![Choose design mode](../media/choose-design-mode.png)

2. From the home page, hover over the sample app and click **Customize**.
3. The App Designer will open providing multiple options for customizing the app. 
4. For additional customization options, click **Advanced** from the left pane.

## Remove sample apps and data 
Keep in mind the following when removing samples apps and data:
- Deleting a sample app requires deleting the corresponsing  [managed solution](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution). 
- Deleting the solution also deletes any sample data specific to the custom entities for the app.
- If customizations were made to the sample app, there may be [dependencies](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components), which must be removed before deleting the solution.

#
1. Login to the [PowerApps admin portal](https://admin.powerapps.com).

2. Select an environment.

3. Click **Dynamics 365 Administration Center** 

    ![Dynamics 365 Administration Center](../media/admin-center.png)

4. Select your Database from the list and select **OPEN**.

    ![Select database](../media/select-database.png)

5. Navigate to **Settings/Solutions**.

6. Select the solution for the app that is to be deleted and select **delete**.

    ![Delete solution](../media/delete-solution.png)

You can also navigate to the list of solutions by clicking **Advanced** in the maker portal and delete everything in the URL after .dynamics.com/*

> [!IMPORTANT]
> Do not delete other system solutions unless you're aware of the impact.

## Install or uninstall Sample Data
1. Login to the [PowerApps admin portal](https://admin.powerapps.com).
1. Select an environment.
1. Click **Dynamics 365 Administration Center** 

    ![Dynamics 365 Administration Center](../media/admin-center.png)

1. Select your Database from the list and select **OPEN**.
    ![Select database](../media/select-database.png)
1. Navigate to **Settings/Data Management/Sample Data**.
1. If sample data is installed, the option to remove is available. Otherwise the option to install is available. 

    ![remove sample data](../media/remove-sample-data.png)
