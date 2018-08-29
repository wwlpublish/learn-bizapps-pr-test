In this unit, you'll create a model-driven app by using one of the standard entities that's available in your PowerApps environment.

## Create your model-driven app

1.	Sign in to [PowerApps](https://web.powerapps.com/) using your organizational account.

1. Select the environment you want, or go to the [PowerApps admin center](https://admin.powerapps.com/) to create a new one.
1.	From the left pane, select **Model-driven** on the bottom. 

    ![Model-driven](../media/choose-design-mode.png)

  > [!IMPORTANT]
  > If the **Model-driven** design mode isn't available, you may need to [Create an environment](https://docs.microsoft.com/powerapps/administrator/create-environment).

1. From the left pane, select **Apps**, and then select **Create an app**.

1. On the **Create a New App** page, enter a name and description for the app.
1. Select **Done**. Your new app will appear in the App Designer where you can add components.

 ## Add components to your app
You add components to your app using the App Designer.
1.	Select the **Open the Site Map Designer** arrow to open the sitemap designer. 

    ![Create-new-sitemap](../media/new-sitemap.png)

2.	On the sitemap designer select **New Subarea**, in the right pane select the **Properties** tab, and then select the following properties.
  - **Type**: Entity
  - **Entity**: Account

    ![Add components to sitemap](../media/sitemap.png)

3.	Select **Save And Close**.
4.	On the App Designer select **Forms**, and then on the right pane under the **Main Forms** group select the **Account** form.

    ![Account main form](../media/main-form.png)

5.	On the App Designer select **Views**, and then select the following properties:
**Active Accounts**
**All Accounts**
**My Active Accounts**.

6. On the App Designer select **Charts**, and then select the **Accounts by Industry** chart.
7. On the App Designer toolbar, select **Save**.

<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](../media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## Publish your app
On the App Designer toolbar, select **Publish**.

After publishing the app it's ready for you to run or share with others.

![Simple account entity app](../media/accounts-quickstart-app.png)