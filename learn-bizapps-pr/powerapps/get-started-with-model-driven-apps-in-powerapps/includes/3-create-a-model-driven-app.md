In this unit, you'll create a model-driven app by using one of the standard entities that's available in your Microsoft Power Apps environment.

## Create a model-driven app

1. Sign in to [Power Apps](https://web.powerapps.com/) by using your organizational account.
1. Select the environment you want, or go to the [Power Apps admin center](https://admin.powerapps.com/) to create a new one.
1. On the **Home** page, select the **Start from blank** option for a model-driven app.  

    ![Model-driven](../media/choose-design-mode.png)

    > [!IMPORTANT]
    > If the **Model-driven** design mode isn't available, you might need to [create an environment](https://docs.microsoft.com/powerapps/administrator/create-environment).

1. In the left pane, select **Apps**, then select **Create an app**.
1. On the **Create a New App** page, enter a name and description for the app.
1. Select **Done**. Your new app appears in the App Designer, and you can now add components to it.

## Add components to your app
You add components to your app by using the App Designer.

1. Select the **Open the Site Map Designer** arrow to open the site map designer.

    ![Create a new site map](../media/new-sitemap.png)

2. In the site map designer, select **New Subarea**, and then, in the right pane on the **Properties** tab, select the following properties:

    - **Type**: *Entity*
    - **Entity**: *Account*

    ![Add components to the site map](../media/sitemap.png)

3. Select **Save And Close**.
4. In the App Designer, select **Forms**, and then, in the right pane under **Main Forms**, select the **Account** form.

    ![Account main form](../media/main-form.png)

5. In the App Designer, select **Views**, then select the following properties:

    - Active Accounts
    - All Accounts
    - My Active Accounts

6. In the App Designer, select **Charts**, then select the **Accounts by Industry** chart.
7. On the App Designer toolbar, select **Save**.

<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](../media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## Publish your app
On the App Designer toolbar, select **Publish**.

After you publish the app, it's ready for you to run or share with others.

![Simple account entity app](../media/accounts-quickstart-app.png)
