WinAutomation provides 15 Active Directory actions that enable you to add, remove, or update users, user roles, and objects in the Active Directory server.

## Connect to an Active Directory server

For any Active Directory-related process to work, you need to establish a connection to an Active Directory server. You can establish the connection by using the **Connect to Active Directory Server** action, which will require the LDAP path to specify the domain controllers.

![Screenshot of Properties of 'Connect to Active Directory Server' action dialog with the Action Input L DAP Path property highlighted.](..\media\connect-to-ad-server-action-properties.png)

Selecting the **Use Authentication** check box will enable you to add more fields. If authentication is required, you will need to provide the **Authentication Type** along with your **Username** and **Password**.
  
![Screenshot of the dialog with the Use Authentication option selected, and Authentication Type, Username, Password Mode, and Password properties.](..\media\connect-to-ad-server-action-properties-continued.png)

The output, **Parent Entry**, is stored into a variable that stores the Active Directory connection; therefore, it can be referenced by other Active Directory actions.

> [!NOTE]
> The **LDAP Path** field should have the following format:
> LDAP://DC=contoso,DC=demo

## Close the Active Directory connection

You can close the Active Directory connection by using the **Close Active Directory Connection** action. The only input that this action requires is the variable that stores the Active Directory Parent Entry.
  
![Screenshot of Properties of 'Close Active Directory Server Connection' action dialog. This action closes a previously opened Active Directory connection.](..\media\close-ad-connection-action-properties.png)

> [!NOTE]
> All Active Directory actions will require that the Active Directory Parent Entry is specified. The name of the variable from the **Connect to Active Directory Server** action where the parent entry is stored will be populated automatically into any Active Directory action, even if the default variable name has been changed.

## User management

Active Directory user management actions are used to create, modify, update, and unlock users and retrieve information about them.

You can create a user with the **Create Active Directory User** action. Initially, the Active Directory Parent Entry must be specified.

The **Location** field must contain the location of the user's container. The user’s details can be entered, as necessary. You can provide the password directly (by entering it into the field), or you can retrieve it from a variable.
  
![Screenshot of Properties of 'Create Active Directory User' action dialog General tab has the properties listed below.](..\media\create-ad-user-action-properties.png)

Active Directory user properties:

- Active Directory Entry
- Location
- First Name
- Initials
- Last Name
- Username
- Password Mode
- Password
- Disable account
- Password never expires

> [!NOTE]
> The **Location** field should have the following format:
> CN=Users,DC=contoso,DC=demo

The **Modify Active Directory User** action allows you to perform the following operations on a user account:

- Enable
- Disable
- Rename
- Delete
- Reset Password
  
![Screenshot of Properties of 'Modify Active Directory User' action dialog with the Operation property expanded and Enable selected.](..\media\modify-ad-user-action-properties.png)

> [!NOTE]
> All Active Directory user management actions will require the user’s distinguished name. The **Distinguished Name** field should have the following format:
> CN=nvarga,CN=Users,DC=contoso,DC=demo,
> where **nvarga** is the username.

You can use the **Update Active Directory User** action to add more details to, or modify existing details of, an Active Directory user.
  
![Screenshot of Properties of 'Update Active Directory User' action dialog  General tab has the properties listed below.](..\media\update-ad-user-action-properties.png)

Action Input properties:

- Active Directory Entry
- Distinguished Name
- First Name
- Initials
- Last Name
- Display Name
- Job Title
- Department
- Email
- Company
- Telephone number
- Extension
- City
- Zip/Postal Code
- State/Province
- Street Address
- Country/Region

The **Unlock Active Directory User** action behaves in a similar manner as the **Update Active Directory User** action, except that the required inputs are limited to those that are required for any Active Directory and user management actions.
  
![Screenshot of Properties of 'Unlock Active Directory User' action dialog with Active Directory Entry and Distinguished Name properties.](..\media\unlock-active-ad-user-action-properties.png)

Similarly, the **Get Active Directory User Info** action requires the same inputs. The retrieved information will be stored in a variable.
  
![Screenshot of Properties of 'Get Active Directory User Info' action dialog with the same input properties, and Action Output property User Info.](..\media\get-ad-user-info-action-properties.png)

> [!NOTE]
> To list the distinguished names of all Active Directory users, open the command prompt and run the following command:
dsquery user

## Group management

Similar to how you create and modify users, you can also create and modify Active Directory groups. The **Create Active Directory Group** action requires that you fill in the **Group Name** and **Location** fields, as you did for the previously described actions. Additionally, you can provide a description and define a group scope and type.
  
![Screenshot of Properties of 'Create Active Directory Group' action dialog with the properties listed below.](..\media\create-ad-group-action-properties.png)

Action Input properties:

- Active Directory Entry
- Group Name
- Location
- Description
- Group Scope
- Group Type

The **Modify Active Directory Group** action requires the distinguished name of the group and, if the operation applies to the user, the distinguished name of the user.
  
![Screenshot of Properties of 'Modify Active Directory Group' action dialog with the Operation property expanded and Rename selected.](..\media\modify-ad-group-action-properties.png)

The **Get Active Directory Group Info** and **Get Active Directory Group Members** actions will require the distinguished name of the group and will store the retrieved information in a variable.

> [!NOTE]
> To list the distinguished names of all Active Directory groups, open the command prompt and run the following command:
> dsquery group

## Object management

Active Directory objects can be created, moved, renamed, and deleted. To create an object, use the **Create Active Directory Object** action. The object’s name, location, and type must be specified in the action properties.
  
![Screenshot of Properties of 'Create Active Directory Object' action dialog with A D Entry, Object Name, Location, and Object Type properties.](..\media\create-ad-object-action-properties.png)

To move, delete, or rename an object, use the appropriate actions and then specify the object by its distinguished name. When you are moving or renaming and object, specify the new location and new name.

> [!NOTE]
> To list the distinguished names of all Active Directory computers, open the command prompt and run the following command:
> dsquery computer
>
> To list the distinguished names of all Active Directory organizational units, open the command prompt and run the following command:
> dsquery ou
