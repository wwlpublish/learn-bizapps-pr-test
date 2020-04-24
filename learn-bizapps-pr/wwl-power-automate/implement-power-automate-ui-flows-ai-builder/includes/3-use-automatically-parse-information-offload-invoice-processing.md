AI Builder is a Power Platform capability that enables you to add intelligence to your automated processes, predict outcomes, and help improve business performance.  There is great value in being able to intelligently extract specific information from a form so that it is available to use as part of a business process automation.


Watch this video to learn how to create a forms processing model, with AI Builder, that can identify and parse key value pairs from your invoice.

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4uGU2]


To recap, here are the steps to create the forms processing model for the sample invoices.  The sample files can be downloaded by going to [download sample invoices](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/tree/master/implement-robotic-process-automation-power-automate-ui-flows-ai-builder?azure-portal=true).


>[!NOTE]
> Some features in AI Builder have not yet released for general availability (GA), and remain in preview status.  In addition, AI Builder requires the use of Common Data Service, which is the data platform for Power Apps and allows you to store and manage business data.  Refer to the Summary and Resources section of this module for links to additional information.


1. In your demo tenant navigate to **Power Automate**.  Make sure you are in the same environment in which you created the flow.

1. In the left navigation click **AI Builder**, then click **Build**.

1. On the **Enhance your business with AI** page, under **Refine a model for your business needs** click **Form Processing (preview)**.

1. In the Form Processing (preview) dialog, on the Get started tab, under Name this AI model click the field and type **Contoso Invoice Processing** (or any meaningful name you choose), then click **Create**.

1. On the Add document examples page, click **Add documents**.

1. Under Select a data source, select the option that applies, based on where you stored the invoices; for example, if you saved the files on your local machine, select **Upload from local storage,** then navigate to the location where you saved the file and select the following documents:

   1. **Contoso INVOICE (Fabrikam_UK).pdf**

   1. **Contoso INVOICE (Litware_CAN).pdf**

   1. **Contoso INVOICE (Proseware_NY).pdf**

   1. **Contoso INVOICE (TailSpin).pdf**

   1. **Contoso INVOICE (Wing Tip).pdf**

1. Click **Open**.

1. Click **Upload 5 documents**.

1. Click **Close**.

1. On the Add document examples page, at bottom left, click **Analyze**.

1. Below **Select the form fields you want to save** page, click the tile displaying the invoice.

1. Click the data highlighted with blue dashed lines.  As you click on each item, a pop-up box opens.  Select the check mark below the data value (it will get added the Selected fields pane on the right side of the screen).

   1. Select the **Due Date value** highlighted with the blue dashed line, then select the **check mark**.

   1. Select the **Bill to value** highlighted with the blue dashed line, then select the **check mark**.

   1. Select the **Balance due value** highlighted with the blue dashed line, then select the **check mark**.

   1. Select the **Contact value** highlighted with the blue dashed line, then select the **check mark**.

    ![Field selection for AI Builder forms processing model](../media/ai-builder-select-field-3.png)

   *Field selection for AI Builder forms processing model*

1. At top right, click **Done.**

1. Click **Next**.

1. Click **Train**.  It may take a few minutes for training to complete.

1. Click **Go to Details page**.

1. On the Models > Contoso Invoice Processing page, in the Training document tile, click **Publish** or you may choose to do a **Quick test**, prior to publishing, as follows:

   1. Select **Upload from my device**.

   1. Upload one of the pdf invoice files and select **Open**.

   1. One the quick test is done, you will see a pop-up box that shows the invoice with the fields that were selected as part of the modeling, highlighted.  Select **Close**.

   1. Select **Publish**.

With the predict model published, you can now incorporate it into your flow, to automate the invoice approval process.