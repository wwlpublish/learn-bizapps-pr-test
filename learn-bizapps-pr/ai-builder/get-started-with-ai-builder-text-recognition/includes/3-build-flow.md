In this unit, you will:

-   Develop a simple flow with Power Automate that uses AI Builder Text Recognition.

-   Practice automatically processing files from a OneDrive folder and saving recognized text to Common Data Service.

In this unit, you will build a Power Automate flow, check when an image is added to a folder, and trigger AI Builder Text Recognition. Then, you will save recognized text in Common Data Service. This process can be useful to automate digitalization of paper forms. For more information, see "Create a flow in Power Automate".

**Create a Common Data Service entity to store the recognized text**

1. Go to <https://make.powerapps.com>. 
2. Open the **Data** menu, and then the **Entities** submenu.
3. Select the **+New Entity** button, which opens a side panel where you can enter information about the entity. For this example, use **Text Recognizer Results** as the display name.
4. When you are finished, select **Create**. A **Name** field is automatically created, which you use to store the recognized text.

The following figure shows an example of the entity structure.

![Example of the entity structure](../media/image2.png)

You can now create a flow in Power Automate that manages the triggering of AI Builder Text Recognition when an image is added to your OneDrive for Business. You can save the result in the entity that you have created.

1. Go to https://flow.microsoft.com/. 
2. Open the **Create** menu. 
3. In the **Start from blank** section, select **Automated flow**. 
4. Enter **Contoso Text Recognition** as the name. 
5. Enter **When a file is created-- OneDrive for Business** as the trigger. 
6. When you are finished, select **Create**.

[!NOTE:] You can use any kind of trigger, such as: **When an email arrives in Outlook**, **When a record is created in Common Data Service**, **When an item is created in SharePoint**, and more.

**Set the folder that Power Automate will monitor for new incoming images**

In this example, you will set the **Folder** property of the "When a file is created" step to the **Images** folder.

**Call AI Builder Text Recognition**

1. Select **New step**. 
2. Select **Predict -- Common Data Service (current environment)**. 
3. Select **TextRecognition model** in the **Model** drop-down menu. 
4. Select **File Content** in the **Image file** drop-down menu.

![Image File drop-down menu](../media/image3.png)

**Save the result in the entity that you previously created by first iterating on text that was extracted by the AI
Builder Text Recognition.**

1. Select **New step**.
2. Select **Apply to each**. 
3. In the **Select an output from previous steps** field, select **Response results**, which will iterate over the various texts that are detected in the image.

![Select Response Results](../media/image4.png)

**Save the results to the entity**

1. Select **Add an action**.
2. Select **Create a new record -- Common Data Service**. 
3. In the **Environment** property, enter the environment name where you have previously created the entity. 
4. On the **Entity Name** property, enter **Text Recognizer Results**. 
5. On the **Name** property, select **Response result line detected text**.

![Select Response result line detected text](../media/image5.png)

[!NOTE:] You can also send the results by email, create a file in SharePoint, and more.

The following image shows what your resulting flow should look like.

![Resulting flow](../media/image6.png)

Select **Save**, and your flow is now ready to process images.

The following image is an example of a file that you can drop in the **Images** folder of your OneDrive for Business.

![Example of a file that you can drop in the Images folder](../media/image7.png)

Power Automate will automatically process this file, trigger AI Builder Text Recognition, and store each line of recognized text in the entity.

![Text Recognizer results](../media/image8.png)
