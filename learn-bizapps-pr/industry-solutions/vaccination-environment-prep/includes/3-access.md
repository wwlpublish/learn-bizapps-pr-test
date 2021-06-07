Insert instructional text hereCurrently, Microsoft Vaccination Management isn't available for everyone and is only accessible to approved partners and customers.

In this exercise, you will be playing the role of a System Administrator and learn to place the request to get the access to deploy MVM Solution in your tenant.

1.  Navigate to [https://admin.Microsoft.com](https://admin.microsoft.com/) -\> Groups-\>Active Groups

2.  Click on "Add a group".

![Graphical user interface, application, Teams Description automatically generated](media/image1.png){width="6.618239282589676in" height="3.886509186351706in"}

3.  Select "Security" and click on "Next"

![Graphical user interface, text, application Description automatically generated](media/image2.png){width="7.3in" height="3.698611111111111in"}

4.  Provide a name and description, click on "Next" and then click on "Create group".

![Graphical user interface, text, application, email Description automatically generated](media/image3.png){width="7.075734908136483in" height="4.0445811461067365in"}

5.  Follow the instructions [in this article](https://docs.microsoft.com/en-us/microsoft-365/admin/create-groups/create-groups?view=o365-worldwide#add-members-to-the-group) to add yourself/ other users into the security group. The users in this group will only be able to deploy MVM in an environment. So, make sure that the user created in Exercise 1-\>Task 1 is part of this group.

6.  Navigate to [https://portal.azure.com](https://portal.azure.com/) with the same credentials and follow the instructions listed [in this article](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-how-to-find-tenant#find-tenant-id-through-the-azure-portal) to retrieve the Tenant ID which you will be using in the later steps.

7.  In Azure portal, click on **Groups.**

![Graphical user interface, text, application, email Description automatically generated](media/image4.png){width="7.3in" height="2.404861111111111in"}

8.  Copy the Object Id of the newly created Security Group.

![Graphical user interface, text, application Description automatically generated](media/image5.png){width="7.3in" height="2.3194444444444446in"}

9.  Navigate to https://aka.ms/MVMAccess and fill the required details to add your Tenant and Security Group to the allow-list. \[Note: It may take 3 business days to add your organization's tenant and security group\]

![Graphical user interface, text, application, email Description automatically generated](media/image6.png){width="3.741557305336833in" height="5.5526312335958in"}

Microsoft will evaluate your request and approve your request if your organization is in the approved list. In the meanwhile, you can proceed with Tasks 1 and 2 in the next exercise.