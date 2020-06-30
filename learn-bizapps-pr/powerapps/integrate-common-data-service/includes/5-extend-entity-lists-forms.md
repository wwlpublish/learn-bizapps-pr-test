Entity lists, entity forms, and web forms are the fundamental building blocks that enable Common Data Service data interactions for portal users. Each of them can be used in isolation. An entity list can display a company directory and allow users to download it as an Excel spreadsheet. An entity form can capture leads on a "contact us" page. A web form can collect anonymous product feedback from site visitors.

The real power of the Power App portals platform, however, is in how these components can be brought together using data-driven configuration. Let's see how we can use the lists and forms together and start building robust and functional web apps instead of isolated web pages.

## Linking lists and forms

Let's consider the Help desk application included in the portal templates.

* **Entity forms** are in place to enable users to create a new case or edit an existing case. These forms leverage model-driven forms defined in a Common Data Service instance with the Dynamics 365 Service app.

   > [!div class="mx-imgBorder"]
   > [![Case entity forms](../media/case-entity-forms.png)](../media/case-entity-forms.png#lightbox)

* The **entity list** has actions linked to **entity forms**.

   > [!div class="mx-imgBorder"]
   > [![Case entity lists](../media/case-entity-list.png)](../media/case-entity-list.png#lightbox)

* The **entity form** for editing a case also has **metadata** to refine the display of some fields and enable the Timeline subgrid for comments. The **entity list** includes case-specific actions such as *Close Case*.

   > [!div class="mx-imgBorder"]
   > [![Case form explained](../media/case-form-explained.png)](../media/case-form-explained.png#lightbox)

This entity list is related to the **Customer Service – Home** web page and portal where users are presented with a complete application in an easy-to-use format.

You can use this pattern across any entity in the Common Data Service, and any new entity that may be required to meet a customer’s needs. The basic configuration includes:

* Entity lists built on one or more views.
* Entity forms to create and view individual records. If the record creation process is complicated, use a web form instead.
* Action button configuration on the entity list to use entity forms for create, update, and view operations.
* **On Success** setting for the entity forms to redirect users back to the list where applicable.

Basic configuration is usually sufficient to get started. You can enhance this configuration with some additional settings.

## Advanced settings

Power Apps portals extend Common Data Service functionality to web audiences, but they are not a direct replacement for model-driven Power Apps. Power Apps portals use model-driven views and forms to define the layout and behavior of lists and forms on the website, but not all features of model-driven apps are available in portals.

There are no direct equivalents for client-side Business Rules or custom JavaScript. Only HTML and image web resources are supported, and HTML cannot rely on any scripts communicating with the parent model-driven form. There are some other limitations as well, for example connections, PCF controls, file datatype and multi-select option sets are not supported.

You can use advanced settings to implement some of the features that do not map across from model-driven apps to portals.

### Commands

Entity lists, entity forms, and web forms include Action Button Configuration that adds per-record actions. See [Entity form action configuration](https://docs.microsoft.com/powerapps/maker/portals/configure/entity-forms#entity-form-action-configuration/?azure-portal=true) and [Entity list configuration](https://docs.microsoft.com/powerapps/maker/portals/configure/entity-lists#entity-list-configuration/?azure-portal=true) for information about available actions.

Some commands include the **Filter Criteria** setting. You can use it to enter FetchXML that evaluates and hides the command if the selected record is not returned by the specified FetchXML query.

### Form metadata

Metadata settings for both entity forms and web forms control the appearance and behavior of individual form elements including fields, sections, tabs, subgrids, and notes.

For example, one of the most common techniques is to specify default values for individual fields. Quite often it's used in combination with hidden fields, for example, case origin can be hidden and set to Web. That ensures that all cases created via the portal have appropriate case origin set without the need for any server-side reinforcement of the rule.

For more details about metadata configuration for forms, see [Configure web form metadata for portals](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-web-form-metadata/?azure-portal=true).

### Form subgrids

If a model-driven form includes a subgrid of related records, the entity form and web forms display a read-only list of records using the default view. To enable actions for the grid such as Create, Update, and Delete, you must configure those actions by using metadata configuration. Metadata configuration allows you to implement the portal equivalent of standard grid commands available in model-driven apps. For more information and step-by-step instructions, see [Configure Web form subgrids for portals](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-web-form-subgrid/?azure-portal=true).

### Notes

Notes are supported by Power Apps portals out of the box. Just like with subgrids, adding notes to your forms on the portal is easy. Just add the Notes control to the model-driven form. You can configure the behavior of the Notes control by using metadata. For more details, see [Configure notes for entity forms and web forms on portals](https://docs.microsoft.com/powerapps/maker/portals/configure-notes/?azure-portal=true).

However, the Notes entity is not customizable in the Common Data Service. As a result, there are certain restrictions on supported functionality. For example, editing is only allowed by the note's author, there is no support for an approval process, and visibility of notes is defined by the content using a predefined naming convention. All these limitations restrict the use of notes in most scenarios.

Power Apps portals include alternative implementations for notes and attachments using portal comments custom activity.

> [!TIP]
> Consider replacing notes with portal comments if your implementation allows that.

Portal comments can be surfaced on a form using the Timeline control. There is no functional difference in the portal implementation of the Notes and Timeline controls and the same metadata configuration is available. Using portal comments has the following benefits:

* Comment approval using the Send command. Only sent or received comments are visible on the portal.
* Record of portal users who created and received the comment.
* Further customization of the Portal Comment entity is possible to implement additional business requirements.

For a reference implementation using Portal Comments, see how case comments are implemented on any of the  portal templates.

## Extending with workflow

Forms and lists support extensibility using classic Common Data Service workflows. This is a very flexible and powerful mechanism to expose additional business functionality. Simply define a classic Common Data Service workflow for the target entity and add a workflow action button.

Both real-time and background workflows are supported and you can configure the action button to refresh the page or redirect to the destination of your choice after the workflow is called.

For example, you could add a custom Email Update button to the case form that invokes a classic workflow to email case details and notes history to the current portal user.
