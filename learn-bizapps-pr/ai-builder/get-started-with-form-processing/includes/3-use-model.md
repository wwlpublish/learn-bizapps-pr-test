Learn how to use your Form processing model in Power Apps and Power Automate.

**Quick test**

After your model has completed training, you can view important details about your newly trained model on a details page.

![Trained model details page](../media/image4.png)

To see your model in action, select **Quick test**.

Drag and drop or upload an image from your device to test. If you are using sample data, go to the **AI Builder Form processing Sample Data\\Invoices Version 2\\Train** folder for a test image.

You will now be able to view the detected fields that you chose and the associated confidence scores for retrieving the individual fields compared to the trained model.

**Publish your model**

Your model can\'t be used until you publish it. If you are satisfied with your model, select **Publish** to make it available for use.

**Use your model in Power Automate**

After your Form processing model is published, you can also use it in a flow. You can use the **AI Builder** action in Power Automate to take advantage of the results of your model.\
\
![screenshot](../media/image5.png)

1.  Select **Use model**.

2.  Select **Create new flow** to begin the flow creation experience.

3.  Make sure that you are signed in to the flow and then select **Continue** to confirm the creation of the flow.

> ![screenshot](../media/image6.png)

The flow has already been configured with a manual trigger that will prompt for a document and to specify the document type after you have run the flow and the AI Builder action with the model.

4.  Add an action to send an email with what is extracted by your model. To complete this step, select **+ New step**. A choose action card will appear, when you can search for the email and then select the **Send an email notification**.

> ![screenshot](../media/image7.png)

5.  In the **To** field, enter the email address that you want to send the email to, and then set the **Subject** field as well. In the email body, include one of the fields that was detected by the model. Those fields are visible in the flyout panel on the right. To retrieve a field, look for its name followed by value. If you used the sample data, you can select the total amount field by searching for **Total value** (for example).

> ![screenshot](../media/image8.png)

6.  Select **Save** to test the flow.

7.  Select **Test**.

8.  Select **I\'ll perform the trigger action** and then select **Save Test**.

9.  Under **Document**, import the image that you used to quick test previously. Under **Document Type**, select the corresponding file type. If you are using the sample data, select **image/jpeg**.

10. Select **Run flow**.

11. After the flow run has started, select **Done**.

After the flow runs successfully, an email will be sent to the email that you set with the content that you defined.

**Use your model in Power Apps**

Now that your model is published, you can use your Form processing model in a canvas app. A special component is available for you to add that analyzes any image and extracts the text based on your trained Form processing model.

![screenshot](../media/image9.png)

1.  Select **Use model**.

2.  Select **Create new app** to begin the canvas app creation experience.

3.  Within your canvas app, a Form processor component is automatically added and linked to your published Form processing model.

> Going forward, you can select **Insert \> AI Builder** to view the list of AI Builder components and then select **Form processor** to add a Form processor component. Make sure that you select the correct model. Only published models will appear in the drop-down list.

4.  Select **Insert** and then add a **Label** component.

5.  To bind the **Label** component to one of the form fields, select the **Fields** property on the formula bar. This selection retrieves the details of the extracted form fields.

6.  To choose a field to display, select one of the names from the **Fields** property. If you want to select table content, select one of the names from the **Tables** property.

> ![screenshot](../media/image10.png)

7.  Select **Play** on the upper right of the Power Apps studio to preview the app.

8.  Select **Analyze** and then select the image that you used to quick test previously.

> A preview of your document shows the detected fields and the values that were detected for the fields that you chose.
