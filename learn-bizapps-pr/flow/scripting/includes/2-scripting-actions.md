WinAutomation offers five scripting actions that satisfy almost every automation scenario. Complex Windows and web operations can be executed efficiently through short blocks of code. 

## Run VBScript

The **Run VBScript** action accepts a VBScript code as input and stores the result of the execution in the **VBScriptOutput** variable. Optionally, you can define a variable to store potential errors. 

![The Run VBScript action.](..\media\run-vbscript.png)

## Run JavaScript

The **Run JavaScript** action accepts a JavaScript code as input and stores the result of the execution in the **JavascriptOutput** variable. Optionally, you can define a variable to store potential errors. 

![The Run JavaScript action.](..\media\run-javascript.png)

## Execute JavaScript Function on Web Page

The **Execute JavaScript Function on Web Page** action functions similarly to the **Run JavaScript** action. The main difference is that this action also accepts a browser instance as an input.

The result is store in the **Result** variable, while the action doesn't provide separate variables for the potential errors. 

There's also the **Use Template** button in the action's properties, which creates the main structure of a JavaScript function automatically.

![The Execute JavaScript Function on Web Page action.](..\media\run-javascript-browser.png)

## Run PowerShell Script

The **Run PowerShell Script** action accepts a PowerShell code as input and stores the result of the execution in the **PowershellOutput** variable. Optionally, you can define a variable to store potential errors. 

![The Run PowerShell Script action.](..\media\run-powershell.png)

## Run Python Script

The **Run Python Script** action accepts a Python code as input and stores the result of the execution in the **PythonScriptOutput** variable. Optionally, you can define a variable to store potential errors. 

![The Run Python Script action.](..\media\run-python.png)