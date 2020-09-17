WinAutomation enables users to interact with any web application through controls. Every element of a web page, like a button and a text field, is considered a control.

Each control is specified by CSS selectors that pinpoint the specific elements you want to interact with. 

The created controls are stored in the **Controls Repository**, located on the bottom part of the **Process Designer**. 

![The Controls Repository in the Process Designer.](..\media\process-designer-controls-repository.png)

All the actions that handle specific elements in web pages require controls as input. To create a control:

1.  Open the action's properties and select the **Select Control From Repository** button. 

    ![The Select Control From Repository button in the CLick Link on Web Page action's properties.](..\media\click-link-on-web-page-action-select-control.png)

1.  Select the **Add Control** button to create a new control. 


    ![The Add Control option in the Link on Web Page action's properties.](..\media\click-link-on-web-page-action-add-control.png)

1.  Use the **Live Helpers** (orange boxes) to select the desired element.

    ![The Live Helpers in the browser.](..\media\live-helpers.png)

1.  Press **Ctrl + Left Click** while the desired element is selected to create the control. 

    ![The created control used in the Click Link on Web Page action's properties.](..\media\created-control.png)

>[!NOTE]
>More information about controls can be found in the **Using repositories in WinAutomation** module.

In the following section of the unit, you can see all the web actions that use controls to handle web page elements and forms. 

## Click Link on Web Page

The **Click Link on Web Page** action enables you to click a link or another element in a web page. This action requires a control that defines the exact element to click on and a browser instance.

![The Click Link on Web Page action.](..\media\click-link-on-web-page-action.png)

## Click Download Link on Web Page

If you want to click a download link on a web page, use the **Click Download Link on Web Page** action instead of the **Click Link on Web Page** action.

Apart from the clicking, this action handles the popup dialogs automatically and saves the downloaded file in a specified folder.

Like the **Click Link on Web Page** action, it requires a browser instance and a control that specifies the link.

![The lick Download Link on Web Page action.](..\media\click-download-link-on-web-page-action.png)

## Hover Mouse over element on Web Page

The **Hover Mouse over element on Web Page** action allows you to relocate the mouse over a specified web page element. This feature can be helpful in web pages that provide hoverable menus. 

Inside the action, you have to specify the browser instance and a control describing the element to hover. 

![The Hover Mouse over element on Web Page action.](..\media\hover-mouse-over-element-on-web-page.png)

## Focus Text Field on Web Page

The **Focus Text Field on Web Page** action sets the input focus on a defined text box on a web page. The text box is specified by a control, while the action also requires a browser instance. 

![The Focus Text Field on Web Page action.](..\media\focus-text-field-on-webpage.png)

## Populate Text Field on Web Page

To populate a web text field, you can use the **Populate Text Field on Web Page** action. In the action's properties, set the text to write, the browser instance, and the control describing the text field. 

Additionally, you can determine whether the action will emulate typing.

![The Populate Text Field on Web Page action.](..\media\populate-text-field-on-web-page.png)

## Set Checkbox State on Web Page

To enable or disable a checkbox on a web form, you can use the **Set Checkbox State on Web Page** action. The action requires the checkbox's desired state, a browser instance, and a control describing the checkbox.

![The Set Checkbox State on Web Page action.](..\media\set-checkbox-state-on-web-page.png)

## Select Radio Button on Web Page

To select a radio button on a web page, use the **Select Radio Button on Web Page** action. Like the other web form handling actions, you have to define a browser instance and a control describing the radio button.

![The Select Radio Button on Web Page action.](..\media\select-radio-button-on-web-page.png)

## Set DropDown List Value on Web page

If you want to pick a specific option in a web dropdown list, use the **Set DropDown List Value on Web page** action. 

The desired option can be selected through its name or its index. The action also requires a browser instance and a control specifying the dropdown list.

![The Set DropDown List Value on Web page action.](..\media\set-dropDown-list-value-on-web-page.png)

## Press Button on Web page

The last action to handle web forms is the **Press Button on Web page** action. Through this action, you can press buttons on web pages.The button to press is specified by a control, while the action also requires a browser instance. 

![The Press Button on Web page action.](..\media\press-button-on-web-page.png)