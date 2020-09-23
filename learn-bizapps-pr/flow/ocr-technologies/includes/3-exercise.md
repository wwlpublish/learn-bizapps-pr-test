In this exercise, you'll create a process that extracts text from a PDF file and saves it to a text file. The desired functionality can be implemented with both **MODI** and **Tesseract** OCR engines. 

1. Launch WinAutomation and create a new process named **PDF extraction**.

    ![](..\media\create-process.png)

1. Use the **Display Select File Dialog** action to prompt users to select a PDF file. In the **File Filter** field, enter the value **.pdf** to limit the selectable files. 

    ![](..\media\display-input-dialog.png)

1. Deploy a **Create MODI OCR Engine** action to initialize an OCR engine variable. In the action's properties, set the image width and height multipliers to **2**.

    ![](..\media\create-ocr-engine.png)

1. Add an **Extract Text From PDF With OCR** action to the workspace. Configure it to extract text from all pages of the selected file.

    ![](..\media\extract-text-exercise.png)

1. Use a **Write Text to File** action to write the extracted text to a .txt file. For this example, the selection is to **Overwrite Existing Content** every time.

    ![](..\media\write-txt-file.png)

1. Save the process and run it to ensure that the extraction is accomplished successfully. 

    ![](..\media\final-process.png)
