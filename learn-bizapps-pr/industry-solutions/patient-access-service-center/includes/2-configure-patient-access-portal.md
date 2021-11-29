In this exercise, you will do the following:

- Configure an external website to display the Healthcare Patient Portal template

- Modify the Healthcare Patient Portal to display the proper company name.

- Create a registration code and invite a patient to create an account for the website

- Log in as the patient to navigate the features of the healthcare portal

The **Healthcare Patient Portal** is a template installed in your environment by the Patient Access module in Microsoft Cloud Solution Center when Microsoft Cloud for Healthcare was deployed.

A **Portal** is an external website that allows for communication between a company and its users. In this case, the Lamna Healthcare Company wants an external website for their patients to access their medical history and communicate effectively with the institution. The Healthcare Patient Portal template tailors the website's user interface for a healthcare company focusing on secure communication, information access, and an overall improved patient experience.

Here's what you will see after configuring and logging into the Healthcare Patient Portal:

> [!div class="mx-imgBorder"]
> [![Screenshot of the Healthcare Patient Portal welcome page.](../media/2-patient-portal.png)](../media/2-patient-portal.png#lightbox)

Learn more about Portals on Microsoft Docs [here](/en-us/powerapps/maker/portals/?azure-portal=true#).

### Task 1: Configure the Healthcare Patient Portal

Prior to deploying Microsoft Cloud for Healthcare, you created a portal in your environment using the **Customer Self-Service** template. This was a prerequisite to deploy the Patient Access module.

Lamna Healthcare wants to associate the previously installed Customer Self-Service portal with the **Healthcare Patient Portal** template, so the correct website is displayed to the user. The following steps will guide you through how to bind your website to the proper template and restart the portal for changes to apply.

We will first open the Portal to show the Customer Self-Service template currently bound. After the configuration steps in this task, you will see the new Healthcare Patient Portal user interface.

1. Using an In-Private or Incognito window, navigate to [http://make.powerapps.com](http://make.powerapps.com/?azure-portal=true).

1. Select the correct environment from the upper right **Environment** drop-down.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Environment horizontal navigation bar.](../media/3-environment-drop-down.png)](../media/3-environment-drop-down.png#lightbox)

1. Select **Apps** on the left navigation bar.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the left navigation bar with the Apps option highlighted.](../media/1-apps.png)](../media/1-apps.png#lightbox)

1. Find the **Healthcare Patient Portal** you created. It should be the only app where Type is Portal. You can also search for it in the Search bar in the upper right corner

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the newly created Healthcare Patient Portal.](../media/4-healthcare-patient-portal.png)](../media/4-healthcare-patient-portal.png#lightbox)

1. Select the app name to **open** the **Healthcare Patient Portal**. You may also select More Commands (...) > Browse or select Browse on the top command bar to open it.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Healthcare Patient Portal app option selected and More Commands menu highlighted.](../media/5-open-portal.png)](../media/5-open-portal.png#lightbox)

1. You should see the **Customer Self-Service template** shown in the Healthcare Patient Portal.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Customer Self-Service template in the Healthcare Patient Portal.](../media/6-self-service.png)](../media/6-self-service.png#lightbox)

1. **Close** the Healthcare Patient Portal website. Now you'll configure it to the Healthcare Patient Portal template.

1. Return to the Power Apps screen in the Apps section. Select the **Healthcare Patient Portal** app if it isn't already selected.

1. Select **More Commands (...)** > **Settings** or select Settings on the top command bar. This will bring out the **Portal settings** panel on the right.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Portal settings right side panel menu.](../media/7-settings.png)](../media/7-settings.png#lightbox)

1. In **Portal settings**, under **Advanced options**, select **Administration**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Advanced options available in Portal settings.](../media/8-advanced-options.png)](../media/8-advanced-options.png#lightbox)

1. Selecting Administration will open a new window, the **Power Apps Portals admin center,** where you can do portal administrative tasks.

1. You should be landed in the **Portal Details** tab of the Power Apps Portals admin center**.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps portal details area of the administrative center](../media/9-portal-details.png)](../media/9-portal-details.png#lightbox)

1. Scroll down to **Update Portal Binding >** **Select** **Website Record**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Update Portal Binding with the Customer Self-Service option selected.](../media/10-website-record.png)](../media/10-website-record.png#lightbox)

1. Open the **Select Website Record** drop-down and change the current value (Customer Self-Service) to **Healthcare Patient Portal.** This will bind the Healthcare Patient Portal template with this portal URL and show the proper user interface to the user.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Select Website record options with Healthcare Patient Portal selected.](../media/11-select-website-record.png)](../media/11-select-website-record.png#lightbox)

1. Select **Update**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Healthcare Patient Portal option selected, Portal State set to On and the Update button selected.](../media/12-update.png)](../media/12-update.png#lightbox)

1. Select **Portal Actions** section on the left navigation. Then select **Restart.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps portals administration center with the Portal Actions options selected in the left navigation pane.](../media/13-portal-actions-restart.png)](../media/13-portal-actions-restart.png#lightbox)

1. When prompted, confirm the **Restart** for the portal. This will allow the change to take effect.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a message advising that restarting the portal will make it unavailable for several minutes with a prompt to select the Restart button.](../media/14-restart.png)](../media/14-restart.png#lightbox)

1. Wait 1-5 minutes for the portal to restart. (Feel free to refill water or stretch your legs!)

1. Navigate back to the Healthcare Patient Portal in [http://make.powerapps.com](http://make.powerapps.com/?azure-portal=true).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Lamna Healthcare Patient Portal in App list.](../media/15-power-apps.png)](../media/15-power-apps.png#lightbox)

1. If you see the following error, the portal is still restarting.
    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Service Unavailable 503 error.](../media/16-service-unavailable.png)](../media/16-service-unavailable.png#lightbox)

1. Once the Portal is opened and running properly, it should look like the following:

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Patient Access Portal sign in page with the Healthcare Patient Portal template configured.](../media/17-secure-sign.png)](../media/17-secure-sign.png#lightbox)

**Congratulations!** You completed the post deployment step to configure the Healthcare Patient Portal template deployed from Patient Access. After updating the bindings and restarting the portal, the website now shows as Healthcare Patient Portal template rather than Customer Self-Service.

### Task 2: Modify Company Name in Patient Portal

In this task, we will edit the Patient Portal website to align the name with Lamna Healthcare Company since the template uses a generic company name.

1. Navigate to **Apps** in [http://make.powerapps.com](http://make.powerapps.com/?azure-portal=true).

1. Select the **Healthcare Patient Portal** app and click **More Commands (...) >** **Edit**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Healthcare Patient Portal More Commands menu expanded.](../media/18-more-commands.png)](../media/18-more-commands.png#lightbox)

1. The Patient Portal designer will load after getting thing ready.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Patient Portal loading screen with the words Getting Things Ready.](../media/19-getting-ready.png)](../media/19-getting-ready.png#lightbox)

1. Once loaded, you should see **Contoso Healthcare** in the upper left of the design screen. The name may be overlapping the logo but will display properly on the website.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the design screen with the Contoso Healthcare logo.](../media/20-contoso-healthcare.png)](../media/20-contoso-healthcare.png#lightbox)

1. Select the text box that reads Contoso Healthcare and change it to **Lamna Healthcare**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a text box highlighted with the words Lamna Healthcare included.](../media/21-lamna-healthcare.png)](../media/21-lamna-healthcare.png#lightbox)

1. The page should automatically save the changes. You can verify in the command bar that it says **Saved**, has the green check mark, and on hover shows the correct saved time.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Saved button in the upper right corner of the page and the message indicating it was last saved 11 seconds ago.](../media/22-saved.png)](../media/22-saved.png#lightbox)

1. Select **Sync Configurations** in the command bar to sync data to CDS.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the command bar with the Sync configuration option highlighted.](../media/23-sync-configuration.png)](../media/23-sync-configuration.png#lightbox)

1. It may take a moment to load the preview.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a loading screen with the words Sync in progress.](../media/24-sync-progress.png)](../media/24-sync-progress.png#lightbox)

1. Once configurations are completed syncing, select **Browse website** on the command bar.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the command bar with the Browse website option highlighted.](../media/25-browse-website.png)](../media/25-browse-website.png#lightbox)

1. The Healthcare Patient Portal should open, and you should see the **Lamna Healthcare** company name in the upper left corner.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Healthcare Patient portal welcome page with the Lamna Healthcare logo in the upper left corner.](../media/26-lamna-secure.png)](../media/26-lamna-secure.png#lightbox)

**Congratulations!** You completed modifying the Healthcare Patient Portal to display the correct company name.

### Task 3: Invite a patient to the Portal

Now that the Patient Portal is ready to go, we need to allow Lamna Healthcare patients to create accounts.

In this task, you will learn how to **create an invitation code** for patients to sign up and use the Healthcare Patient Portal. Since **Casey Jensen** will be accessing the patient portal to fill her medication in this lab, we will create an account for her.

1. Open the **Healthcare Administration** app in [http://make.powerapps.com](http://make.powerapps.com/?azure-portal=true).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps list of apps with the Healthcare Administration option highlighted.](../media/27-healthcare-administration.png)](../media/27-healthcare-administration.png#lightbox)

1. In the Administration section of the sitemap, select **People**. You will see the **Active Patients** grid view. Open the **Casey Jensen** patient record so we can obtain an invitation code for her to use.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Healthcare Administration page. The People menu option is selected and a list of Active patients is displayed.](../media/28-active-patients.png)](../media/28-active-patients.png#lightbox)

1. On the Casey Jensen patient record, select **Create Invitation** from the top command bar. It should be near the right side.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a patient record with the Create Invitation menu option selected in the upper right-corner.](../media/29-create-invitation.png)](../media/29-create-invitation.png#lightbox)

1. You may have to expand more options to see this command in the drop-down.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of additional options expanded and the Create Invitation option selected.](../media/30-invitation-drop-down.png)](../media/30-invitation-drop-down.png#lightbox)

1. A **New Invitation** form will appear. You don't need to make any changes. Select **Save.** Once saved, an invitation code will be created for the patient. Let's retrieve it.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Invitation form with the Save option selected.](../media/31-new-invitation.png)](../media/31-new-invitation.png#lightbox)

1. Go to the **Advanced** tab on the Invitation record. Copy and store the **Invitation Code** for accessing the Patient Portal in the next task.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Advanced tab of the Invitation record and the Invitation code.](../media/32-advanced.png)](../media/32-advanced.png#lightbox)

**Congratulations!** You have successfully created an invitation code for Casey to register an account in the Patient Portal.

### Task 4: Redeem invitation code and sign into Patient Portal

In this task, you will **transition personas** and act as Casey, who just received an invitation code to the Healthcare Patient Portal and are excited to register and navigate its features.

1. Navigate back to the **Healthcare Patient Portal** in [http://make.powerapps.com](http://make.powerapps.com/?azure-portal=true).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Lamna Healthcare Patient Portal App list.](../media/4-healthcare-patient-portal.png)](../media/4-healthcare-patient-portal.png#lightbox)

1. In the Patient Portal, select **Sign in**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Patient Portal secure sign in.](../media/33-secure-sign-in.png)](../media/33-secure-sign-in.png#lightbox)

1. After the sign-in page loads, select the **Redeem invitation** tab.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Redeem invitation page with blank fields for Username and Password.](../media/34-redeem-invitation.png)](../media/34-redeem-invitation.png#lightbox)

1. Paste the **Invitation code** you stored for Casey Jensen. Select **Register.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Redeem Invitation page with the Invitation code field populated.](../media/35-invitation-code.png)](../media/35-invitation-code.png#lightbox)

1. Register a new local account for Casey Jensen with the following recommended details:

    a.  **Email**: Casey.Jensen\@contoso.com (should autofill)

    b.  **Username**: CaseyJensen

    c.  **Password**: Make up your own. Note the password to use for sign-in later.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Register tab with fields for Email, Username, Password and Confirm Password.](../media/36-register-account.png)](../media/36-register-account.png#lightbox)

1. Select **Register**. After selecting Register, you should be signed into the Patient Portal.

**Congratulations!** You have successfully redeemed an invitation to register an account for Casey Jensen and signed in.

### Task 5: Navigate the Patient Access Portal

In this task, you will continue as **Casey** and navigate the features of the Patient Portal.

1. After registering an account in the **Patient Access Portal**, you may be welcomed by Casey's profile page on first login. You may also be welcomed by the homepage. If so, continue to step 3.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a sample profile page for Casey Jensen with information and security details.](../media/37-information.png)](../media/37-information.png#lightbox)

1. Select **Lamna Healthcare** company name/logo in the upper left to go to the Homepage.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a sample profile for Casey Jensen with the Lamna Healthcare logo.](../media/38-lamna-logo.png)](../media/38-lamna-logo.png#lightbox)

1. You will be navigated to the Patient Portal **Homepage**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Lamna Healthcare Patient Portal homepage.](../media/39-homepage.png)](../media/39-homepage.png#lightbox)

1. In the center of the homepage, you will see **shortcuts** to **schedule an appointment**, **view messages**, or **find a doctor**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of homepage sections to schedule an appointment, view messages or find a doctor.](../media/40-shortcuts.png)](../media/40-shortcuts.png#lightbox)

1. Below the shortcuts, you will see current patient information including **unread messages**, **upcoming appointments**, and **current medications**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of sample patient information displaying unread messages, upcoming appointments, and current medications.](../media/41-unread-messages.png)](../media/41-unread-messages.png#lightbox)

1. In the left navigation bar, you will see all available options for navigation in the Patient Portal. Select each option to see what's available and each associated screen.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of options available in the left navigation pane.](../media/42-left-navigation.png)](../media/42-left-navigation.png#lightbox)

1. **Home** command will direct you to the homepage.

1. **Find a** **doctor** shows a list of practitioners with associated information.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a list of Physicians names with corresponding City, State, Primary language and Secondary language.](../media/43-find-doctor.png)](../media/43-find-doctor.png#lightbox)

1. **Messages** allows a secure method to send and receive messages to healthcare professionals. Expand Messages on the navigation bar to see both the **Inbox** and **Sent** messages.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the messages inbox with From, Subject, Received and Status fields displayed.](../media/44-messages.png)](../media/44-messages.png#lightbox)

1. Expand **Appointments** to check **upcoming** and **schedule** **new** appointments. Scheduling new appointments allows for **clinic** or **virtual** appointments, which also include instant virtual appointments. The Virtual Visit Lab will go through the process of booking an instant virtual appointment.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the schedule a new appointment page with options to schedule as soon as possible or choose a specific day and time.](../media/45-schedule-appointment.png)](../media/45-schedule-appointment.png#lightbox)

1. Check **Medical records** including **medications**, **allergies**, **conditions, visit summaries**, **care plans**, and **care team**. You can see a full overview and filter by date and type.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Medical records overview page with date filter options and record types listed.](../media/46-overview.png)](../media/46-overview.png#lightbox)

1. Lastly, there is **Personal information**, including **emergency contacts** and insurance **coverages**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of sample emergency contacts and fields for contact Name, Consent Access, Consented Access On and Revoked Access on.](../media/47-emergency-contacts.png)](../media/47-emergency-contacts.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Coverage section with fields for coverage Name, Subscriber ID, Policy Holder name, Coverage End Date and Group Plan.](../media/48-coverage.png)](../media/48-coverage.png#lightbox)

1. The Azure Health Bot icon shows at the lower right-hand corner of the screen. You may start a conversation by clicking **Let's Chat** button to open the virtual assistant.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Let's Chat virtual assistant Health Bot.](../media/49-chat.png)](../media/49-chat.png#lightbox)

1. In the final exercise, we will have a full conversation with the bot, but for now we will close and continue.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of closing the Health Bot conversation.](../media/50-close-chat.png)](../media/50-close-chat.png#lightbox)

1. You may access the patient Profile page at any time by selecting the patient's name in the upper right drop-down and selecting **Profile**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the patient profile page drop-down menu with the Profile option selected.](../media/51-profile.png)](../media/51-profile.png#lightbox)

1. Here you can customize the patient profile as needed. For now, we will keep it the same.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a sample patient profile for Casey Jensen again.](../media/52-customize-profile.png)](../media/52-customize-profile.png#lightbox)

1. You may log out of the Patient Portal by selecting the patient's name in the upper right drop-down and selecting **Sign Out**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of he patient name drop-down menu with Profile and Sign out options.](../media/53-sign-out.png)](../media/53-sign-out.png#lightbox)

1. You should be redirected back to the sign-in page.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Lamna Healthcare patient portal secure sign in page again.](../media/54-secure-redirect.png)](../media/54-secure-redirect.png#lightbox)

**Congratulations!** You have navigated the Patient Portal to see what information and communication is available to the Patient.

In this exercise, you learned how to configure the Patient Access Portal to display as the Healthcare Patient Portal, modify the portal to display the company name, invite patients to register to the website, and navigate the website features.
