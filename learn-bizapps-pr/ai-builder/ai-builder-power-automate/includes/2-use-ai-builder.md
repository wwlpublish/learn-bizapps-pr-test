In this section, we'll see some use cases that can be fulfilled using AI Builder and Power Automate.

## Invoice processing

Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person. Processing these documents and manually entering them into your database can take a considerable amount of time. This can be greatly improved by:

-   Using **AI Builder form processing** model to extract the fields and tables from your documents

-   Creating a Power Automate flow to automatically pipe the information into your database

## Analyze email sentiments

Employees may want to process their emails according to their overall sentiment:

-   If my boss is angry, I'd like to know the purpose right now

-   If my customer is not satisfied, I need to answer as soon as possible to avoid generating more frustration

-   After sharing a document, I want to track the positive and negative feedback

AI Builder allows to analyze overall sentiment of a text and even sentiment of each sentence. Using a Power Automate flow, you can apply the **AI Builder sentiment analysis** model upon email reception and be notified of the sentiment of important emails to you.

You can also combine the sentiment analysis with the key phrase detection using **AI Builder key phrase extraction** model.

## Dematerialize documents

Companies can have multiple sites in which some key information is still entered on paper form. Afterward, an agent manually enters the form content into a centralized tool.

This process can be improved using Power Automate and AI Builder:

-   The agent takes a picture of each audit record and saves it in a folder

-   A Power Automate flow processes all new pictures in the folder, sends them to your **AI Builder text recognition** model to extract the forms information, and then saves them in the centralized tool

Same process could be used to record business cards at scale, using the **AI Builder business card reader** model.

## Filter support requests by language 

Support teams usually receive numerous requests from customers worldwide. The team in charge of a request can vary depending on the language. It's therefore important to detect language as quickly as possible to redirect requests to the relevant teams.

To solve this use case, you can build a Power Automate flow that:

-   Checks for the language of an email received using **AI Builder language detection** model

-   Routes the email into the mailbox of the team in charge depending on the language detected

## Categorize feedback

Public facing company may need to categorize feedback they get for more relevant processing. For example, a hotel may need to know if feedback targets check-in, rooms, staff, or restaurant.

Such company can fulfill this scenario by creating a flow that would perform these two actions:

-   Get new feedback:

    -   Power Automate gets data directly from external sources. Example: New messages on Twitter. A flow could be triggered upon tweets, which mentions the company name

    -   Power Automate gets data from an aggregated data source. Example: an entity in Common Data Service. A flow could be triggered upon new record creation

-   Categorize the feedback using **AI Builder category classification model**
