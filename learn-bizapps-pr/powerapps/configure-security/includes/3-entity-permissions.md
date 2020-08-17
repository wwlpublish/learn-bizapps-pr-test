Entity permissions define the access and scope that a portal user has to a particular Common Data Service or Dynamics 365 entity on the portal. Common Data Service records can be accessed on a Power Apps portal by using an entity form, entity list, or web form, or it can be shown by using *Liquid* tags in webpage content or web templates.

> [!div class="mx-imgBorder"]
> [![Entity Permission](../media/entity-permission.png)](../media/entity-permission.png#lightbox)

You can create an entity permission in the Portal Management app and associate it to a specific web role to allow portal user access.

> [!div class="mx-imgBorder"]
> [![Entity Permission Web Role](../media/web-role-entity-lists.png)](../media/web-role-entity-lists.png#lightbox)

## Create an entity permission

Follow these steps to create a new **Entity Permission** record:

1. Identify the entity that will be secured.
1. Define scope.
1. For any scope other than Global, select the relationships that define that scope.
1. Determine the privileges that are being granted to the role through this permission.

> [!IMPORTANT]
> Rights are cumulative. If a user is in one role that grants Read rights and another role that grants Read and Update rights, the user will have Read and Update rights for any records that overlap between the two roles. No mechanism exists to reduce the permission scope or remove a privilege by assigning another role.

The **Entity Permission** record includes the following common attributes.

| Attribute                             | Description                                                  |
| ------------------------------------ | ------------------------------------------------------------ |
| Entity Name                           | Name of the entity that you are securing on the portal.       |
| Scope                                 | Defines which records can be accessed.                        |
| Account/Contact/Parental Relationship | Defines the relationship from portal user, parent account, or related record to the record that is being secured. |
| Parent Entity Details                 | The Entity Name and Entity Permission that defines permission to the parent entity. |
| Privileges                            | Defines what privileges are being granted by this permission set: Read, Write, Create, Delete, Append, Append To. |

The following sections closely examine how these attributes are used to define scope and identify the records that the portal user has access to.

## Global scope

If an **Entity Permission** record that has Global scope is associated with a web role, any contact in that role will have specified access to all records of the defined entity in Common Data Service.

For example, if a lead entity is granted the Read privilege with Global scope, all users in assigned web roles will be able to see all leads. This permission will be automatically respected by any entity lists, essentially showing all records, according to the model-driven views, that have been defined for that list.

> [!div class="mx-imgBorder"]
> [![Global scope](../media/global-scope.png)](../media/global-scope.png#lightbox)

Global scope is most frequently used with Read privilege to provide access to the reference data, for example, a list of countries or currencies.

## Contact scope

With Contact scope, a signed-in user in the role for which the entity permission record is defined will have the rights granted by that permission only for records that are related to that user's contact record through a selected Common Data Service relationship.

On an entity list, a filter will be added to whatever model-driven views are shown by that list, which only retrieves records that are directly linked to the current user. Depending on the scenario, this relationship can be thought of as ownership or management rights.

> [!div class="mx-imgBorder"]
> [![Contact scope](../media/contact-scope.png)](../media/contact-scope.png#lightbox)

For example, a set of privileges can be granted to a web role that allow Contact scope access to the orders by using the customer type of relationship. In other words, any portal user with that web role will have access to a subset that can be considered as *My Orders*.

## Account scope

With Account scope, a signed-in user in the role for which the permission record is defined will have the rights granted by that permission only for records that are related to that user's parent account record through a selected Common Data Service relationship.

> [!div class="mx-imgBorder"]
> [![Account scope](../media/account-scope.png)](../media/account-scope.png#lightbox)

For example, a set of privileges is granted to a web role that allows Account scope access to the cases by using a customer type relationship between an account and case entities. In other words, any portal user with that web role will have access to a subset that can be thought of as *My Account's Cases*. 

## Parent scope

Parent scope is designed to cover most complex scenarios where a portal user will require full access to the records but the access must be limited to a specific scope. For example, for users who have access to Cases (for example, *My Cases*), you would grant permissions to those users to access Notes that are related to the cases, but you would restrict access to the Notes for only the cases that the user already has access to.

The **Parent Permission** record defines a permission and scope for an entity (Cases, in this example). With that permission in place, a child permission is created that defines a relationship from another entity (Notes, in this example) to the entity that is defined in the parent relationship (Cases).

> [!div class="mx-imgBorder"]
> [![Parental scope](../media/parental-scope.png)](../media/parental-scope.png#lightbox)

Users in a web role with access to records that are defined by parent entity permissions will also have rights, as defined by the child permission record, to the records that are related to the parent record.

## Self scope

Self scope allows you to define the rights that a user has to their own contact record. This scope allows people to use entity forms or web forms to make changes to the contact record that is linked with their profile.

The default profile page has a special built-in form that allows any user to change their basic contact info and to opt in or out of marketing lists. If this form is used in your portal, users won't require the Self scope permission to use it. However, they'll require the Self scope permission to use any other custom entity forms or web forms that target their contact record.

To apply entity permissions to entity list or entity form components, a maker will need to select the **Enable entity permissions** check box when configuring the component in the portals Studio.

> [!div class="mx-imgBorder"]
> [![Portal Studio Set Entity Permission](../media/portal-studio-entity-permission.png)](../media/portal-studio-entity-permission.png#lightbox)

**Entity permissions** are automatically applied to data that is retrieved by using Liquid tags.

<!--VIDEO EntityPermissions.mp4-->
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4AjtN]

For more information, see [Add record-based security by using entity permissions for portals](https://docs.microsoft.com/powerapps/maker/portals/configure/assign-entity-permissions/?azure-portal=true).
