In this unit, you will

-   Develop a simple flow with Power Automate that leverages AI Builder key phrase extraction

**Let's build a Power Automate flow that checks for key phrases in a message when you get a new message in a Yammer group. The sentiment is then sent as a push notification to our mobile flow app. See also [Create a flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow))**

**The prerequisites are:**

-   **CDS (common data service)**

-   **Microsoft** **Excel**

**Create a flow that extracts key phrases**

Power Automate has connectors to many different services, including Yammer. Let's create a flow that automatically stores key phrases to an Excel file for each message that arrives in your Yammer group.

1.  Sign in to [Power Automate](https://ms.flow.microsoft.com/).

2.  Select **My flows**.

3.  Select **New** \> **Automated--from blank**

4.  Search for Yammer in "Choose your flow's trigger" field and then choose **When there is a new message in a group.** If you do not have a Yammer account, you could choose "When a new email arrives" as your flow's trigger. 

5.  Select **Create**.

6.  Select the Yammer group you want to use for Key phrase extraction.

7.  Select **Add an action**, and then select **Predict** under **Actions.**

8.  Select

    -   **Model: KeyphraseExtraction model**

    -   **Text: Message Body Text**

    -   **Language: Two-letter abbreviation for your language**

9. Add a new action: **Add a row into a table** from Excel connector. Select your previously saved Excel file, and the table that you want to update with key phrases.

10. In the **Select an output form previous steps** field, enter **Key phrases** **results**

11.  Select **Save** to save and test the flow.

12. To change the flow, select **Edit flow**.

Now, when a new message on a yammer channel arrives, the Excel file will automatically update with key phrases from the message.

**You have successfully learned how to leverage AI Builder Sentiment Analysis using Power Automate Template.**