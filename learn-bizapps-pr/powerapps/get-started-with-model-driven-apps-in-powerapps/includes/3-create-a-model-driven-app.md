## Create a model-driven app

In this unit, you'll create a model-driven app by using one of the standard entities that's available in your Microsoft Power Apps environment.

1. Sign in to [Power Apps](https://make.powerapps.com/) by using your organizational account.
2. Select the environment you want, or go to the [Power Apps admin center](https://admin.powerplatform.microsoft.com) to create a new one.
3. On the **Home** page, select the **Model-driven app from blank**.  
4. Click **Create**.

    ![Screenshot of the Model-driven app from blank feature.](../media/updated-choose-design-mode.png)

5. On the **Create a New App** page, enter a name and description for the app.
6. Select **Done**. Your new app appears in the App Designer, and you can now add components to it.

## Add components to your app
You add components to your app by using the App Designer.

1. Select the **Open the Site Map Designer** pencil icon to open the site map designer.

    ![Screenshot of the Site Map Designer view.](../media/updated-new-sitemap.png)

2. In the site map designer, select **New Subarea**, and then, in the right pane on the **Properties** tab, select the following properties:

    - **Type**: *Entity*
    - **Entity**: *Account*

    > [!NOTE]
    > If *Account* is not an option as an entity, you may not have any sample data in your environment. Refer to this exercise on [how to create sample apps and data](/learn/modules/intro-model-driven-apps-common-data-service/4-template-apps/?azure-portal=true).

    ![Screenshot of the Properties tab with type and entity set.](../media/updated-sitemap.png)

3. Select **Save And Close**.
4. In the App Designer, select **Forms**, and then, in the right pane under **Main Forms**, select the **Account** form.

    ![Screenshot of the Main Forms with Account form selected.](../media/updated-main-form.png)

5. In the App Designer, select **Views**, then select the following properties:

    - Active Accounts
    - All Accounts
    - My Active Accounts

6. In the App Designer, select **Charts**, then select the **Accounts by Industry** chart.
7. On the App Designer toolbar, select **Save**.

## Publish your app
On the App Designer toolbar, select **Publish**. After you publish the app, it's ready 
for you to run or share with others.

Above My Active Accounts, select **Show Chart**.

If the sample data for your accounts does not have an Industry populated, go into a few accounts and add an Industry. Once you have updated a few accounts with an industry the chart will update as well.  

![Screenshot of updated chart with industry populated.](../media/updated-accounts-quickstart-app.png)
