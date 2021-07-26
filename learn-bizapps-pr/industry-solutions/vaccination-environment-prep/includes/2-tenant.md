To deploy Microsoft Vaccination Management in a Dataverse environment, you need to add a tenant and the prerequisite licenses.

In this exercise, you will be playing the role of a system administrator and will learn how to create a demo tenant along with the required trial licenses. You can skip this exercise if you have already created a demo tenant and added the trial licenses.

### Task 1: Create a demo tenant

In this task, you will learn how to create a demo tenant along with the required Microsoft Dynamics 365 and Microsoft Power Apps trial licenses. You can skip this task if you already have a tenant.

1.  Open an internet browser in **In-Private** or **Incognito** mode.

2.  Go to <https://trials.dynamics.com>.

    > [!div class="mx-imgBorder"]
    > [![Setup page for creating a Dynamics 365 trial.](../media/1-trial.png)](../media/1-trial.png)

3. Select Try for free in the Dynamics 365 Sales card.  A pop-up window will appear, asking you to enter your email to start your free trial. Leave the Email ID field blank and select **Start your free trial**. 

    > [!div class="mx-imgBorder"]
    > [![Pop-up window asking if you are a partner or a Microsoft employee.](../media/2-partner.png)](../media/2-partner.png)

4. That will show an error asking to provide a valid work or school email ID with a link below to click to set up a new trial account instead. Select the **Click here** to set up a new trial account instead.

5. This will lead to a new account creation flow. In the next page, enter your Email address.

    > [!div class="mx-imgBorder"]
    > [![Selecting Set up account from the trial.](../media/3-account.png)](../media/3-account.png)

6. If the email is already using other Microsoft Services, it will throw the following warning.

    > [!div class="mx-imgBorder"]
    > [![Provide a phone number where you can receive a text message or be called with a verification code to prove that you are not a robot.](../media/4-contact.png)](../media/4-contact.png)

7. Select **Create a new account instead**. It will open the following page. Provide the necessary information. Enter a valid phone number where you can receive text message to validate the sign-up process.  

    > [!div class="mx-imgBorder"]
    > [![Screenshot of code verification for the trial.](../media/5-code.png)](../media/5-code.png)

8. Once the verification completes, request a valid domain name and Check Availability.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of validating the domain name.](../media/6-identity.png)](../media/6-identity.png)

9. Set up a username and password and sign-up.
    
    > [!div class="mx-imgBorder"]
    > [![Set up a User ID and password in your new domain and then select Sign up.](../media/7-plan.png)](../media/7-plan.png)

10. Your Microsoft 365 tenant has been successfully created along with the Dynamics 365 Customer Engagement Plan license that includes a Power Apps license as well.

    > [!div class="mx-imgBorder"]
    > [![Sreenshot of trial set up being completed for the license.](../media/7-finalize-trial.png)](../media/7-finalize-trial.png)

11. Select Get Started. This will open the Power Platform Admin Center where you will create a **New Environment** on which the Microsoft Vaccination Management applications will be installed later. Select a valid name for the Environment.  

    >[!NOTE] 
    > Select United States - Default for region. As of current state, Microsoft Vaccination Management is only available in United States region. 

12.	For **Enable Dynamics 365 apps**, select No. This will ensure no Dynamics 365 applications are installed on the Dataverse Environment. Subsequently only Microsoft Vaccination Management applications will be installed. 

13. Select **Save**.

### Task 2: Add prerequisite licenses

In this task, you will learn how to add the other trial licenses (Office 365 E5 for sending/receiving emails and Power BI Pro to deploy and view the Microsoft Vaccination Management dashboards) that are required for you to complete the labs.

1.  Go to <https://admin.microsoft.com> and sign in with the credentials that you created in **Task 1**.

2.  Select **Purchase services** on the left pane and then search for **Office 365 E5** in the **Office 365** category. Select **Details** on Office 365 E5.

    > [!div class="mx-imgBorder"]
    > [![Sreenshot of selecting Purchase services in the trial.](../media/8-service.png)](../media/8-service.png)

3.  Select **Start free trial**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of selecting the trial subscription.](../media/9-start-trial.png)](../media/9-start-trial.png)

4.  Provide the same phone number that you used while creating the tenant.

    > [!div class="mx-imgBorder"]
    > [![Screenshot to enter a code to prove that you are not a robot.](../media/10-verification.png)](../media/10-verification.png)

5.  Provide the code and select **Start your free trial**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot to enter verification code for the trial.](../media/11-verify-code.png)](../media/11-verify-code.png)

6.  Select **Try now** and then **Continue** to check out the free trial order.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the check out process for the trial.](../media/12-check-out.png)](../media/12-check-out.png)

7.  Go to the **Microsoft 365 admin center** page, select **Purchase services** on the left pane and then search for **Power BI Pro** in the **Power BI** category. Select **Details** on **Power BI Pro**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the selection of Power BI.](../media/13-power-bi.png)](../media/13-power-bi.png)

8.  Select **Start free trial**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the final selection for Power BI.](../media/14-power-bi-trial.png)](../media/14-power-bi-trial.png)

9.  Select **Try now** and then **Continue** to check out the free trial order.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Check out screen to confirm your free trial order.](../media/15-check-out.png)](../media/15-check-out.png)

You have now added Office 365 E5 and Power BI Pro trial licenses. Now, you can assign the new licenses to the required users in the tenant.
