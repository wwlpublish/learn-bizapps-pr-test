Your goal for this exercise is to accelerate the process of creating an appointment by using information from business cards. Users will extract contact information from a business card and prefill the **Quick Create: Appointment** form with the contact information. 

You will build a model-driven Power App and use the Business card reader component for this exercise. For more information, see the [What are model-driven apps in Power Apps?](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview) and the [Use the business card reader in model-driven apps](https://docs.microsoft.com/ai-builder/business-card-reader-component-model-driven) documentation.

## Create a model-driven app in Power Apps
To create a model-driven app in Power Apps, follow these steps:

1. Select **Create** in the Power Apps left menu. 
2. Select **Canvas model-driven from blank**.
3. Name the canvas app **Contoso Business card reader**.
4. In the App Designer, edit the **Site map** and then edit the sub group. 
5. Select a Common Data Service entity related to the form that you will create that will use the Business card reader component. For this lesson, use the **Appointment** entity. 
6. Select **Save and close**.

    ![App designer UI](../media/image9.png)

Update the appointment's **Quick Create** form so it can use the Business card reader component. 
1. Select **Forms**. 
2. Edit the **Quick Create: Appointment** form.

## Update an existing form 
You have entered the edition mode of the form. You can now create a new field that will host the Business card component.

1. Select **+ Add field**. 
2. Name the field **Business Card** and drag it to your form to add it.
3. Add the AI Builder Business card by selecting **+ Add component**. 
4. Select the **AI Builder Business card** control. Set the following properties:

   - Business Card Reader field: Business Card (Text)
   - Full Name Field: Subject (Text)
   - Address Street Field: Location (Text)

After the component has been added, you should see a page similar to the following image.

![A screenshot of a computer description automatically generated](../media/image10.png)

Save and publish your updated form.

## Publish your model-driven app 

Publish your app and create an appointment by using the Business card reader. You can now use the **Quick Create: Appointment** form.

1. Return to the App Designer. Publish your application and select the **run** button. 
2. Test your updated form with the Business card component by selecting the plus sign (**+**), and then in **Activities**, and then in **Appointment**. 
3. You can scan a business card and the extracted contact fields will appear in the form. Fill out the remaining fields and save your appointment by selecting **Save and Close**.

    ![App designer UI](../media/image11.png)
