Develop a process that connects to an Active Directory server, creates a new user and object, and adds the user to a group.

Specifically, the process will:

* Open an Active Directory connection
* Create a user with details based on the details provided
* Add the user to an existing group
* Add a computer based on the details provided

## Connect to AD Server

Create a new Process and add the **Connect to Active Directory Server** Action. Enter the **LDAP Path**, specifying the Domain Controllers.

If authentication is required, check **Use Authentication**, and provide your **Authentication Type** as well as your credentials.
  
![connect to ad server properties exercise](..\media\connect-to-ad-server-properties-exercise.png)
 
## Create an Active Directory User

The **Create Active Directory User** Action requires the location where the user is to be created. Enter the location of the **Users** container. 

Provide the user’s personal details and credentials as below. Check the **Disable account** and **Password never expires** boxes.

* First Name—Norbert
* Last Name—Varga
* Initials—NV
* Username—nvarga
* Password—Password123
	
![create ad user properties exercise](..\media\create-ad-user-properties-exercise.png)

## Add User to Group

At this point in the process, an Active Directory user has been created, and the next step is to add this user to a group. 

Use the **Modify Active Directory Group** Action. Specify the group by using its distinguished name and set the Operation to **Add User**, again specifying the user’s distinguished name.
  
![modify ad group properties exercise](..\media\modify-ad-group-properties-exercise.png)

## Create Computer Object

Next add the **Create Active Directory Object** action. Set the Object Name to **JSBOT** (in uppercase). The object’s location should be the **Computers** container, and the Object Type should be to **Computer** as well.
  
![create ad object properties exercise](..\media\create-ad-object-properties-exercise.png)

## Close Connection

The last action in the process, **Close Active Directory Connection** will disconnect from the Active Directory server.
  
![close ad connection properties exercise](..\media\close-ad-connection-properties-exercise.png)

## Running the Process

Execute the process. An Active Directory connection will be established. A user is created based on your input, the user is added to a group, a computer is created, and the connection is closed.

## Active Directory Check

You can check that the objects have been created by going to “Active Directory Users and Computers” on the server machine. Under users, check for the user and group, also confirming that the user is a member of the specified group. Under computers, the new computer object can also be confirmed to have been created.