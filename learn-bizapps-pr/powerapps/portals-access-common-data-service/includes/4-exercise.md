The purpose of this exercise is to provide you with hands-on experience to add a list and a form to a Power Apps portal.

## Learning objectives

At the end of these exercises, you will be able to accomplish the following:

- Add a list component to a portal page
- Add a form component to a portal page
- Configure the list component to drill down and view details of the record

### Prerequisites

1. You will need access to the Power Apps maker portal.
1. Ideally you will have the default sample CDS apps and data, but you can use other Common Data Service entities.
1. You will need to have provisioned a Power Apps portal to complete the exercise [Create Portal](https://docs.microsoft.com/powerapps/maker/portals/create-portal/?azure-portal=true).

> [!TIP]
> The exercises work best when you have some sample data to work with. When you provision a CDS environment, you have the opportunity to add sample apps and data.  Please review [Create Environment](https://docs.microsoft.com/power-platform/admin/create-environment.md?azure-portal=true#create-an-environment-with-a-database) steps to provision a CDS environment with sample apps and data.

## Scenario

Your organization has provisioned Power Apps portal and wants to surface a list of ideas the research team is considering on a public web page.  The requirement is also to allow visitors to drill down and view additional details.

## High-level steps

To finish the exercise you need to complete the following tasks.

- Create a web page and add a list component linked to a Common Data Service entity.
- Create a child web page with a form component to display details for a Common Data Service entity.
- Modify the list component to be able to drill down and view the detail record on the form page.

## Detailed steps

### Create a web page for the entity list

We will need to create a web page to contain the Entity List component.

1. Navigate to the [maker portal](https://make.powerapps.com/?azure-portal=true) and sign-in.  
1. Locate your portal app and click on the ellipses (...) and select **Edit** to open the Portal Studio.
1. From the command bar click **+ New page** from **Fixed Layouts** select **Page with title**.
1. In the properties pane, fill the following:

	- **Name**: Ideas
	- **Partial URL**: ideasview
	
1. Click in the canvas area to save the web page.

### Add and configure a list component 
1. On the canvas, select the *page copy* component and then from the toolbelt, choose components.
1. In the Portal components section, select the **List** component.
1. On the properties pane, enter the following values for the list component:

	- **Name**: Ideas List
	- **Entity**: Idea (sample idea) *or choose another entity from your own app*
	- **Views**: Active Ideas

1. Choose **Browse** from the Command bar and ensure that you can see a list of Idea data records from CDS.

### Create a web page for the entity form

We will need to create a web page to contain the Entity Form component to view record details.  This will be a child page of the Ideas list page.

1. From the toolbelt, select **Pages** and locate the *Ideas* page you created earlier.
1. Click on the ellipse (...) and choose **Add a child page**
1. In the properties pane, fill the following:

	- **Name**: Idea Detail
	- **Partial URL**: ideasdetail
	
1. Click in the canvas area to save the web page.

### Add and configure a form component

1. On the canvas, choose the *page copy* component and then from the toolbelt, choose components.
1. In the Portal components section, select the **Form** component.
1. On the properties pane, enter the following values for the form component:

	- **Name**: Ideas Detail
	- **Entity**: Idea (sample idea) *or choose another entity from your own app*
	- **Form Layout**: Information *you can click edit to modify your form or create your own form specifically for the portal*
	- **Mode**:ReadOnly

1. Click in the canvas area to save the web page.

### Modify the list page to navigate to the form component

1. From the toolbelt, choose **Pages** and locate the *Ideas* page that contains the list component.
1. Select the list component on the canvas.
1. On the properties pane, activate the **View Details** option.
1. Fill in the following: 

	- **Target Type**: Form
	- **Form**: Ideas Detail

1. Click in the canvas area to save the web page.
1. Choose **Browse** from the Command bar and ensure that you can see a list of Idea data records from CDS and click on an idea to view details.

> [!div class="mx-imgBorder"]
> [![entity list](../media/4-entity-list-exercise-ss.png)](../media/4-entity-list-exercise-ss.png#lightbox)

You can see how easy it is to add components to a web page that will allow you to quickly view Common Data Service records.
