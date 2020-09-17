WinAutomation provides three actions that enable users to interact with APIs and execute scripts on web pages.

## Download from Web

The **Download from Web** action downloads text and files from web pages. To use this action, you have to specify the URL of the desired page and the appropriate method (GET or POST). 

The returned text is stored into a variable, while the downloaded files are saved as files locally.

![The Download from Web action.](..\media\download-from-web-action.png)

## Invoke Web Service

The **Invoke Web Service** action is used to send data to web services and retrieve the respective responses. 

Every web service comes with API documentation that specifies the appropriate input parameters. The use of invalid parameters may cause an exception. 

The text responses are stored into a variable, while the retrieved files are saved as files locally.

![The Invoke Web Service action.](..\media\invoke-web-services-action.png)

## Execute JavaScript Function on Web Page

The **Execute JavaScript Function on Web Page** action executes JavaScript functions on web pages. 

This action accepts a browser instance and a JavaScript function as inputs, and stores the result of the execution in the Result variable.

You can use the **Use Template** button to automatically create the JavaScript function's main structure.

![The Execute JavaScript Function on Web Page action.](..\media\execute-javascript-function-on-web-page-action.png)