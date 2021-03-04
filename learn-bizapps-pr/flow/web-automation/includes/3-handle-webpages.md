WinAutomation provides users with the ability to interact with any web application through controls. Every element of a webpage, such as a button and a text field, is considered a control.

Each control is specified by Cascading Style Sheets (CSS) selectors that pinpoint the specific elements that you want to interact with.

The created controls are stored in the **Controls Repository**, which is located in the lower portion of the **Process Designer**.

![Screenshot of the Controls Repository in the Process Designer.](..\media\process-designer-controls-repository.png)

All actions that handle specific elements in webpages require controls as input. To create a control, follow these steps:

1. Open the action's properties and select the **Select Control From Repository** button.

    ![Screenshot of the Select Control From Repository button in the Click Link on Web Page action's properties.](..\media\click-link-on-web-page-action-select-control.png)

1. Select the **Add Control** button to create a new control.

    ![Screenshot of the Add Control option in the Link on Web Page action's properties.](..\media\click-link-on-web-page-action-add-control.png)

1. Use the **Live Helpers** (orange boxes) to select the desired element.

    ![Screenshot of the Live Helpers in the browser.](..\media\live-helpers.png)

1. Press **Ctrl + left-click** while the desired element is selected to create the control.

    ![Screenshot of the created control used in the Click Link on Web Page action's properties.](..\media\create-control.png)

> [!NOTE]
> For more information about controls, see the **Use repositories in WinAutomation** module.

The following sections describe all web actions that use controls to handle webpage elements and forms.

## Click Link on Web Page action

The **Click Link on Web Page** action enables you to select a link or another element on a webpage. This action requires a control that defines the exact element to select and a browser instance.

![Screenshot of the Click Link on Web Page action.](..\media\click-link-on-web-page.png)

## Click Download Link on Web Page action

If you want to select a download link on a webpage, use the **Click Download Link on Web Page** action instead of the **Click Link on Web Page** action.

Apart from the selection, this action handles the pop-up dialog boxes automatically and saves the downloaded file in a specified folder.

Similar to the **Click Link on Web Page** action, the **Click Download Link on Web Page** action requires a browser instance and a control that specifies the link.

![Screenshot of the Click Download Link on Web Page action.](..\media\click-download-link-on-web-page.png)

## Hover Mouse over element on Web Page action

The **Hover Mouse over element on Web Page** action allows you to relocate the mouse pointer over a specified webpage element. This feature can be helpful on webpages that provide menus that you can hover over.

Inside the action, you need to specify the browser instance and a control that describes the element to hover over.

![Screenshot of the Hover Mouse over element on Web Page action.](..\media\hover-mouse-over-element-web-page.png)

## Focus Text Field on Web Page action

The **Focus Text Field on Web Page** action sets the input focus on a defined text box on a webpage. The text box is specified by a control, while the action also requires a browser instance.

![Screenshot of the Focus Text Field on Web Page action.](..\media\focus-text-field-webpage.png)

## Populate Text Field on Web Page action

To populate a web text field, you can use the **Populate Text Field on Web Page** action. In the action's properties, set the text to write, the browser instance, and the control that describes the text field.

Additionally, you can determine whether the action will emulate typing.

![Screenshot of the Populate Text Field on Web Page action.](..\media\populate-text-field-web-page.png)

## Set Checkbox State on Web Page action

To enable or disable a check box on a web form, you can use the **Set Checkbox State on Web Page** action. The action requires the check box's desired state, a browser instance, and a control that describes the check box.

![Screenshot of the Set Checkbox State on Web Page action.](..\media\set-checkbox-state-web-page.png)

## Select Radio Button on Web Page action

To select a radio button on a webpage, use the **Select Radio Button on Web Page** action. Like the other web form handling actions, you need to define a browser instance and a control that describes the button.

![Screenshot of the Select Radio Button on Web Page action.](..\media\select-radio-button-web-page.png)

## Set DropDown List Value on Web page action

If you want to pick a specific option in a web drop-down list, use the **Set DropDown List Value on Web Page** action.

The desired option can be selected through its name or index. The action also requires a browser instance and a control that specifies the drop-down list.

![Screenshot of the Set DropDown List Value on Web Page action.](..\media\set-dropDown-list-value-web-page.png)

## Press Button on Web Page action

The last action to handle web forms is the **Press Button on Web Page** action. Through this action, you can press buttons on webpages. The button to press is specified by a control, while the action also requires a browser instance.

![Screenshot of the Press Button on Web Page action.](..\media\press-button-web-page.png)
