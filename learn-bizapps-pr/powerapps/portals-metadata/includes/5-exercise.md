The purpose of this hands-on-lab is to configure a web page layout and add a side menu navigation to other portal pages and external links.

## Learning objectives

At the end of these exercises, you will be able to accomplish the following:

- Identify and modify secondary portal navigation.
- Use the Portal Management app to add new **Web Links** to an existing **Web Link Set**.
- Create a web page with an embedded navigation menu using the Portal Studio.

### Prerequisites

For this exercise you will need to have the following in your environment:

1. A Power Apps portal provisioned. If you do not have a Power Apps portal available, follow [Create Portal](https://docs.microsoft.com/powerapps/maker/portals/create-portal/?azure-portal=true) instructions to create one. 
1. Access to the Power Apps maker portal.

## Scenario

Your organization has provisioned and configured a Power Apps portal. You would like to start modifying the portal navigation to provide quick access to frequently used information.

### High-level steps

To be able to modify portal navigation to suit organizational requirements, you need to complete the following tasks.

- Use the Portal Management app to modify the existing *Secondary Navigation* web link set to include existing web pages and an external link.
- Create new page using the Portal Studio.
- Add a two-column component to the new page.
- Modify the page source code to reference the secondary navigation.

### Detailed steps

#### Update web link set

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true).

1. Make sure correct environment is selected in the environment selector in the top right-hand corner.

1. From the list of Apps, locate and open the Portal Management app (Type = Model-driven).

1. Locate **Web Link Sets** records.

1. Select and open the *Secondary Navigation* **Web Link Set** record.

1. Select the **Links** tab.

1. Press **+ New Web Link**.

1. Enter in the following information:

	- **Name:** *Product A*
	- **Web Link Set:** *Secondary Navigation* (should already be selected)
	- **Publishing State:** *Published*
	- **Page:** *Product A*

     > [!NOTE]
     > This exercise assumes that the portal from blank template was used to provision the portal. If a different template was used your portal may not have the page Product A included. You can select any page of your choice to create the link.

1. Press **Save & Close**. 

1. Again, press **+ New Web Link**.

1. Enter in the following information: 

	- **Name:** *Product B*
	- **Web Link Set:** *Secondary Navigation* (should already be selected)
	- **Publishing State:** *Published*
	- **Page:** *Product B*

1. Press **Save & Close**. 

1. Again, press **+ New Web Link**.

1. Enter in the following information:

	- **Name:** *Microsoft*
	- **Web Link Set:** *Secondary Navigation* (should already be selected)
	- **Publishing State:** *Published*
	- **External URL:** `https://www.microsoft.com`

1. Press **Save & Close** 

#### Launch portal Studio

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true).
1. Make sure correct environment is selected in the environment selector in the top right-hand corner.
1. From the list of Apps, locate your portal app (Type = Portal).
1. Click on the ellipse (...) and choose **Edit**.  This will launch the Portal Studio.

#### Create webpage 

1. From the command bar, choose **+ New Page**, then **Fixed Layouts** and finally **Page with title** template
1. In the properties pane, add the following values:
	- **Name** *Product Links*
	- **Partial URL** *productlinks*

#### Add column component and add navigation 

1. On the canvas, select the page copy component and from the toolbelt, click on the **Components** icon and add the *Two columns section* component.
1. On the canvas, select the left column component.
1. In the bottom-right hand corner, choose the source code editor **</>**.
1. In the Code Editor, locate the following line:

	```html
	<div class="col-md-6 columnBlockLayout" style="display: flex; flex-direction: column;"></div>
	```

1. Add the `{% include "weblink_list_group" weblink_set_name: "Secondary Navigation" %}` Liquid tag to the line so it appears like this:

	```twig
	<div class="col-md-6 columnBlockLayout" style="display: flex; flex-direction: column;">{% include "weblink_list_group" weblink_set_name: "Secondary Navigation" %}</div>
	```

1. Press **Save** to close the source code editor.
1. Press **Browse website**  You should be able to see a page with links to both portal pages and an external link.

> [!NOTE]
> Many portal page components such as lists and forms are represented by Liquid tags.  In this exercise, the *include* tag references the **Web Template** called *Weblink List Group* which describes how the secondary navigation should be rendered.  For more information, please refer to [Work with Liquid templates](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-overview/?azure-portal=true)
