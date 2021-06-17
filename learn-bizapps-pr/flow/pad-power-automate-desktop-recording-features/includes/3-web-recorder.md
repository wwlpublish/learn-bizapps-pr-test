To become familiar with the web recorder, follow the presented instructions to develop a web-based flow. The flow will convert a set amount of USA dollars to euros using the MSN currency converter tool.

To record the flow:

1. Create a new desktop flow, select **Web recorder** in the flow designer, and select the web browser to use for the recording.

    ![The Specify web browser instance to use dialog.](..\media\web-recorder-instance-selection-dialog.png)

1. After selecting the browser, a browser window will open automatically. Use this window to navigate to the [MSN currency converter page](https://www.msn.com/en-us/money/tools/currencyconverter).

    ![The MSN currency converter page.](..\media\msn-currency-converter-page.png)

1. Select **Record** in the web recorder and set the drop-down menus of the converter to **United States Dollar** and **Euro**, respectively1.

    ![The currency drop-down menus in the MSN currency converter page.](..\media\msn-currency-converter-page-drop-down-menus.png)

1. Populate the amount of USA dollars to convert in the appropriate field of the page.

    ![The populated USA dollar field in the MSN currency converter page.](..\media\msn-currency-converter-page-populate-dollars.png)

1. Select the field with the converted euros, right-click on it, and extract its value.

    ![The option to extract the converted euros from the MSN currency converter page.](..\media\msn-currency-converter-page-extract-euros.png)

1. Finally, press **Finish** to add all the automatically generated actions to the flow. These actions are no different from any others: they can be moved, edited, or deleted.

    ![The generated action in the workspace.](..\media\web-recorder-generated-actions.png)