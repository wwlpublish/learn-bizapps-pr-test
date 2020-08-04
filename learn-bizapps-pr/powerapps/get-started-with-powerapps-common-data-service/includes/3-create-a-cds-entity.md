In this unit, you'll create an entity and then customize key components, like fields, relationships, views, and forms. You'll learn how to:

- Create a custom entity.
- Add custom fields to your entity.
- Add an entity relationship.
- Customize a view.
- Customize a form.

The tutorial follows the Contoso company, which is a pet grooming business that grooms dogs and cats. Contoso needs an app for client and pet tracking that can be used by employees on a variety of devices.

## Create a custom entity

Sign in to [Power Apps](https://make.powerapps.com) and follow these steps to create a new custom entity.

1. In the left navigation pane, expand **Data**, select **Entities**, and then select **+ New entity**.

2. Under New Entity, enter the following:

    - **Display name**: *Pet*

3. In the Primary Field section, enter the following:

    - **Display name**: *Pet Name*

4. At the bottom, click **Create**.

You will notice in our example, the new entity and primary field begins with **cree0_**. Additional fields created for this entity will also begin with **cree0**, this is specific to our demo environment. When testing in your own environment this may look different.

## Add and customize fields

1. In the list of entities, select the **Pet** entity that you created in the previous section.
2. On the **Fields** tab, on the entity designer toolbar, select **Add field**.
3. In the **Field properties** pane, enter the following values:

    - **Display name**: *Species*
    - **Data type**: *Option Set*
    - **Option set**: *New option set*
    - **Searchable**: *Yes*

4. Create the option set:

    1. Replace *New option* with *Dog*.
    2. Select **Add new item**.
    3. Replace *New option* with *Cat*.
    4. Select **Save**.

    > [!div class="mx-imgBorder"]
    > ![New option set](../media/updated-optionset-add-items.png)

5. Make sure **Searchable** is selected, and then select **Done**.
6. On the entity designer toolbar, select **Add field**.
7. In the **Field properties** pane, enter the following values, and then select **Done**:

    - **Display name**: *Breed*
    - **Data type**: *Text*
    - **Searchable**: *Yes*

8. On the entity designer toolbar, select **Add field**.
9. In the **Field properties** pane, enter the following values, and then select **Done**:

    - **Display name**: *Appointment date*
    - **Data type**: *Date Only*
    - **Searchable**: *Yes*

10. Select **Save Entity**.

## Add a relationship

1. On the **Relationships** tab, on the entity designer toolbar, select **Add relationship**, and then select **Many-to-one**.
2. In the right pane, in the **Related** list, select **Account**.
3. Select **Done**.
4. Select **Save Entity**.

    Notice that when you add a many-to-one relationship, an **Account** field of the **Lookup** data type is automatically added to your list of fields on the **Fields** tab.

    > [!div class="mx-imgBorder"]
    > ![Account lookup field](../media/updated-account-lookup-field.png)

## Customize a view

1. On the **Views** tab, right-click **Active Pets** view and select **Open Link in New Tab**. If you don't see the **Active Pets** view, select **Remove filter**.
2. In the view designer, select **Add Columns**, select the following columns, and then select **OK**:

    - Account
    - Appointment date
    - Breed
    - Species

3. Select the **Created On** column, select **Remove**.
4. To arrange the columns, select the column to move, and then select **Move Left** or **Move Right** until your view looks like this. You could also simply drag and drop the columns to arrange the order as well.

    > [!div class="mx-imgBorder"]
    > ![Active pets view](../media/updated-active-pets-view.png)

5. On the view designer toolbar, select **Save**.
6. Select **Publish**.

## Customize the main form

1. In the left navigation pane, expand **Data**, select **Entities**, and then select **Pet**.
1. On the **Forms** tab, select **Information** next to the **Main** form type to open the form editor.

    > [!div class="mx-imgBorder"]
    > ![Edit main form](../media/updated-main-form-edit.png)

4. In the form editor, drag the **Species**, **Breed**, **Appointment date**, and **Account** fields from the **Field Explorer** pane to the **General** section of the form canvas, so that the form looks like this.

    > [!div class="mx-imgBorder"]
    > ![Select fields for main form](../media/updated-main-form-edit2.png)

5. Select **Save**.
6. Select **Publish**.
7. Click the back arrow in your browser to close the form designer.
