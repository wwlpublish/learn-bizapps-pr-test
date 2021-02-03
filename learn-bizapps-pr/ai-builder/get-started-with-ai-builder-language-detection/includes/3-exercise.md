In this exercise, you will build a Power Automate flow that checks for the language of an email and then routes it to a specific email inbox. For more information, see the Create a flow in Power Automate documentation.

The prerequisite for this exercise is to have Microsoft Dataverse in the environment where you are building your flow.

## Create a flow that detects language and routes to a specific inbox

To create a flow that detects language of an email and then routes it to a specific email inbox, follow these steps:

1. Sign in to Power Automate.

2. Select **Create** from the left navigation bar and then select **Automated flow**.

3. Pick a name for your flow and then select **When a new email arrives** as your flow's trigger.

    ![The Flow name is "Route emails according to Language using A I Builder. Under Choose your flow's trigger, "When a new email arrives" is selected.](../media/image1.png)

4. Select **Create** and then **New Step**.

5. Search for the **Predict** action and then select it.

    ![Under Choose an action, search results for "predict" appear in the Actions tab.](../media/image2.png)

6. Select **LanguageDetection model** from the **Model** drop-down menu, and then select **Body** (or **Body** and **Subject**) from the dynamic content from previous steps.

    ![On the Predict step, Model is set to LanguageDetection model, and Text value is set to Body. You can insert parameters from previous steps.](../media/image3.png)

7. Select **New Step** and search for **Condition Control**.

    ![Under Choose an action, search results show the Condition Control.](../media/image4.png)

8. Select **Response Results Language** in the **Select output from previous steps** field.

    ![Under Apply to each, Select an output from previous steps allows you to select Response Results Language.](../media/image5.png)

9. Select **Condition** and then enter **FR** (for French), **EN** (for English), **DE** (for German), and so on, to select what language you want to route to a particular email.

    ![Under Condition, select Response is equal to FR.](../media/image6.png)

10. Scroll down the page and, under the **If yes** condition, add the **Send an email** action. Select a trigger according to your preferred email provider.

    ![Under If yes, Choose an action, the search results for send an email appear in the Actions tab.](../media/image7.png)

11. Customize the **To**, **Subject**, and **Body** fields by using dynamic content, such as the content shown in the following image.

    ![Under If yes, Send an email (V2), the To, Subject, and Body fields are filled in with parameters from previous steps.](../media/image8.png)

12. Select **Save** and test the flow with a sample email.

13. To change the flow, select **Edit flow**.

Now, when emails arrive in a specified language, they will be sent to the email that is specified in your flow.

You have successfully completed this lesson on how to use AI Builder Language detection in Power Automate.
