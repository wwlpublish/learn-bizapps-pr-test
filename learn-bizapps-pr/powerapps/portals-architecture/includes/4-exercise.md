The purpose of this exercise is to create a web page using the Portal Studio.

At the end of these exercises, you will be able to accomplish the following:

- Open the Portal Studio to edit your portal
- Create a new web page using existing page templates
- Add content to your web page

For this exercise you will need to have the following in your environment:

1. A Power Apps portal provisioned. If you do not have a Power Apps portal available, follow [Create Portal](https://docs.microsoft.com/powerapps/maker/portals/create-portal/?azure-portal=true) instructions to create one.
1. Access to the Power Apps maker portal.

## Scenario

Creating and editing a portal web page is an easy process and allows you to quickly build a power portal application. In this exercise you need to complete the following tasks:

- Open your portal in Power Apps portal Studio
- Create a new web page 
- Add a component with two sections 
- Configure one section to display text 
- Configure another section to display an existing portal image

### Launch portal Studio

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true).
1. Make sure correct environment is selected in the environment selector in the top right-hand corner.
1. From the list of Apps, locate your portal app (Type = Portal).
1. Click on the ellipse (...) and choose **Edit**.  This will launch the Portal Studio.

### Create new web page
1. From the command bar, choose **New page**.
1. Move the mouse over **Fixed layouts** and then choose **Page with title**.
1. A new web page will appear with the title *New page*.
1. In the properties pane, enter a new name for the web page, press tab, the web page will autosave.
1. In the properties pane, enter a name without spaces for the partial URL, press tab, the web page will autosave.

### Add static content
1. On the canvas, select the text area that contains "This website uses sample data..." .
1. On the toolbelt, choose **Components** (grid icon).
1. In the **Section layout** area, select **Two columns section**.  This will add a two column section on the web page canvas.
1. On the canvas, select the left column section.
1. On the toolbelt, select **Components** and then select **Text** from the **Portal components** section.
1. On the canvas, add some text to the component.
1. On the canvas, select the right column section.
1. On the toolbelt, select **Components** and then select **Image** from the **Portal components** section.
1. On the properties pane, from the drop down, select **AboutUs.png**.

### View web page

1. From the command bar, choose **Browse website**.
1. You should now see your new web page on the portal.
1. Note that there is also a link on the main menu to your web page.

> [!div class="mx-imgBorder"]
> [![first web page](../media/4-first-web-page-ss.png)](../media/4-first-web-page-ss.png#lightbox)
