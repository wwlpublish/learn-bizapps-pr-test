## Connecting to an Active Directory server

First, for any Active Directory related Process to work, a connection to an Active Directory Server has to be established. The **Connect to an Active Directory Server** Action, used for this purpose, will require the LDAP path, specifying the Domain Controllers.
 

![connect to ad server action properties](..\media\connect-to-ad-server-action-properties.png)

Enabling Use Authentication adds additional fields. In case authentication is required, you will need to provide the **Authentication Type** along with your **Username** and **Password**.
  
![connect to ad server action properties continued](..\media\connect-to-ad-server-action-properties-continued.png)

The output, **Parent Entry**, is stored into a variable which stores the Active Directory connection and thus can be referenced by other Active Directory Actions.

>[!NOTE]
>The LDAP Path should have the following format:
>LDAP://DC=contoso,DC=demo

 
## Closing the Active Directory connection
The connection can be closed by using the **Close Active Directory Connection** Action. The only input the Action requires is the variable that stores the Active Directory Parent Entry.
  
![close ad connection action properties](..\media\close-ad-connection-action-properties.png)

>[!NOTE]
>All Active Directory Actions will require that the Active Directory Parent Entry is specified. The name of the variable from the Connect to an Active Directory Server Action where the parent entry is stored will be populated automatically into any Active Directory Action, even if the default variable name has been changed.
 
## User management

Active Directory user management Actions are used to create, modify, update and unlock Users, as well as retrieve information about them. 

Creating a user is done with the **Create Active Directory User** Action. Initially, the **Active Directory Parent Entry** has to be specified. 

**Location** must be the location of the Users container. The user’s details can be entered as needed. The Password can be provided directly (typed into the field) or it can be retrieved from a variable.
  
![create ad user action properties](..\media\create-ad-user-action-properties.png)

>[!NOTE]
>Location should have the following format:
>CN=Users,DC=contoso,DC=demo
 

The Modify Active Directory User Action allows for following operations to be performed on a user:

* Enable
* Disable
* Rename
* Delete
* Reset Password
  
![modify ad user action properties](..\media\modify-ad-user-action-properties.png)

>[!NOTE]
>All Active Directory user management Actions will require the user’s Distinguished Name. The distinguished name should have the following format:
>CN=nvarga,CN=Users,DC=contoso,DC=demo
>Where nvarga is the username.

The **Update Active Directory User** Action is used to either add additional details to, or modify any existing details of, an Active Directory User.
  
![update ad user action properties](..\media\update-ad-user-action-properties.png)
 
The **Unlock Active Directory User** Action functions in a similar manner, except the required inputs are limited to those which are required for any Active Directory and User Management Actions.
  
![unlock active ad user action properties](..\media\unlock-active-ad-user-action-properties.png)

Similarly, the **Get Active Directory User Info** Action requires the same inputs. The retrieved info is stored in a variable.
  
![get ad user info action properties](..\media\get-ad-user-info-action-properties.png)

>[!NOTE]
>To list the distinguished names of all Active Directory users, open the command prompt and execute the following command:
dsquery user

## Group management

Active Directory groups can be created and modified similarly to users. The **Create Active Directory Group** Action will require a Group Name and a Location, similarly to the previously described Actions. A Description can be added, and a group scope and type must be defined as well.
  
![create ad group action properties](..\media\create-ad-group-action-properties.png)

The Modify Active Directory Group Action requires the distinguished name of the group, and, in case the operation applies to the user, the distinguished name of the user as well.
  
![modify ad group action properties](..\media\modify-ad-group-action-properties.png)

Both **Get Active Directory Group Info** and **Get Active Directory Group Members** will require the distinguished name of the group and store the retrieved information in a variable.

>[!NOTE]To list the distinguished names of all Active Directory groups, open the command prompt and execute the following command:
dsquery group

## Object management

Active Directory objects can be created, moved, renamed and deleted. To create an object, use **Create Active Directory Object** Action. The object’s name, location and type must be specified in the action properties.
  
![create ad object action properties](..\media\create-ad-object-action-properties.png)

To move, delete or rename an object, use the appropriate actions, specifying the object by its distinguished name. When moving or renaming, specify the new location and new name respectively.

>[!NOTE]To list the distinguished names of all Active Directory computers, open the command prompt and execute the following command:
dsquery computer

To list the distinguished names of all Active Directory organizational units:
dsquery ou