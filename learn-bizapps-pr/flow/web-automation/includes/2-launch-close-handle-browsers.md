WinAutomation provides four launching actions that create a browser instance for each supported browser:

- **Launch New Edge**
- **Launch New Internet Explorer**
- **Launch New Chrome**
- **Launch New Firefox**

All these actions accept similar input parameters and function similarly. Inside the actions, you can set the initial URL of the browser and the desired state of the window.

![Screenshot of the Launch New Edge action.](..\media\launch-new-edge-actions.png)

You can also set whether the action will launch a new browser or attach to one that's already running. The **Launch New Internet Explorer** action provides one additional option in this parameter that will launch the WinAutomation built-in browser.

![Screenshot of the Launch New Internet Explorer action.](..\media\launch-new-internet-explorer-actions.png)

> [!NOTE]
> The **WinAutomation Runtime Browser** implements some limitations that increase the speed and the efficiency of the web-related processes. For more information, see the [WinAutomation documentation page](https://docs.winautomation.com/en/actual-internet-explorer-vs-automated-browser.html).

> [!NOTE]
> Apart from the **WinAutomation Runtime Browser**, the other browsers require proper configuration. For more information, see the [WinAutomation documentation page](https://docs.winautomation.com/en/configure-chrome--firefox-and-edge-for-web-automation.html).

To close a browser instance, use the **Close Web Browser** action. This action accepts a browser instance as input and doesn't return any outputs.

![Screenshot of the Close Web Browser action.](..\media\close-web-browser-actions.png)

If you want to go to a new page using an existing browser instance, use the **Go to Web Page** action. In this action's properties, you need to specify the browser instance and the URL of the webpage that you want to load.

This action can also be used to reload the current page and move a page back or forward.

![Screenshot of the Go to Web Page action.](..\media\go-web-page-action.png)

If you want to launch a new tab in an existing browser instance, use the **Create New Tab** action. This action requires the browser instance and the URL of the page that you want to load.

![Screenshot of the Create New Tab action.](..\media\create-new-tab-actions.png)
