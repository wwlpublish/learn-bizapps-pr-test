# Explore your app
Now we're going to look more closely at PowerApps Studio and the screens and controls that define your app's behavior. You can  We won't go through all the details, but seeing more about how this app works will help you to build your own apps. 

## Understand controls in PowerApps
A control is simply a UI element that produces an action or displays information. Many controls in PowerApps are the same as controls that you've used in other apps: labels, text-input boxes, drop-down lists, navigation elements, and so on.

In addition to these typical controls, PowerApps has more specialized controls. These can be found on the top toolbar.

![Controls tab on PowerApps Studio ribbon](../media/powerapps-ribbon-controls.png)

Here are just a few that add interest and impact to your apps:

- **Galleries**: These controls are layout containers that contain a set of controls that represent data from a data source.
- **Forms**: These controls display detail data and enable you to create and edit items. 
- **Media**: These controls allow you add pictures as background images, camera button for your users to take a picture with the app, and a barcode reader for quick capture of identification information. 
- **Charts**: These allow you to add charts for instant analysis on the road.

To see what's available, Select **Insert** on the ribbon, and then select each of the options in turn.

## Explore the browse screen
Each of the three app screens has a main control and some additional controls. The first screen in the app is the browse screen, named **BrowseScreen1** by default. 

Here are some of the primary controls for the Browse screen that you will want to become familiar with:
- **BrowseGallery1**: This is the main control on this screen. It displays data from your data source.  
- **NextArrow1**: This control when selected sends the app to the Details screen. 
-  **IconNewItem1**: This screen sends the app to the Edit/Create screen.

![Browse screen with controls](../media/powerapps-browse-screen.png)

PowerApps has a variety of gallery types beyond the default vertical orientation. 

- Try the horizontal orientation to see how it changes the look of your app. You will see more ways to control layout later in this section.

![PowerApps gallery options](../media/powerapps-galleries.png)

## Explore the details screen
Next is the details screen. Here are its main controls:
- **DetailScreen1** This is the main control on this screen
- **DetailForm1**: This control is a container for other controls.
- **DataCard1**: This is a card control, which displays, in this case, a flooring category from the Flooring Estimates app seen from the previous topic. 
- **IconEdit1** This control when selected allows a user to edit the current item using the Edit/Create screen in the next section.

![Details screen with controls](../media/powerapps-details-screen.png)

## Explore the Edit/Screan screen
The third screen in the app is the Edit/Create screen. Here are its main controls:
- **EditScreen1**: This is the main control on this screen.
- **EditForm1**: This control is a container for other controls.
-  **DataCard8** This is another a card control, which displays a flooring category from tghe Flooring Estimates app see from the previous topic.
- **IconAccept1** This control when selected allows the user to save the changes made on the screen.

![Edit screen with controls](../media/powerapps-edit-screen.png)

Now that you have a sense of how the app is composed of screens and controls, we'll look at how you customize the app in the next topic.