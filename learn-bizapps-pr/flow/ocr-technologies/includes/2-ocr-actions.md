WinAutomation provides three primary OCR actions, while there are also four more actions from other groups that use OCR. In this unit, we'll present all the actions that use OCR technologies.  

## Create OCR Engine

Before using any OCR actions, you have to initialize an OCR engine. WinAutomation supports the **Microsoft MODI** and the **Google Tesseract** engines through the respective actions.

Both **Create MODI OCR Engine** and **Create Tesseract OCR Engine** actions have the same structure and work identically. 

![The Create MODI OCR Engine action.](..\media\create-modi.png)

To initialize the engine, specify its language, and set the image's width and height multiplier. 

Image multipliers increase the size of the image to make the text extraction or searching more effective. Avoid using values greater than two, because high values may lead to failed results. 

As an output, these actions produce an OCR engine variable. This variable is used as input in other OCR actions.

![The Create Tesseract OCR Engine action.](..\media\create-tesseract.png)

> [!NOTE]
> To use the **Create MODI OCR Engine** action you have to install the MODI OCR engine. Find more information in the [WinAutomation documentation](https://docs.winautomation.com/en/install-modi.html).

## Extract Text With OCR - Extract Text From PDF With OCR

After creating an engine, you can use the **Extract Text With OCR** action to extract text from the screen, the foreground window, or an image file.

You can specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

![The Extract Text With OCR action.](..\media\extract-text.png)

In case you want to extract text from a PDF file, use the **Extract Text From PDF With OCR** action. In the action's properties, specify the file and the extraction mode.

The file can be provided through a hardcoded file path or a variable containing a file. The extraction can be made to the whole document, a specific page, or a range of pages.

![The Extract Text From PDF With OCR action.](..\media\extract-text-pdf.png)

## If Text on Screen

Except for text extraction, OCR actions enable you to check if a given text exists or not on the screen or the foreground window. 

To implement this kind of condition, deploy the **If Text on Screen** action. In the action's properties, specify the text to search and the source of it. 

You can also specify whether the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

![The If Text on Screen action.](..\media\if-text-screen.png)

## Wait for Text on Screen

Some processes may need to wait for an application or webpage to load before continuing to the next actions. You can ensure that the required information is loaded using the **Wait for Text on Screen** action.

In the action's properties, choose if you want to wait for the text to appear or disappear and its source. The text can be a hardcoded string or a regular expression, while the source can be the whole screen or the foreground window. 

You can specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

![The Wait for Text on Screen action.](..\media\wait-text.png)

As a protection measure, the action provides a time limit field that determines how long the action will wait for the text.

As an output, the action produces two variables describing the exact position of the found text. 

![The output variables of the Wait for Text on Screen action.](..\media\wait-text-outputs.png)

## Move Mouse to Text on Screen

WinAutomation provides the mouse and keyboard actions to automate applications that aren't compatible with the UI actions. In these cases, you can use the **Move Mouse to Text on Screen** action to move the mouse to a wished part of the screen. 

In the action's properties, populate the text to search for and its source. The text can be a hardcoded string or a regular expression, while the source can be the whole screen or the foreground window. 

You can specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion relative to an image.

![The Move Mouse to Text on Screen action.](..\media\move-mouse.png)


If there are many occurrences of the same text in the defined source, specify which one to select in the **Occurrences** field.

Lastly, select if you want the mouse to be moved instantly or with animation (slow, natural, or fast). 

As an output, the action produces four variables describing the found text's exact position and size. 

![The output variables of the Move Mouse to Text on Screen action.](..\media\move-mouse-outputs.png)