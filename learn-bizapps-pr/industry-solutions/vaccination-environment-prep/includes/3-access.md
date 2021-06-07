Insert instructional text hereCurrently, Microsoft Vaccination Management isn't available for everyone and is only accessible to approved partners and customers.

In this exercise, you will be playing the role of a System Administrator and learn to place the request to get the access to deploy MVM Solution in your tenant.

1.  Navigate to [https://admin.Microsoft.com](https://admin.microsoft.com/). Select **Groups** and then select **Active groups**.

2.  Select on **Add a group**.

> [!div class="mx-imgBorder"]
> [![Screenshot of adding a group to your environment.](../media/16-add-group.png)](../media/16-add-group.png)

3.  Select **Security** and select on **Next**.

> [!div class="mx-imgBorder"]
> [![Screenshot of selecting a security role for the group.](../media/17-group-type.png)](../media/17-group-type.png)

4.  Provide a name and description, select **Next** and then select **Create group**.

> [!div class="mx-imgBorder"]
> [![Screenshot of providing a name for the group creation.](../media/18-group-name.png)](../media/18-group-name.png)

5.  Follow the instructions for [create groups](/microsoft-365/admin/create-groups/create-groups?view=o365-worldwide#add-members-to-the-group) to add yourself and other users to the security group. The users in this group will only be able to deploy MVM in an environment. Make sure that the user created in Exercise 1, Task 1 is part of this group.

6.  Navigate to [https://portal.azure.com](https://portal.azure.com/) with the same credentials and follow the instructions for [find tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant#find-tenant-id-through-the-azure-portal) to retrieve the Tenant ID, which you will be using in the later steps.

7.  In Azure portal, select **Groups.**

> [!div class="mx-imgBorder"]
> [![Screenshto of selecting the group for testing.](../media/19-test-overview.png)](..media/19-test-overview.png)

8.  Copy the Object ID of the newly created Security Group.

> [!div class="mx-imgBorder"]
> [![Screenshot of finding the object ID for your group.](../media/20-object-id.png)](../media/20-object-id.png)

9.  Navigate to https://aka.ms/MVMAccess and fill the required details to add your Tenant and Security Group to the allowlist. 

> [!NOTE] It may take three business days to add your organization's tenant and security group.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the request access form.](../media/21-request-access.png)](../media/21-request-access.png)

Microsoft will evaluate your request and approve your request if your organization is in the approved list. In the meanwhile, you can proceed with Tasks 1 and 2 in the next exercise.