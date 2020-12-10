In this exercise, you'll create a flow that extracts invoice data from scanned documents and saves it to a text file. The wanted functionality can be implemented with both **MODI** and **Tesseract** OCR engines.

1. Launch Power Automate Desktop console and create a new flow named **Invoice extraction**.

    ![The Build a flow dialog.](..\media\exercise-new-flow.png)

1. Use the **Display select file dialog** action to prompt users to select an image file. In the **File filter** field, enter the value **\*.jpg** to limit the selectable files.

    ![The Display select file dialo action.](..\media\exercise-display-select-file-dialog-action.png)

1. Deploy a **Create MODI OCR engine** action to initialize an OCR engine variable. In the action's properties, set the image width and height multipliers to 2.

    ![The Create MODI OCR engine action.](..\media\exercise-create-modi-ocer-engine-action.png)

1. Add an **Extract text with OCR** action to the workspace and configure it to extract text from the previously selected image. 

    ![The Extract text with OCR action.](..\media\exercise-extract-text-with-ocr-action.png)

1. Use a **Write text to file** action to write the extracted text to a .txt file. For this example, we chose to overwrite the existing content of the file in each execution. 

    ![The Write text to file action.](..\media\exercise-write-text-to-file-action.png)

1. Save the flow and run it to ensure that the extraction is completed successfully.

    ![The final flow and the save and run buttons.](..\media\exericse-final-flow.png)