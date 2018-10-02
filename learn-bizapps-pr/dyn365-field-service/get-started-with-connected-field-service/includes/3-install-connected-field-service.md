## Exercise - Installing Connected Field Service

In this exercise, you will configure your environment, install the Connected Field Service App, and create a deployment.

### Configure Environment

Create a trial or reset an existing test environment and configure it for Field Service.  This installs the Dynamics 365 Field Service application.  From this base deployment you will be adding the Connected Field Service add-on.   Make sure your lab environment has sample data enabled.

It is important that you do not complete these exercises in your production environment.  Always do these labs in a demo or sandbox type instance.

[!Note]
See onboarding options for getting an environment [https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/onboard-your-organization-and-users-to-dynamics-365-online](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/onboard-your-organization-and-users-to-dynamics-365-online "Getting an Environment")

![Environment scenario options](../media/1-gs-unit3.png)

### Install Connected Field Service App

1. Go to your Dynamics 365 org and click Switch to Another App

![Switch Apps](../media/2-gs-unit3.png)

2. Click Get More Apps</li>

![Get more apps](../media/3-gs-unit3.png)

3. Search for Connected Field Service and select it.

![Select Connected Field Service App](../media/4-gs-unit3.png)

4. Click GET IT NOW.

![Get it now button](../media/5-gs-unit3.png)

5. Click Continue.

![Continue button](../media/6-gs-unit3.png)

6. Select the organization and continue.

![Organization selection](../media/7-gs-unit3.png)

7. Click Accept.

![Permission requested accept](../media/8-gs-unit3.png)

8. Read the Terms of Service and click Next.

![Terms of Service](../media/9-gs-unit3.png)

9. Click Next again.

![Next button](../media/10-gs-unit3.png)


## Create Deployment

1. Select your organization and click New Deployment

![New Deployment button](../media/11-gs-unit3.png)

If your Azure Subscription is in the same Azure AD as your Dynamics 365 environment, this step is not required, otherwise if it is in a different environment click Use Different and sign in with those credentials.  After sign-in you should see in the subscription list the correct Azure subscription.

2.	Select Subscription, enter Resource Group name, select your Region, and click Deploy.

![Deploy button](../media/12-gs-unit3.png)

3. Click Show Deployment Status.

![Deployment status button](../media/13-gs-unit3.png)

4. Wait for the deployment to complete, the deployment status will update the progress as it goes.

![Deployment status](../media/14-gs-unit3.png)

5. Confirm the deployment succeeds before you proceed to the next steps.

![Deployment success](../media/15-gs-unit3.png)

6. Click Authorize.

![Authorize button](../media/16-gs-unit3.png)

7. Sign in with your Azure credentials.

8. Click This Connection is Not Authenticated.

![Not authenticated button](../media/17-gs-unit3.png)

9. Click Authorize.

![Authorizebutton](../media/18-gs-unit3.png)

10. Sign in with your Dynamics 365 credentials.

11. Click Save.

![Save button](../media/19-gs-unit3.png)

12.	You have now completed your Connected Field Service installation.  If you would like to have some demo data installed you can download and deploy it from here [https://www.microsoft.com/en-us/download/details.aspx?id=55320](https://www.microsoft.com/en-us/download/details.aspx?id=55320  "Demo Data")  