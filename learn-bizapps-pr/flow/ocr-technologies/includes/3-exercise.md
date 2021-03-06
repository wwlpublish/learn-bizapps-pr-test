In this exercise, you'll create a process that extracts text from a PDF file and saves it to a text file. The desired functionality can be implemented with both **MODI** and **Tesseract** OCR engines.

1. Launch WinAutomation and create a new process named **PDF extraction**.

    ![Screenshot of Creating New Process with the name set to P D F extraction, and the Process Designer tool highlighted.](..\media\create-process.png)

1. Use the **Display Select File Dialog** action to prompt users to select a PDF file. In the **File Filter** field, enter the value **\*.pdf** to limit the selectable files.

    ![Screenshot of the Properties of 'Display Select File Dialog' action dialog.](..\media\display-input-dialog.png)

1. Deploy a **Create MODI OCR Engine** action to initialize an OCR engine variable. In the action's properties, set the image width and height multipliers to **2**.

    ![Screenshot of the Properties of 'Create MODI O C R Engine' action dialog.](..\media\create-ocr-engine.png)

1. Add an **Extract Text From PDF With OCR** action to the workspace. Configure it to extract text from all pages of the selected file.

    ![Screenshot of the Properties of 'Extreact Text from P D F with O C R' action dialog.](..\media\extract-text-exercise.png)

1. Use a **Write Text to File** action to write the extracted text to a .txt file. For this example, the selection is to **Overwrite Existing Content** every time.

    ![Screenshot of the Properties of 'Write Text to File' action dialog.](..\media\write-txt-file.png)

1. Save the process and run it to ensure that the extraction is accomplished successfully.

    ![Screenshot of the P D F extraction process running in the Process Designer.](..\media\final-process.png)
