WinAutomation provides various actions that enable users to extract data and details from webpages.

To extract information about a webpage, you can use the **Get Details of Web Page** action. This action can retrieve several details about a webpage, such as its title, metadata keywords, and description. To use this action, you need to define the browser instance and the desired detail to retrieve.

![Screenshot of the Get Details of Web Page action.](..\media\get-details-web-page-action.png)

To extract details about a specific element rather than the entire webpage, use the **Get Details of Element on Web Page** action. This action requires a browser instance and a control that specifies the element.

![Screenshot of the Get Details of Element on Web Page action.](..\media\get-details-element-web-page-action.png)

If you want to take a screenshot from a webpage, use the **Take Screenshot of Web Page** action. Through this action, you can take a screenshot of the entire webpage or a specific element. The taken screenshot can be saved to the clipboard or a file.

![Screenshot of the Take Screenshot of Web Page action.](..\media\take-screenshot-web-page-action.png)

## Advanced data extraction

It's common in business procedures to extract web data that is displayed in the form of tables and lists. WinAutomation enables the automation of these procedures through the **Extract Data from Web Page** action.

Similar to the other web actions, the **Extract Data from Web Page** action requires the browser instance that contains the page that you want to extract data from.

![Screenshot of the Extract Data from Web Page action.](..\media\extract-data-from-web-page-actions.png)

The extracted data can be saved into a variable or a newly generated Microsoft Excel spreadsheet. The extracted data can be in any of the following forms:

- **Single value** - The value is stored as a text. This data form is used to extract a single value, like a product's name.
- **Handpicked (multiple) values** - The values are stored in a list. This data form is used to extract multiple values, like the name and price of a product.
- **Lists** - This data form is used to extract a single value from multiple registries, like all available product names.
- **Tables** - This data form is used to extract multiple values from multiple registries, like all available product names and prices.

To specify which data to extract, select the **Specify Web Data to Extract** button to launch the **Web Helper** dialog box.

![Screenshot of the Specify Web Data to Extract option in the Extract Data from Web Page action.](..\media\specify-data-extract-button.png)

The **Web Helper** dialog box consists of two parts:

- The left pane, which is the web browser
- The right sidebar, which displays a preview of the selected data

![Screenshot of the Web Helper dialog box.](..\media\web-helpers.png)

Use the left pane to go to the page that contains the data that you want to extract. To extract a specific value, right-click the desired element and select the property that you want to extract.

![Screenshot of a single value extraction.](..\media\extract-single-values.png)

If you repeat the selection for another corresponding value, a list with the particular values of all elements will be extracted automatically.

![Screenshot of a list extraction preview.](..\media\extract-lists.png)

If you select an additional value, WinAutomation will return a data table that contains the corresponding data for each element in the list.

![Screenshot of a data table extraction preview.](..\media\extract-tables.png)

To extract data that is spread throughout multiple pages, right-click the website's **Pager** button and then select **Set This Element As Pager**.

To discard the selection that you have made, select the **Reset** button to the right of the **Web Helper**.

![Screenshot of the Reset button in the Web Helper.](..\media\reset-buttons.png)

If you want to modify the CSS selectors manually, select the **Advanced Settings** button.

![Screenshot of the Advanced Settings dialog box.](..\media\selector-editing.png)

Select the **Recalculate Now** button to highlight which data will be extracted based on the current selection.

This feature can be useful if you want to repeat a similar extraction for multiple pages, such as when you want to extract the same values from the pages of different products.

![Screenshot of the Recalculate button in the Web Helper.](..\media\recalculate-buttons.png)
