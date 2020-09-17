WinAutomation provides four browser launching actions that create a browser instance for each supported browser: 

- **Launch New Edge**
- **Launch New Internet Explorer**
- **Launch New Chrome**
- **Launch New Firefox**

All these actions accept similar input parameters and function in the same way. Inside the actions, you can set the initial URL of the browser and the desired state of the window. 

![The Launch New Edge action.](..\media\launch-new-edge-action.png)

You can also set whether the action will launch a new browser or attach to an already running one. The **Launch New Internet Explorer** provides one additional option in this parameter that launches the WinAutomation build-in browser. 

![The Launch New Internet Explorer action.](..\media\launch-new-internet-explorer-action.png)

>[!NOTE]
>The **WinAutomation Runtime Browser** implements some limitations that increase the speed and the efficiency of the web-related processes. More information can be found in the [respective WinAutomation documentation page](https://docs.winautomation.com/en/actual-internet-explorer-vs-automated-browser.html). 

>[!NOTE]
>Apart from **WinAutomation Runtime Browser**, the other browsers require the proper configuration. More information can be found in the [respective WinAutomation documentation page](https://docs.winautomation.com/en/configure-chrome--firefox-and-edge-for-web-automation.html).

To close a browser instance, use the **Close Web Browser** action. This action accepts a browser instance as input and doesn't return any outputs.

![The Close Web Browser action.](..\media\close-web-browser-action.png)

If you want to navigate to a new page using an existing browser instance, use the **Go to Web Page** action. In this action's properties, you have to specify the browser instance and the URL of the web page to load. 

This action can also be used to reload the current page and move a page back or forward.

![The Go to Web Page action.](..\media\go-to-web-page-action.png)

If you want to launch a new tab in an existing browser instance, use the **Create New Tab** action. This action requires the browser instance and the URL of the page to load. 

![The Create New Tab action.](..\media\create-new-tab-action.png)