The following procedures will show you how to create a Form processing model in AI Builder.

## Sign in to AI Builder

Follow these steps to sign in to AI Builder:

1.  Go to Power Apps or Power Automate and sign in with your
    organizational account.
2.  In the left pane, select **AI Builder > Build**.
3.  Select **Form processing**.
4.  Enter a name for your model.
5.  If you want to create your model by using your own documents, make
    sure that you have at least five examples that use the same layout.
    Otherwise, you can use sample data to create the model.
6.  Select **Create**.

## Add documents

This guided experience will walk through each step of the model
creation process. You can save your work and return at any time.
Progress will be saved automatically when you go between steps.

If you want to use sample data, select **Get sample documents**.
Download the **AI Builder Form processing Sample Data.zip** file and extract it inside a folder
on your computer. The documents that are used in this exercise are
located in the **AI Builder Form processing Sample Data\Invoices Version 2\Train** folder.

![Sample data documents](../media/image2.png)

1.  Select **Add documents**.
2.  Select five to ten examples of your document. Only JPG, PNG, and PDF files are accepted.
3.  Verify that you have selected the correct files and then select **Upload documents**.
4.  After the upload has completed, select **Close**.
5.  Select **Analyze**.

## Select form fields

By using the sample documents that you have uploaded, your model will
begin to analyze the document layout to detect all the various form
fields. This process might take a few minutes to complete.

![Select form fields](../media/image3.png)

When the analysis has finished, select the thumbnail to open the field selection experience.

1.  Review the document and select all fields that you want to save. Alternatively, select the **Select all** button if you want to save all fields. You can also rename the field names.
2.  If one of the fields that you want to save has not been automatically detected, you can draw a rectangle around the field that you are interested in, give it a name, and validate the selection. If you used the sample invoices, notice that the address on the top left has not been detected.  

    ![Select form fields](../media/form-processing-undetected-fields.gif)

3.  If a field that you want to save has been automatically selected but does not contain all values for that field, you can adjust the selection by selecting the field, resizing the selection, and then validating the selection. In the sample invoices, notice that this situation has occurred for the **Bill to** field.  

    ![Select form fields](../media/form-processing-resize-selection.gif)

4.  When you are finished, select **Confirm Fields**. If you have only selected an automatically detected field, you will see the **Done** button instead of **Confirm Fields**. In that case, you can go to the Summary and train section of this unit.

### Confirm fields

When drawing new fields or resizing automatically detected fields, you are presented with all documents that you have uploaded. In this step, you will need to draw the fields that are indicated as pending on the right panel. By completing this step, you are teaching your AI Builder model to recognize these fields in documents of this type.

To draw a field on a document, start drawing a selection on the document and you will be asked which field it corresponds to. You can also select the **Draw in document** option on the fields list on the right to star the selection process for that field.

If a field is not present on one of the documents, select the **Field not in document** option.

![Select form fields](../media/form-processing-confirm-fields.gif)

## Summary and train

After you have selected your fields, follow these steps:

1.  Select **Next**.
2.  Review the summary of your model's details. If everything looks acceptable, select **Train**.

## Next steps

Now that you've created a Form processing model in AI Builder, you'll
learn how to test your model and use it in Power Apps and Power
Automate.
