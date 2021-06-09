In this exercise, you will develop a process that connects to an Active Directory server, creates a new user and object, and then adds the user to a group.

You will complete the following tasks:

- Open an Active Directory connection.
- Create a user with information based on the provided details.
- Add the user to an existing group.
- Add a computer based on the provided details.

## Connect to an Active Directory server

Create a new process and then add the **Connect to Active Directory Server** action. Enter information in the **LDAP Path** field, specifying the domain controllers.

If authentication is required, select the **Use Authentication** check box, and then provide your **Authentication Type** and credentials.
  
![Screenshot of Properties of 'Connect to Active Directory User' action dialog with the L DAP Path property set to LDAP://DC=contoso,DC=demo.](..\media\connect-to-ad-server-properties-exercise.png)

## Create an Active Directory user

The **Create Active Directory User** action requires the location where the user will be created. Enter the location of the user's container.

Provide the user’s personal details and credentials, as follows, and then select the **Disable account** and **Password never expires** check boxes.

- **First Name** — Norbert
- **Last Name** — Varga
- **Initials** — NV
- **Username** — nvarga
- **Password** — Password123

![Screenshot of Properties of 'Create Active Directory User' action dialog with the Action Input properties listed above highlighted.](..\media\create-ad-user-properties-exercise.png)

## Add the user to a group

Now that an Active Directory user has been created, the next step is to add this user to a group with the **Modify Active Directory Group** action.

Specify the group by filling in the **Distinguished Name** field and then set the **Operation** option to **Add User**, again specifying the user’s distinguished name.
  
![Screenshot of Properties of 'Modify Active Directory Group' action dialog with Distinguished Name, Operation, and User Distinguished Name highlighted.](..\media\modify-ad-group-properties-exercise.png)

## Create a computer object

Next, you will add the **Create Active Directory Object** action. Set the **Object Name** field to **NVBOT** (in uppercase). The object’s location should be the computer's container, and the **Object Type** option should be set to **Computer**.
  
![Screenshot of Properties of 'Create Active Directory Object' action dialog with the Object Name, Location, and Object Type properties highlighted.](..\media\create-ad-object-properties-exercise.png)

## Close connection

The last step in the process, **Close Active Directory Connection**, will disconnect from the Active Directory server.
  
![Screenshot of Properties of 'Close Active Directory Connection' action dialog. This action closes a previously opened Active Directory connection.](..\media\close-ad-connection-properties-exercise.png)

## Run the process

Run the process, and an Active Directory connection will be established. To determine if the process was successful, you should notice that a user was created based on your input, the user was added to a group, a computer was created, and then the connection was closed.

## Active Directory check

You can check that the objects have been created by going to **Active Directory Users and Computers** on the server machine. Under **Users**, check for the user and group and also confirm that the user is a member of the specified group. Under **Computers**, you can also confirm that the new computer object was created.
