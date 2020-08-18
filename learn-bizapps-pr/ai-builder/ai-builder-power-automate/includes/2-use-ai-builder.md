This section describes various use cases that can be fulfilled by using AI Builder and Power Automate.

## Invoice processing

Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person. Processing these documents and manually entering them into your database can take considerable time. This process can be greatly improved by:

- Using the **AI Builder form processing** model to extract the fields and tables from your documents.

- Creating a Power Automate flow to automatically move information into your database.

## Analyze email sentiment

Employees might want to process emails according to their overall sentiment, for example:

-   If my boss is angry, I'd like to know the purpose right now.

-   If my customer is not satisfied, I need to answer immediately to avoid generating more frustration.

-   After sharing a document, I want to track the positive and negative feedback.

AI Builder allows you to analyze overall sentiment of a text and even the sentiment of each sentence. By using a Power Automate flow, you can apply the **AI Builder sentiment analysis** model on receipt of an email and be notified of the sentiment of important emails to you.

You can also combine the sentiment analysis with key phrase detection by using the **AI Builder key phrase extraction** model.

## Dematerialize documents

Companies can have multiple sites in which some key information is still entered on paper form. Afterward, an agent will manually enter the form content into a centralized tool.

This process can be improved by using Power Automate and AI Builder in the following ways:

-   The agent takes a picture of each audit record and saves it in a folder.

-   A Power Automate flow processes all new pictures in the folder, sends them to your **AI Builder text recognition** model to extract the forms' information, and then saves them in the centralized tool.

Similar processes could be used to record business cards at scale by using the **AI Builder business card reader** model.

## Filter support requests by language 

Typically, support teams receive numerous requests from customers worldwide. The team in charge of a request can vary, depending on the language. Therefore, it's important to detect language as quickly as possible to redirect requests to the relevant teams.

To solve this use case, you can build a Power Automate flow that:

-   Checks for the language of a received email by using the **AI Builder language detection** model.

-   Routes the email into the mailbox of the team in charge, depending on the language that is detected.

## Categorize feedback

A public-facing company might need to categorize feedback that they receive for more relevant processing. For example, a hotel might need to know if feedback targets check-in, rooms, staff, or restaurant.

A company as such can fulfill this scenario by creating a flow that would perform these two actions:

- Get new feedback:

    - Power Automate gets data directly from external sources, for example, new messages on Twitter. A flow could be triggered on tweets that mention the company name.

    - Power Automate gets data from an aggregated data source, for example, an entity in Common Data Service. A flow could be triggered on new record creation.

- Categorize the feedback by using the **AI Builder category classification model**.
