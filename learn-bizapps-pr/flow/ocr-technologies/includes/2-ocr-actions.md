WinAutomation provides three primary OCR actions, while four more actions are also available from other groups that use OCR. The following sections discuss all actions that use OCR technologies.  

## Create the OCR engine

Before using OCR actions, you need to initialize an OCR engine. WinAutomation supports the Microsoft MODI and Google Tesseract engines through the **Create MODI OCR Engine** and **Create Tesseract OCR Engine** actions, which have the same structure and work identically.

![The Create MODI OCR Engine action.](..\media\create-modi.png)

To initialize the engine, you need to specify its language and set the image's width and height multipliers. 

Image multipliers increase the size of the image to make text extraction or searching more effective. Avoid using values greater than two because high values might lead to failed results. 

As an output, these actions produce an OCR engine variable. This variable is used as input in other OCR actions.

![The Create Tesseract OCR Engine action.](..\media\create-tesseract.png)

> [!NOTE]
> To use the **Create MODI OCR Engine** action, you need to install the MODI OCR engine. For more information, see the [WinAutomation documentation](https://docs.winautomation.com/en/install-modi.html).

## Extract text 

After creating an engine, you can use the **Extract Text With OCR** action to extract text from the screen, the foreground window, or an image file.

You can specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion that is relative to an image.

![The Extract Text With OCR action.](..\media\extract-text.png)

If you want to extract text from a PDF file, you can use the **Extract Text From PDF With OCR** action. In the action's properties, you can specify the file and the extraction mode.

The file can be provided through a hardcoded file path or a variable that contains a file. The extraction can be made to the whole document, a specific page, or a range of pages.

![The Extract Text From PDF With OCR action.](..\media\extract-text-pdf.png)

## Verify if text is on the screen or a window

Except for text extraction, OCR actions enable you to check whether a given text exists on the screen or the foreground window. 

To implement this kind of condition, deploy the **If Text on Screen (OCR)** action. In the action's properties, you can specify the text to search for and the source of it. 

You can also specify whether the text will be extracted from the whole selected source, a specific subregion, or a subregion that is relative to an image.

![The If Text on Screen action.](..\media\if-text-screen.png)

## Wait for text on the screen

Some processes might need to wait for an application or webpage to load before continuing to the next actions. You can ensure that the required information is loaded by using the **Wait for Text on Screen (OCR)** action.

In the action's properties, you can choose whether you want to wait for the text to appear or disappear and wait for its source. The text can be a hardcoded string or a regular expression, while the source can be the whole screen or the foreground window. 

You can specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion that is relative to an image.

![The Wait for Text on Screen action.](..\media\wait-text.png)

As a protection measure, the action provides a time limit field that determines how long the action will wait for the text.

As an output, the action produces two variables that describe the exact position of the found text. 

![The output variables of the Wait for Text on Screen action.](..\media\wait-text-outputs.png)

## Mouse actions

WinAutomation provides the mouse and keyboard actions to automate applications that aren't compatible with UI actions. In these circumstances, you can use the **Move Mouse to Text on Screen** action to move the mouse to a part of the screen of your choosing. 

In the action's properties, you can populate the text to search for and its source. The text can be a hardcoded string or a regular expression, while the source can be the whole screen or the foreground window. 

You can specify if the text will be extracted from the whole selected source, a specific subregion, or a subregion that is relative to an image.

![The Move Mouse to Text on Screen action.](..\media\move-mouse.png)


If several occurrences of the same text are in the defined source, specify which one to select in the **Occurrences** field. Additionally, you can select if you want the mouse to be moved instantly or with animation (slow, natural, or fast). 

As an output, the action produces four variables that describe the found text's exact position and size. 

![The output variables of the Move Mouse to Text on Screen action.](..\media\move-mouse-outputs.png)
