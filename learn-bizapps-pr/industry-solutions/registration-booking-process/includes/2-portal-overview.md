In this exercise, you will assume the persona of a public user who is looking to register for vaccination via the Vaccine Management Portal. You will learn how to browse to the portal, become familiar with the eligibility questions, and understand the registration process.

## Task 1: Navigate to portal and register for vaccination

1.  Launch in-private/incognito mode in your browser and navigate to [Power Apps](https://make.preview.powerapps.com/?azure-portal=true) using the user credentials shared by your coach.

1.  Select your allocated environment from the list of environments in the dropdown.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the environments dropdown list.](../media/environments.png)](../media/environments.png#lightbox)

1.  Navigate to **Apps** and locate **Registration and Booking portal** and click on ellipsis, then **Browse**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the registration and booking portal app with browse highlighted.](../media/registration-booking-portal.png)](../media/registration-booking-portal.png#lightbox)

1.  The portal launches in another tab. Click on **Start registration** button to begin the registration process.

	Alternately, you can also enter the Event code in the textbox below and then click on **Start registration** button. For steps to generate an event code, go to Bonus Exercise 1. The overall registration process remains same irrespective of the option you choose.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the start registration button to begin the process.](../media/start-registration.png)](../media/start-registration.png#lightbox)

1.  Select the responses to the eligibility questionnaire as shown in the screenshots and click on **Next**.

	Have you received the first dose of the COVID-19 vaccine? : **No**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the vaccine history window with first dose question.](../media/vaccine-history.png)](../media/vaccine-history.png#lightbox)

	Alternately, you can also select **Yes** for above question if you have already taken the dose 1 and set values shown below and click **Next**

	> [!NOTE]
	> You can either do step 5 or step 6 and click on **Next**.

	Have you received the first dose of the COVID-19 vaccine? : **Yes**

	Did we administer that dose: **Any option No/Yes**

	What was the date of your first dose? : **Any date in past**

	What was the vaccine type? : **Choose any from list**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of vaccine history with additional questions if first dose has been received.](../media/vaccine-history-2.png)](../media/vaccine-history-2.png#lightbox)

1.  Select Yes only for the below question and default pre-selected responses for others and click **Next**

	Are you currently employed as a healthcare worker? : **Yes**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the vaccine phase qualifications window.](../media/qualifications.png)](../media/qualifications.png#lightbox)

1.  Select default pre-selected responses and click **Next**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the pre-existing health conditions window.](../media/health-conditions.png)](../media/health-conditions.png#lightbox)

1.  Select default pre-selected responses and click **Next**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the covid-19 exposure and vaccine reaction window.](../media/exposure-reactions.png)](../media/exposure-reactions.png#lightbox)

1. At this step, you will create **three** new residents records that we will book as appointments for today. Fill out the following values fields and ensure the **email address** is a valid one so that you can receive booking notifications and take action on the next steps.

    **Resident One**:

	1.  **First Name**: Madison

    1. **Last Name**: Butler

    1. **Race**: Asian

    1. **Ethnicity**: Not Hispanic or Latino

    1.  **Gender**: Female

    1. **Date of Birth**: February 01, 1967 *Make a note of this value and keep for reference. This will be required in later exercises.

    1. **Street Address**: 123 23rd Street

    1. **City**: Redmond

    1. **County:** King

    1.  **State/Province**: WA/Washington

    1. **Zip/Postal Code**: 98052

    1. **Country**: USA

		> [!div class="mx-imgBorder"]
		> [![Screenshot of the personal contact information window.](../media/contact-information.png)](../media/contact-information.png#lightbox)

	1.  **Email Address**: Your valid email address (This is important and needs to be a valid email.)
		
	1. **Confirm Email Address** : Same as above email address
		
	1. **Primary Phone**: can be left blank
		
	1. **Special Assistance** : can be left blank

1. Click **Next**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the personal contact information window with next button.](../media/contact-information-2.png)](../media/contact-information-2.png#lightbox)

1. On the next page, review the summary screen and select the checkbox for **I certify that the information I've provided is true to the best of my knowledge** and click **Complete registration**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the complete registration window with certification of information provided.](../media/complete-registration.png)](../media/complete-registration.png#lightbox)

1. You should now see the following screen completing your registration for the vaccine.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the successful registration message.](../media/success-message.png)](../media/success-message.png#lightbox)

1. **Repeat** **Steps** **10 - 13** to create more registrations for **two** more residents:

    **Resident Two**:

    1. **First Name**: Christopher

    1. **Last Name**: Reed

    1. **Race**: Black or African American

    1. **Ethnicity**: Not Hispanic or Latino

    1. **Gender**: Male

    1. **Date of Birth**: March 01, 1967

    1. **Street Address**: 456 23^rd^ Street

    1. **City**: Redmond

    1. **County:** King

    1. **State/Province**: WA

    1. **Zip/Postal Code**: 98052

    1. **Country**: USA

    1. **Email Address**: Your email address

    **Resident Three**:

    1. **First Name**: Kayla

    1. **Last Name**: Lewis

    1. **Race**: White

    1. **Ethnicity**: Hispanic or Latino

    1. **Gender**: Female

    1. **Date of Birth**: April 01, 1978

    1. **Street Address**: 789 23^rd^ Street

    1. **City**: Redmond

    1. **County:** King

    1. **State/Province**: WA

    1. **Zip/Postal Code**: 98052

    1. **Country**: USA

    1. **Email Address**: Your email address

## Task 2: Verify Dataverse records created post registration process

In this task, you will assume the persona of a system user/administrator and login to the Dataverse environment and view the records that are created/edited post the registration process.

1.  Launch in-private/incognito mode in your browser and navigate to 'make.powerapps.com' using the user credentials shared by your coach.

1.  Select your allocated environment from the list of environments in the dropdown.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the environments list with dropdown menu.](../media/environments.png)](../media/environments.png#lightbox)

1.  Navigate to **Apps** and locate **Vaccination site management app** and click on '...' , then **Play**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the play feature for vaccination site management app.](../media/play.png)](../media/play.png#lightbox)

1.  The Vaccination Site Management app launches in the next tab. Navigate to **Change area** in the navigation panel and click on it to set to **Registration**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the change area in the navigation panel with registration option.](../media/registration.png)](../media/registration.png#lightbox)

1.  The default view will load to **Active Covid Vaccine Eligibilities**. You can select view your **Vaccine Eligibility record** created as a result of your registration steps on the portal.

1. Open your Vaccine Eligibility record and click on all tabs highlighted below - **General, Risk Factors** and **Covid History**. You can note the values you entered during the registration process reflect in the **COVID Vaccine Eligibility** record.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the vaccine eligibility record with general, risk factors, and covid history tabs.](../media/tabs.png)](../media/tabs.png#lightbox)

1.  Make a note of the 'Phase' showing up on the **COVID Vaccine Eligibility** record. This will be used in the subsequent exercise. For example, in the below screenshot, it shows up as **Phase 1. **

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the phase noted on the covid vaccine eligibility record.](../media/phase-1.png)](../media/phase-1.png#lightbox)

1.  Now click on **Related** tab and select **Vaccine Recommendations**. You will not see any **Vaccine Recommendation** record tagged to your **COVID Vaccine Eligibility** record. It will get created in the subsequent exercises.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the vaccine recommendations tab with no results displayed.](../media/recommendations.png)](../media/recommendations.png#lightbox)

**Congratulations!** You have now completed your vaccine eligibility process and verified how it manifests in Dataverse. Now that you are eligible, you can move on to book your appointment for the vaccination in the next exercises.

