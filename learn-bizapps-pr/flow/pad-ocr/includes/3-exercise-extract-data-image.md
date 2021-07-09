In this exercise, you'll create a flow that extracts invoice data from scanned documents and saves it to a text file. The wanted functionality can be implemented with both **MODI** and **Tesseract** OCR engines.

1. Launch Power Automate Desktop console and create a new flow named **Invoice extraction**.

    ![Screenshot of the Build a flow dialog with Flow name set to Invoice extraction.](..\media\exercise-new-flow.png)

1. Use the **Display select file dialog** action to prompt users to select an image file. In the **File filter** field, enter the value **\*.jpg** to limit the selectable files.

    ![Screenshot of the Display select file dialog action.](..\media\exercise-display-select-file-dialog-action.png)

1. Add an **Extract text with OCR** action to the workspace and configure it to extract text from the previously selected image. In the **OCR engine settings**, set the image width and height multipliers to 2.

    ![Screenshot of the Extract text with O C R action.](..\media\exercise-extract-text-with-ocr-action.png)

1. Use a **Write text to file** action to write the extracted text to a .txt file. For this example, we chose to overwrite the existing content of the file in each execution.

    ![Screenshot of the Write text to file action.](..\media\exercise-write-text-to-file-action.png)

1. Save the flow and run it to ensure that the extraction is completed successfully.

    > [!NOTE]
    > To test the flow, you can use the [newinvoice.jpg](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-automate-desktop/newinvoice.zip) image file. Select **Download** on the right side of the page and extract the downloaded file to your local computer.

> [!div class="mx-imgBorder"]
> [![Screenshot of the appropriate buttons in the designer to save and run the final flow.](../media/exericse-final-flow.png)](../media/exericse-final-flow.png#lightbox)
