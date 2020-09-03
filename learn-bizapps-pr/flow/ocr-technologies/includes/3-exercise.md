In this exercise, you'll create a process that extracts text from a PDF file and saves it to a text file. The wished functionality can be implemented with both **MODI** and **Tesseract** OCR engines. 

1. Launch WinAutomation and create a new process named **PDF extraction**.

    ![](..\media\create-process.png)

1. Use a **Display Select File Dialog** action to prompt users to select a PDF file. In the **file filter** field, enter the value **.pdf** to limit the selectable files. 

    ![](..\media\display-input-dialog.png)

1. Deploy a **Create MODI OCR Engine** action to initialize an OCR engine variable. In the action's properties, set the image multipliers to two.

    ![](..\media\create-ocr-engine.png)

1. Now, add an **Extract Text From PDF WIth OCR** action to the workspace. Configure it to extract text from all the pages of the selected file.

    ![](..\media\extract-text-exercise.png)

1. Use a **Write Text to File** action to write the extracted text to a .txt file. In this example, we selected to overwrite each time the content of the file.

    ![](..\media\write-txt-file.png)

1. Lastly, save the process and run it to ensure that the extraction is accomplished successfully. 

    ![](..\media\final-process.png)