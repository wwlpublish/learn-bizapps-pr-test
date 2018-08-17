## Create environments for your apps
An environment is a container for apps and other resources, like data connections and flows from Microsoft Flow. It's a way to group things based on business requirements.

![Environment picker](../media/powerapps-environments2.png)

If you have followed along with the course so far, you've spent some time working in web.powerapps.com. Whether you knew it or not, you have been working in a specific environment the whole time.

In the upper right web.powerapps.com page, you see your current environment.

![Environment picker](../media/powerapps-environment-picker.png)

If you are new to PowerApps, you might have only the default environment at this point.

- Select the menu to see if there are other environments available.

### Why use environments?
There are several reasons to create additional environments beyond the default one:

- **Separate app development by department**: In a large organization, each department could work in a different environment. Having separate environments allows department employee to see only apps and company data appropriate to their needs.
- **Support application lifecycle management (ALM)**: Separate environments allows you to separate apps that are in development stages from those that you have already been shared. Or maybe you want a trial environment so that you can gain feedback from employees before rolling out the final app. For some organizations, showing apps before they are completely developed and published can present security concerns.
- **Manage data access**: Each environment can have its own source of business data, called a Common Data Service for Apps database. Other data connections are specific to the environment and cannot be shared across environments

[!NOTE] Keep in mind that environments are relevant only to app creators and PowerApps admins. When you share an app to a user, that user just runs the app as long as they have the right permissions. You users don't have to worry about what environment it came from.

### Create an environment
Only an admin can create environments. If you're not an admin, this information can still be helpful when you talk to your admin about setting up environments.

1. From the Web.powerapps.com home page, select the gear icon on the right, and select **Admin Center**.

    You can also go directly to admin.powerapps.com.

2. In the PowerApps Admin Center, select **New environment**. 
3. On the **New environment** box, enter a name for the environment, select a region, and the environment type.
4. Select **Create environment**.

That's it. You now have a new environment to work in. If you go back to web.powerapps.com, you will see it in the environments list.

### Manage access to an environment
Two types of people within an organizaion have access to an environment:

* **System administrator**: A system admin has full permissions to create and manage environments.
* **Environment maker**: An environmental maker can see all apps, create apps, and work with the Common Data Service for Apps (other permissions apply).

1. Select the **Environments** tab on the left.
2. Select an environment.
3. Enter the person's email for whom you want to assign a role.
4. Select **Add User**.
5. Select **Assign security roles**. The Dynamics 365 user management center will appear.
6. select the new name.
7. Select **Manage Roles** in the toolbar.
8. Select the types of roles for this user in the **Manage User Roles** box. In the example below, the user has been assigned the Environment Maker role.

    ![Select a new user role](../media/powerapps-user-roles.png)

9. Select **OK**.

You now understand the benefits of environments, and how to create them and grant access to them. Even if you're not in an admin role, it's helpful to know how this works.