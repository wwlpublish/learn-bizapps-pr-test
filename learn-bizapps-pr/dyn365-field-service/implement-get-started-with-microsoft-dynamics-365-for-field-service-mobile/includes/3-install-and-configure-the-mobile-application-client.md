The mobile application available for Microsoft Dynamics 365 for Field Service is based on Resco Mobile CRM. Field Service Mobile provides field agents with a unique set of capabilities that are not typically available with the traditional Dynamics 365 mobile application. Organizations that are implementing Dynamics 365 Field Service, need to deploy the mobile application for all field agents that will be servicing customers. Deploying Field Service Mobile involves several steps to ensure that agents can use all  features and run the application successfully.

To ensure that agents can launch and use Field Service Mobile, you'll need to a publish a mobile project for the Dynamics 365 instance you have Field Service installed on. You'll also need to download and deploy it to each field
agent who will access it.

To deploy the Field Service Mobile client:

- Deploy and publish a Field Service Mobile project using the Resco Woodford solution.
   - Download the Woodford solution.
   - Import the Woodford solution into your Dynamics 365 for Field Service instance.
   - Download the standalone editor.
   - Download the Field Service mobile project template.
   - Import the Field Service Mobile project template.
   - Assign security roles to the mobile project.
   - Publish the Field Service Mobile Project.
- Deploy the Field Service Mobile application to field agents.
   - Download the mobile client.
   - Connect the mobile client to the Dynamics 365 instance where field service is installed.

> [!IMPORTANT]
> Following the steps outlined above is critical to ensure successful deployment of the mobile application. If these steps are not followed, agents might not be able to access the application, or it might not function properly.

### Downloading the Woodford solution and standalone editor

Field Service mobile uses the Woodford solution to deploy and customize the application. The solution provides access to the necessary customization and publishing tools as well as assists in creating and deploying mobile projects.

### Version Numbers

Field Service Mobile is based on the Resco Mobile CRM Woodford solution, version 11.1.1. At the time this course was created, the Woodford solution was at version 11.2.2. Newer versions might contain items that are not available in Field Service Mobile. While it's possible to create and modify Field Service projects using a higher version, it's possible for you to add features that are not available. For this reason, it's recommended that you use, or at least publish to, version 11.1.1 of the solution when deploying mobile projects.

You can download the Resco Woodford solution version needed for your organization from the [Resco Woodford Overview](https://www.resco.net/mobilecrm/woodford.html) page.

When you access the site, the solution version will likely be using the most current version. If you would rather use a previous version of the solution, select the **Woodford version history** link on the page. This will display a list of all the previous versions of the solution. You can select the specific version you want to use. *REMEMBER: It's recommended that you are using at least version 11.1.1.* To download the Woodford managed solution that can be used with a Dynamics 365 instance, select  **Download for 2013, 2015, and 2016**.

### Importing the Woodford solution

After the solution have been downloaded, it can be imported into your Dynamics 365 environment.

To import the solution, navigate to **Settings** \> **Solutions**, and select the import button. Be sure to select the Woodford solution (ex. Woodford\_11\_1\_1\_1\_managed) and follow the prompts on the import solution page to finish deploying the solution. Once the solution has been installed, you can view the solution and version number by going to **Settings** \> **Solutions.**

After the solution is imported, you'll see the following items have been added to your Dynamics 365 instance under settings:

- **Woodford:** The customization tool that is used to customize and deploy mobile projects
- **Mobile Auditing:** Provides access to auditing tools and features.

Depending on the version of the solution you deployed, additional items like inspections, and location tracking might be displayed as well.

### Using the Standalone Editor

The easiest way to create and publish mobile projects is to use the Resco Woodford standalone editor. The standalone editor is a desktop application that is installed on a client machine and connects to the Dynamics 365 instance that has Field Service and the Woodford solution deployed to it.

To download the standalone editor for the most recent version of the Woodford solution, see the [Resco Woodford Overview](http://www.resco.net/mobilecrm/woodford.html) page. You can change to a
previous version by using the **Woodford version history**  link.

When you first launch the editor, you might be asked to increase the quota for the isolated storage area to ensure that no errors are generated. It is recommended that you increase the quota to 500 MB to be safe.

You'll need to connect the editor to the organization where you deployed the Woodford solution, as well as provide the instance URL and user login information. You'll also need to fill out the user registration information before you can use the editor.

> [!Note] 
> When loading the editor, you might be notified that a newer version of the solution is available. Do not to update to the newer version. Updating might prevent the application from opening.

> [!IMPORTANT]
> When using the editor, you must ensure that the solution version of the standalone editor and the Woodford solution version installed in your Dynamics 365 instance are the same. If they do not match, it's possible that the editor will not load correctly, and you won't be able to deploy the solution.

If you experience a problem with opening the editor, do one of the following:
-  Remove the Woodford solution from your Dynamics 365 instance and replace it with the version used by the editor. 
-  Remove the standalone editor and replace it with
the version installed in Dynamics 365.

### Activating Field Service Mobile licenses

Organizations that are using Dynamics 365 for Field Service receive access to Field Service Mobile as part of their licensing. Your organization must submit a request to activate the mobile licenses before users can access the mobile app.

In addition, the Woodford solution is available on a 30-day trial period. To extend this period or restore an environment (or do any work that changes an organization ID), a new activation request must be submitted.

For additional information on activating Field Service Mobile licenses, see [Extend Field Service mobile configuration tool trial] (https://docs.microsoft.com/dynamics365/customer-engagement/field-service/activate-fs-mobile-app-license).

### Importing and setting up mobile projects

After you've deployed the Woodford solution and connected to a Dynamics 365 instance that contains the solution, you'll create mobile projects. A *mobile project* is the file that agents load and access when they use the field service mobile application.

To assist in creating mobile projects, a Field Service project template is provided. The template helps you configure the necessary entities related to Field Service that can be used in the application. You can download the template from the [Mobile Project
Template](https://go.microsoft.com/fwlink/p/?linkid=836310) page.

After downloading a project, you'll import it as a mobile project. Select **Import**, and then select the **CentaurusStoreVersion.woodford** template that you previously downloaded.

When you import a project, you'll need to provide the following information:

- **Type:** Defines the type of user that will be accessing this project. Typically, you'll choose Standard, unless you have the need for external or anonymous users to have access.
- **Name:** Specifies the name of the project
- **Priority:** Defines a numeric priority for the project
- **Roles:** Defines the security roles that will have access to the project. The roles represent the Dynamics 365 security roles that exist in your organization.

![Add Mobile Project Window](../media/MO-Unit4-1.png)
  
> [!Note]
> Dynamics 365 security roles and how they relate to mobile projects will be discussed later.