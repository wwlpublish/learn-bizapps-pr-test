The Microsoft Vaccination Management Dashboard offers a vaccination management dashboard created in Microsoft Power BI, which enables healthcare program leaders to obtain various insights and establish situational awareness about their vaccination program. They can track cumulative and daily vaccinations, view registrations, bookings and shipments, and monitor KPIs at the site level.

> [!div class="mx-imgBorder"]
> [![Screenshot of vaccination dashboard with data.](../media/1-vaccination.png)](../media/1-vaccination.png)

In this exercise, you will learn how to configure the Microsoft Vaccination Management Dashboard from AppSource, connect to your data, and load the Microsoft Vaccination Management Dashboard in a Power BI (PBI) Online workspace to view the report.

**Task 1: Install Microsoft Vaccination Management Dashboard from Microsoft AppSource**

In this task, you will retrieve the Microsoft Vaccination Management Dashboard from AppSource and configure it in Power BI (PBI) Online where a new workspace and Application will be auto created.

Once MVM is more widely available, you can configure the application directly from Microsoft Cloud Solution Center instead of through AppSource, as seen below.

> [!div class="mx-imgBorder"]
> [![Graphical user interface, text, application Description automatically generated.](../media/2-cloud-center.png)](../media/2-cloud-center.png)

While we are privately available and for this training, you will retrieve the application from AppSource.

1.  Navigate to [Microsoft AppSource](https://appsource.microsoft.com/en-US/). (Incognito/InPrivate mode)

2.  Search Apps for **vaccination** using the top search bar.

    > [!div class="mx-imgBorder"]
    > [![Graphical user interface Description automatically generated with medium confidence.](../media/3-app-source.png)](../media/3-app-source.png)

3.  Select the **Microsoft Vaccination Management Dashboard.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of dashboard app details in app source.](../media/4-dashboard-app.png)](../media/4-dashboard-app.png)

4.  Select **Get it now.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of app source details for vaccination app.](../media/5-get-now.png)](../media/5-get-now.png)

5.  Enter your provided **training user email** if prompted. Select **Sign in**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of sign-in for app on app source to install.](../media/6-sign-in-app.png)](../media/6-sign-in-app.png)

6.  In the prompt, fill in your **training** **user email**, a **dummy phone number**, select **Country/region**, and check the permissions box. 

    > [!NOTE]
    > If you're in an official training, use the email provided to you.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of app contact details for download.](../media/7-app-contact.png)](../media/7-app-contact.png)

7.  Select **Continue**.

8.  Power BI Online will load and prompt to install the Power BI app. Select **Install**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of install of the Power BI app from app source.](../media/8-install-app.png)](../media/8-install-app.png)

9.  The app should begin to install.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing app install as complete.](../media/9-insatll-complete.png)](../media/9-install-complete.png)

10. Once complete, you should see a prompt that your app is ready. Select **Go to app**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing navigation to open the installed app.](../media/10-go-to-app.png)](../media/10-go-to-app.png)

11. If you miss the prompt, you can select **Apps** on the left navigation bar and **Select** your new app.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the app to select in the dashboard.](../media/11-select-app.png)](../media/11-select-app.png)

12. The Microsoft Vaccination Management Dashboard Data Model app will open. Select **Connect** in the center to connect data.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing connection to dashboard app.](../media/12-connect-app.png)](../media/12-connect-app.png)

13. You will be prompted to add **DataverseName** and **UTCZoneOffset.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the command center report.](../media/13-command-report.png)](../media/13-command-report.png)

14. To get the Dataverse name, navigate to [Power Apps](https://make.powerapps.com/) (Incognito or InPrivate session).

15. Log in using the credentials supplied in the training for your user.

16. Select the correct environment from the upper right **Environment** drop-down.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the environment connnection.](../media/14-select-environment.png)](../media/14-select-environment.png)

17. Select **Apps** on the left navigation bar.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the app in the left navigation pane.](../media/15-apps-selection.png)](../media/15-apps-selection.png)

18. Find the **Vaccination site management** **app** and select on the app name.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of vaccination site management app.](../media/16-site-app.png)](../media/16-site-app.png)

19. Once loaded, copy the **URL** ending in **crm.dynamics.com** (don't include https://).

    > [!div class="mx-imgBorder"]
    > [![A screenshot of a computer description automatically generated with medium confidence](../media/17-url.png)](../media/17-url.png)

20. Navigate back to PBI Desktop and paste the **DataverseName** URL (without https:// and trailing /).

21. Add your **UTCZoneOffset**. UTCZoneOffset is the number of hours your local time is offset from UTC. Depending on location, your value may be negative (for example, PT = 8, IST = -5.5).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the timezone setting for the dashboard.](../media/18-command-report.png)](../media/18-command-report.png)

22. Select **Next.**

23. You will be prompted for an Authentication method to connect. Keep OAuth2 selected in the drop-down. Select the **pencil** under **Privacy setting for this data source** to edit.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of authentication method for dashboard.](../media/19-report-connect.png)](../media/19-report-connect.png)

24. For Privacy level setting for this data source, select **Organizational**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the data source connection.](../media/20-privacy.png)](../media/20-privacy.png)

25. Select **Sign in and Continue.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the sign-in process for the dashboard.](../media/21-sign-in-auth.png)]((../media/21-sign-in-auth.png)

26. **Log in** with your training user credentials.

27. You will now see a blank report showing on the screen. This file only contains the Data Model.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the blank dashboard not connected.](../media/22-blank-report.png)](../media/22-blank-report.png)

28. Select the **MVM Command Center Report** on the left site map. The report should load, and you should see the visualizations lit up with the data in your environment.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of vaccination management dashboard.](../media/23-report-detail.png)](../media/23-report-detail.png)

**Congratulations!** You successfully installed the Microsoft Vaccination Management Dashboard from AppSource into a new Power BI workspace in your tenant and connected to your data.

