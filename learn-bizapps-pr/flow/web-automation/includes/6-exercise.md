In this unit, you'll create a process that extracts the gainer stocks from the MSN website. The extracted names and prices will be stored in a new Excel worksheet. 

1. Launch WinAutomation and create a new process named **Gainer stocks extraction**.

    ![The Create New Process dialog.](..\media\create-new-process.png)  

1. Deploy a browser launching action and set its initial URL to the [MSN Money main page](https://www.msn.com/en-us/money). We used the **Launch New Edge** action for this example, but all browser launching action can be used. 

    ![The populated Launch New Edge action.](..\media\launch-new-edge-action-url.png)

1. Add a **Click Link on Web Page** action and set it to click the **Markets** link on the **MSN Money** main page.

    ![The Markets link in the MSN page.](..\media\markets-link.png)

1. Add a second **Click Link on Web Page** action and set it to click the **GAINERS** link on the **MSN Markets** page.

    ![The Gainers link in the MSN page.](..\media\gainers-link.png)

1. Use the **Extract Data from Web Page** action to extract the names and the prices of the gainer stocks. 

    1. Set the previously defined browser instance as input and select to save the extracted data in a new Excel spreadsheet.

        ![The populated Extract Data from Web Page action.](..\media\extract-data-from-web-page-configuration.png)

    1. Press the **Specify Data to Extract** button and navigate to the [MSN page for gainer stocks](https://www.msn.com/en-us/money/markets/marketmovers/fi-gainers) that we used in the previous steps.

        ![The Web Helper dialog.](..\media\web-helper-url.png)

    1. Right-click on the name of the first stock and select its text attribute.

        ![The options to extract the name of the first stock.](..\media\extract-first-name.png)

    1. Repeat the same procedure for the name of the second stock. If the selection is correct, a list with all the gainer stocks must be displayed in the **Web Helper**.

        ![The list containing the stock's names in the Web Helper.](..\media\extract-names.png)

    1. Right-click on the price of the first stock and select its text attribute. Now, a table with the names and prices of the stocks must be displayed in the **Web Helper**.

        ![The data table containing the stock's names and prices in the Web Helper.](..\media\extract-prices.png)

1. Use the **Close Web Browser** action to close the previously open browser instance.

    ![The populated Close Web Browser action.](..\media\close-web-browser.png)

1. Use an **Insert Row to Excel Worksheet** action to add a new line at the top of the created spreadsheet.

    ![The populated Insert Row to Excel Worksheet action.](..\media\insert-row-to-excel-worksheet.png)

1. Deploy a **Write to Excel Worksheet** action to create a header for the column containing the stocks' names. 

    ![The populated Write to Excel Worksheet action for the name header.](..\media\write-to-excel-worksheet-name.png)

1. Repeat the same step to create a header for the column containing the stocks' prices. 

    ![The populated Write to Excel Worksheet action for the price header.](..\media\write-to-excel-worksheet-price.png)

1. Add a **Close Excel** action to save and close the Excel worksheet. Because the file is new and you'll save it for the first time, select **Save document as** in the **Before Closing Excel** dropdown list. 

    ![The populated Close Excel action.](..\media\write-to-excel-worksheet-price.png)

1. Lastly, save the process and execute it to ensure that every action runs as expected. 

    ![The final process.](..\media\final-process.png)