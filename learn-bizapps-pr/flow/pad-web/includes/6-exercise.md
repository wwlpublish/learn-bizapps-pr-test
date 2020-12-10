In this exercise, you'll create a flow that extracts gainer stocks from the MSN website and stores them in a new Excel worksheet.

> [!NOTE]
> The exercise is developed based on the USA version of the MSN Money page, but it'll work with all the regional versions with the same structure.

1. Launch Power Automate Desktop console and create a new flow named **Gainer stocks extraction**.

    ![The Build a flow dialog.](..\media\exercise-new-flow.png)

1. Deploy a browser launching action and set its initial URL to the [MSN Money main page](https://www.msn.com/money). For this example, we used the **Launch new Edge** action; however, all browser launching actions can be used.

   ![The Launch new Edge action.](..\media\exercise-launch-new-edge.png)

1. Add a **Click link on web page** action and set it to select the **Markets** link on the MSN Money main page.

   ![The first Click link on web page action clicking the Markets link.](..\media\exercise-click-link-on-web-page-markets.png)

1. Add a second **Click link on web page** action and set it to select the **GAINERS** link on the **MSN Markets** page.

   ![The second  Click link on web page action clicking the Markets Gainers link.](..\media\exercise-click-link-on-web-page-gainers.png)

1. Use the **Extract data from web page** action to extract the names and prices of the gainer stocks.

    1. Set the previously defined browser instance as input and select to save the extracted data in a new Excel spreadsheet.

        ![The Extract data from web page action.](..\media\exercise-extract-data-from-web-page-action.png)

    1. While the action's properties dialog is open, launch your browser and navigate to the gainer stocks page that you used in the previous steps. Right-click on the name of the first stock and select to extract its text attribute.

        ![Extracting first stock.](..\media\exercise-extracting-first-stock.png)

    1. Repeat the same procedure for the name of the second stock. If the selection is correct, a list with all gainer stocks must be displayed in the **Live web helper**.

        ![Extracting all stocks](..\media\exercise-extracting-all-stocks.png)

    1. Right-click on the price of the first stock and select to extract its text attribute. Now, a table with the names and prices of all the stocks must be displayed.

        ![Extracting the prices of the stocks](..\media\exercise-extracting-pricesk.png)

1. Use the **Close web browser** action to close the previously opened browser instance.

   ![The Close web browser action.](..\media\exercise-close-web-browser.png)

1. Use an **Insert row to Excel worksheet** action to add a new line at the top of the created spreadsheet.

   ![The Insert row to Excel worksheet action.](..\media\exercise-insert-row-to-excel-worksheet-action.png)

1. Deploy a **Write to Excel worksheet** action to create a header for the column that contains the stocks' names.

   ![The first Write to Excel worksheet action to write the name header.](..\media\exercise-write-to-excel-worksheet-action-name.png)

1. Repeat the previous step to create a header for the column that contains the stocks' prices.

   ![The second Write to Excel worksheet action to write the price header.](..\media\exercise-write-to-excel-worksheet-action-price.png)

1. Add a **Close Excel** action to save and close the Excel worksheet. Because the file is new, and you will be saving it for the first time, select **Save document as** in the **Before closing Excel** drop-down list.

   ![The Close Excel action.](..\media\exercise-close-excel-action.png)

1. Save the flow and run it to ensure that every action runs as expected.

   ![The final flow and the save and run buttons.](..\media\exercise-final-flow.png)