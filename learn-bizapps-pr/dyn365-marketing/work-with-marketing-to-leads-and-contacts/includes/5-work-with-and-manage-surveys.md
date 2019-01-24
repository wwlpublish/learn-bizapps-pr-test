Dynamics 365 includes a surveys app that you can use to send surveys to capture feedback about your products or services. These surveys can be integrated into your events, emails, and customer journeys.

In the current version of Dynamics 365, surveys are provided as a separate application, but still operates on the same database as your Dynamics 365 Customer Engagement application. The survey application has access to the same records such as your contacts and accounts, and the surveys you design will be available for other marketing features.
The survey responses are stored in Dynamics 365 for Customer Engagement,
providing availability for both sales and marketing to review analytics.

Use the app-selector menu to switch between Surveys and your other
Dynamics 365 apps.

!![Create Survey](../media/wwm-createandmanagesurveys-1.png)

### Create a theme and upload images

Before to creating a new survey, you might want to create a color theme
matching your company's brand. In Dynamics 365, you can create and store
multiple themes and apply them to different surveys. You might also want
to upload images prior to building any surveys. After an image is
uploaded, you can reuse it in multiple surveys.

To create a survey theme:

1.  Go to **Surveys** from the app-selector
2.  Go to **Marketing > Voice of the Customer > Themes** under  **Collateral**
3.  To create a new theme, select **New**
4.  Enter the name of the theme
5.  Adjust the color of the elements on a survey page by specifying hue, saturation, and lightness.
6.  Select **Save**

To an upload an image into Voice of the Customer:

1.  Go to **Voice of the Customer > Images**
2.  Select **New**
3.  Under **General,** enter values in the Name, Image Title, and  Alternative Text fields
4.  Select **Save** to save the record so you can upload an image and add other information
5.  Under **Custom Icon**, in the Upload your image to remote server field, select Choose File, and then select the image you want to upload
6.  Select **Submit**
7.  In the **Image Format field**, select the format of the image that you uploaded to preview it. You can select from .gif, .jpg, and .png
8.  Select **Save** in the lower-right corner of the screen. Enter the following details, and then select **Add**

After creating a theme and uploading images for your survey, you can start creating your Voice of the Customer survey

### Survey question types

There a variety of question types to help you build detailed and effective surveys. Refer to the [decide the question type](https://docs.microsoft.com/dynamics365/customer-engagement/voice-of-customer/plan-survey#decide-the-question-type) documentation for a full list of question types.

### Create a survey

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2NFze]

### Configure responsive routing

When you want to ask additional questions based on a response in a survey, you can create one or more response routing rules. For example, if you ask the question "How likely is it that you would recommend us to
a friend?", you can create a response routing rule to ask the reason why if someone responds, "Not likely."

Refer to [Design an advanced survey](https://docs.microsoft.com/dynamics365/customer-engagement/voice-of-customer/design-advanced-survey#design-interactive-surveys-by-using-response-routing) for details on configuring responsive routing rules.

### Clone, import, and translate surveys

You can reuse existing questions and sections to avoid creating the same questions multiple times for different surveys. Additionally, after creating a survey, you can translate it into other languages as required by your respondents.

To clone a survey means you are creating an exact duplicate survey where only the name is different. The new survey is created with an integer appended to the survey name. The cloned survey will be in Draft status. The questions are separate from the first survey, and any changes to one survey will not be reflected in the other survey.

To clone a survey:

1.  Go to **Voice of the Customer > Surveys**
2.  Select the name of the survey that you want to clone
3.  On the toolbar, select **Clone** 

You can also import a survey by creating the survey in one environment, testing it, and then moving it to the production environment.

To import a survey from an existing environment:

1.  Go to **Voice of the Customer > Surveys**
2.  Select the name of the survey you want to move to another environment
3.  Select the survey XML file under the **Notes** section and save it to the location you want
4.  Then, sign in to the Dynamics 365 environment to which you want to move the survey
5.  Go to **Settings > Voice of the Customer Imports**
6.  Select **New**
7.  Enter information in the **General** area. If you want additional information, point to any field to read the tooltip
8.  To overwrite the existing survey, select Yes in the Overwrite Survey field. If you select No, a copy of the survey is created
9.  In the **Survey Xml To Import** field, paste the **survey XML**
10. Select **Save** in the lower-right corner of the screen. The survey is imported and available at **Voice of the Customer > Survey**

After creating a survey, you can **translate** it into other languages as required by your respondents.
