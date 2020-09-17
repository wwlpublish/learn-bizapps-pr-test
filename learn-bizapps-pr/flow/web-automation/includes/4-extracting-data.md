WinAutomation provides various actions that enable users to extract data and details from web pages. 

To extract information about a web page, you can use the **Get Details of Web Page** action. This action can retrieve several details about a web page, like its title, metadata keywords and description. To use it, you have to define the browser instance and the desired detail to retrieve.

![The Get Details of Web Page action.](..\media\get-details-of-web-page-action.png)

To extract details about a specific element and not the whole web page, use the **Get Details of Element on Web Page** action. This action requires a browser instance and a control specifying the element.

![The Get Details of Element on Web Page action.](..\media\get-details-of-element-on-web-page-action.png)

If you want to take a screenshot from a web page, use the **Take Screenshot of Web Page** action. Through this action, you can take a screenshot of the whole web page or a specific element. The taken screenshot can be saved to the clipboard or a file. 

![The Take Screenshot of Web Page action.](..\media\take-screenshot-of-web-page-action.png)

## Advanced data extraction

It's common in business procedures to extract web data displayed in the form of tables and lists. WinAutomation enables the automation of these procedures through the **Extract Data from Web Page** action.

Like the other web actions, it requires the browser instance containing the page you want to extract data from. 

![The Extract Data from Web Page action.](..\media\extract-data-from-web-page-action.png)

The extracted data can be saved into a variable or a newly generated Excel spreadsheet. The extracted data can be in any of the following forms: 

- **Single Value** - The value is stored as a text. This data form is used to extract a single value, like a product's name.
- **Handpicked (multiple) values** - The values are stored in a list. This data form is used to extract multiple values, like the name and the price of a product.
- **Lists** - This data form is used to extract a single value from multiple registries, like all the available products' names.
- **Tables** - This data form is used to extract multiple values from multiple registries, like all the available products' names and prices.

To specify which data to extract, select the **Specify Data to Extract** button to launch the **Web Helper** dialog. 

![The Specify Data to Extract option in the Extract Data from Web Page action.](..\media\specify-data-to-extract-button.png)

The **Web Helper** dialog consists of two parts:
- The left pane, which is the web browser.
- The right sidebar, which displays a preview of the selected data.

![The Web Helper dialog.](..\media\web-helper.png)

Through the left pane, you can navigate to the page containing the data to be extracted. To extract a specific value, right-click on the desired element, and select the property you want to extract.

![A single value extraction.](..\media\extract-single-value.png)

If you repeat the selection for another corresponding value, a list with the particular values of all the elements will be extracted automatically.

![A list extraction.](..\media\extract-list.png)

If you select an additional value, WinAutomation will return a data table containing the corresponding data for each element in the list.

![A data table extraction.](..\media\extract-table.png)

To extract data spread in multiple pages, right-click on the website's pager and select **Set This Element As Pager**. 

To discard the selection made so far, press the **Reset** button on the right side of the **Web Helper**.

![The Reset button in the Web Helper.](..\media\reset-button.png)

If you want to modify the CSS selectors manually, press the **Advanced Settings** button. 

![The Advanced Settings dialog.](..\media\selectors-editing.png)

Lastly, you can press the **Recalculate Now** button to highlight which data will be extracted based on the current selection. 

This feature can be useful if you want to repeat a similar extraction for multiple pages. For example, it can be used when you want to extract the same values from the pages of different products. 

![The Recalculate button in the Web Helper.](..\media\recalculate-button.png)