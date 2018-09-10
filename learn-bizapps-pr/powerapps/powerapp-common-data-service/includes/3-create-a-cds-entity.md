In this unit you create an entity and then customize key components such as fields, relationships, views, and forms. You learn how to:

- Create a custom entity
- Add custom fields to your entity
- Add an entity relationship
- Customize a view 
- Customize a form

The tutorial will follow the company, Contoso, which is a pet grooming business that grooms dogs and cats. Contoso needs an app for client and pet tracking that can be used by employees across a variety of devices.

## Prerequisites

Sign in to [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). If you don’t already have a PowerApps account, select the **Get started free** link from [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## Create a custom entity

1. On the left navigation pane expand **Data**, click **Entities**, and then click **New entity**.
    > [!div class="mx-imgBorder"] 
    > ![New entity](../media/create-new-entity.png)
2. Enter the following values:
  - **Display name**: *Pet* 
  - **Description**: *Custom entity to track pet services*
3. Click **Next**, and then after the default fields are displayed click **Save Entity**.

## Add and customize fields
 
1. In the list of entities, select the **Pet** entity that was created in the previous section.
2. On the **Fields** tab, select the **Pet** field.
3. In the right pane make the following changes to the **Display name** field: 
  - Change the **Display name** from **Pet** to *Pet Name*
  -	Select **Searchable**  
  
    > [!div class="mx-imgBorder"] 
    > ![Change primary field](../media/primary-field.png)
3. Select **Done**.
4. On the **Fields** tab on the entity designer toolbar select **Add field**. On the **Field properties** pane, enter or select the following values and options.
  - **Display name**. *Species*
  - **Data type**. *Option Set*
  - **Option set**. *New option set*
5. Create the option set

  a. Select **Add new item**. 
  
  b. Replace **New option** with *Dog*. 
   
  c. Select **Add new item**. 
    
  d.  Replace **New option** with *Cat*. 
    
  e. Select **Save**. 

  > [!div class="mx-imgBorder"] 
  > ![New option set](../media/optionset-add-items.png)

6. Select **Searchable**, and then select **Done**.

7. On the entity designer toolbar select **Add field**. On the **Field properties** pane, enter or select the following values, and then select **Done**.
  - **Display name**. *Breed*
  - **Data type**. *Text*
  - **Searchable**. *Yes*

8. On the entity designer toolbar select **Add field**. 

9. On the **Field properties** pane, enter or select the following values, and then select **Done**. 
  -	**Display name**. *Appointment date*
  - **Data type**. *Date and time*

10. Select **Save Entity**.

## Add a relationship

1. Select the **Relationships** tab, on the entity designer toolbar select **Add relationship**, and then select **Many-to-one**. 
2. On the right pane, in the **Related** list select **Account**.
3. Select **Done**.
4. Select **Save Entity**.

  Notice that when you add a many-to-one relationship, an **Account** field with the data type **Lookup** is automatically added to your list of fields on the **Fields** tab.
  > [!div class="mx-imgBorder"]
  > ![Account lookup field](../media/account-lookup-field.png)

## Customize a view

1. Select the **Views** tab, and then select the **Active Pets** view. If you don't see the **Active Pets** view, select **Remove filter**.
2. On the view designer select **Add Columns**, select the following columns, and then select **OK**.
  - Account
  - Appointment date 
  - Breed 
  - Species
3. Select the **Created On** column, select **Remove**, and then select **OK** to confirm the column removal.
4. To arrange the columns, select the column you want to move and then use the <- and -> arrow buttons until your view looks like this.
    > [!div class="mx-imgBorder"] 
    > ![Active pets view](../media/active-pets-view.png)
5. On the view designer toolbar, select **Save and Close**.  

## Customize the main form

1. On the PowerApps left navigation pane, select **Model-driven**.
2. On the left navigation pane, expand **Data**, select **Entities**, and then select **Pet**.
3. Select the **Forms** tab, and then select **Information** next to the **Main** form type to open the form editor.
    > [!div class="mx-imgBorder"] 
    > ![Edit main form](../media/main-form-edit.png)
4. On the form editor, drag and drop the **Species**, **Breed**, **Appointment date**, and **Account** fields located on the Field Explorer pane on to the General section of the form canvas until the form looks like this.
    > [!div class="mx-imgBorder"] 
    > ![Select fields for main form](../media/main-form-edit2.png) 
5. Select **Save**.
6. Select **Publish**.
7. Select **Save and close** to close the form designer.