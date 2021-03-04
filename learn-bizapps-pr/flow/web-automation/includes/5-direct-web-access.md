WinAutomation provides three actions that enable users to interact with APIs and run scripts on webpages:

- **Download from Web**

- **Invoke Web Service**

- **Execute Javascript Function on Web Page**

## Download from Web action

The **Download from Web** action downloads text and files from webpages. To use this action, you need to specify the URL of the desired page and the appropriate method (GET or POST).

The returned text is stored into a variable, while the downloaded files are saved as files locally.

![Screenshot of the Download from Web action.](..\media\download-from-web-actions.png)

## Invoke Web Service action

The **Invoke Web Service** action is used to send data to web services and retrieve the responses.

Every web service comes with API documentation that specifies the appropriate input parameters. The use of invalid parameters might cause an exception.

The text responses are stored into a variable, while the retrieved files are saved as files locally.

![Screenshot of the Invoke Web Service action.](..\media\invoke-web-services-actions.png)

## Execute Javascript Function on Web Page action

The **Execute Javascript Function on Web Page** action implements JavaScript functions on webpages.

This action accepts a browser instance and a JavaScript function as inputs and then stores the result of the implementation in the **Result** variable.

You can select the **Use Template** button to automatically create the JavaScript function's main structure.

![Screenshot of the Execute JavaScript Function on Web Page action.](..\media\execute-javascript-function-on-web-page-actions.png)
