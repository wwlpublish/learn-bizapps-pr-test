Customer journeys enable you to visualize and automate the journey contacts take while interacting with your marketing initiatives. You create flows that help guide your intended audience through a process of automated messaging, activity generation, and interactive decision points.

Within customer journeys, you can create campaigns for lead-nurturing, sales engagement, events, customer onboarding, retention through the established templates provided or create a new journey.

Customer journeys can be simple or complex. An example of a simple journey could be a short interaction, such as a single email. A complex journey could be a multi-faceted campaign that takes customers and leads down unique paths as they interact with your messaging.

## Create a customer journey

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2NPR5] 

### Customer journey reference components

#### Minimum consent

Dynamics 365 for Marketing allows you to request, capture, and store consent of your audience. You can design your marketing activities to respect the consent given. It is important you include relevant information in your marketing content (like landing pages and email marketing message) that unambiguously informs your audience about the data that you collect and the purpose of your processing their information. Your audience must have the option to give consent freely, make an informed decision, and be able to review, update, or revoke consent at any time.

| **Level** | **Consent level name** | **Consent level detail** |
| --------- | ---------------------- | ------------------------ |
|    0      |       (none)           | No consent has been given by the contact. The organization should not reach out to the individual or perform data processing or automated decision making until consent is given. Regardless of the given consent, individuals can submit information using an online form (landing page) provided by the organization. |
|    1      |       Consent          | The individual allows the organization to reach out only to confirm consent or obtain a higher level of consent. A typical example is a re-consenting customer journey that sends an email containing a link to a subscription center page where the individual can give consent. |
|    2      |       Transactional    | The individual consents to be sent transactional messages that relate to specific, existing business between the two parties. These messages can't include marketing or promotional content. Examples include bank statements, order receipts, and membership status messages. |
|    3      |       Subscriptions    | The individual consents to receive messages that include offers to sign up for mailing lists or other subscribed content. |
|    4      |       Marketing        | The individual consents to receive messages that include offers to sign up for mailing lists or other subscribed content. |
|    5      |       Profiling        | The individual allows the organization to use demographic and behavior information (such as website visits, email opens, and email clicks) for automated decision making. It is the organization's responsibility to classify which of their processing activities fall under the category of automated decision making. Examples include automatic calculation of credit limits or loan promises based on available data, and calculation mechanics using rule-based or predictive calculations. Children shall never be subject to such profiling and automated decision making. |

## Designer Tile Descriptions

### Content

-   **Marketing email message** - The email tile sends a marketing email message to each contact that enters it.

>[!Note]
> Your marketing email messages might contain special links to other Dynamics 365 features such as marketing pages, event websites, or voice-of-the-customer surveys, and you can set up customer-journey trigger tiles that react to customer interactions regarding each or any of these specifically. But even though you\'ve selected a marketing email message that includes elements such as these, the customer journey won't be associated with them unless you also add a nested tile for each specific link that you want to trigger on. Add a nested landing-page, event, or survey to an email tile to expose these elements and make them selectable in your trigger-tile configurations.

- **Marketing page** - Any marketing page that is the destination of a link embedded in some other type of marketing message, such as an email or social media post. Landing-page tiles can be nested under email tiles, where they represent a landing-page link that is included in the email message's content. The most important reason to add a nested landing page tile is to enable trigger tiles placed later in the pipeline to \"know\" about the landing page link and to react to contact interactions with it.

-  **Event** - Event tiles are typically nested under email tiles, where they represent a link to an event website that is included in the message's content, but they can also be placed on their own. The most important reason to add an event tile is to enable trigger tiles placed later in the pipeline to "know" about the event link and to react to contact interactions with it (registered or attended). Triggers can react either as soon as a contact clicks on    the link in an email, or only after a contact registers for or attends the event.

-  **Survey** - Survey tiles are typically nested under marketing email tiles, where they represent a link to an online survey that is included in the message's content. The most important reason to add a survey tile is to enable trigger tiles placed later in the pipeline to "know" about the survey link and to react to contact interactions with it. Triggers can react either as soon as a contact clicks on the link in an email, or only after a contact submits the survey.

### Actions

-  **Activity** - An activity is a record of a planned or completed real-world activity, such as an appointment, task, or phone call, that relates to some other record in Dynamics 365. Most forms in Dynamics 365 include an activity wall that shows all the activities that various users planned or completed in relation to that record, such as phone conversations with a specific contact, or meetings related to planning a particular event. Records for planned    activities can function as a to-do list for the users they are assigned to, and records for completed activities can contain details about what happened or what the outcome was. Activity tiles are stand-alone, so they can neither contain nor be nested under other tiles.

-  **Launch workflow** - Use a launch-workflow tile to invoke a custom workflow at any point in the customer journey. You can use them to advance a process stage, create alerts, and more. Workflows are highly customizable, and many organizations work with internal or external consultants to optimize them for their own unique, internal business requirements. Launch-workflow tiles are stand-alone, so they can not be contained or be nested under other tiles.

-  **Create lead** - The create-lead tile creates a new lead for each contact or account that enters the tile. It doesn't try to match any existing leads, so it always creates a new one. Each lead created will be linked either to the contact that entered the tile, or to the account that contact belongs to (the company they work for).

-  **LinkedIn campaign**- The LinkedIn-campaign tile links each contact who passes through it to a specific LinkedIn campaign, thus making it possible for a subsequent trigger tile to react to submissions of any LinkedIn Lead Gen Forms that belong to that campaign on LinkedIn.

### Targets

-  **Segment**- A segment is a collection of contacts grouped according to some common attribute or explicit assignment. Usually, each of your customer journeys starts with a segment tile, which establishes the collection of contacts who you'll be working with for that journey. When your customer journey starts running, it immediately processes all the contacts found in its target segments at that time. As time goes on, any new contacts that join the target segments will also start their journey here for as long as the customer journey is active.

-  **Record updated** - Use the record-updated tile to monitor all records belonging to a specific entity, and then find the contact associated with any of those records that gets created, deleted, or updated while the journey is running. All contacts found by this tile will be sent down the customer journey starting at the location of the tile.

### Flow Control

-  **Scheduler**- The scheduler tile holds contacts for some amount of time before sending them on to the next tile in their journey. You could use this to insert a delay, such as a delay of one week between sending an initial marketing email message and then sending a reminder. You can set the schedule using a relative time (such as: wait 7 days) or an absolute time (such as, wait until May 21, 2018). Scheduler tiles are stand-alone, so they cannot contain nor be nested under other tiles.

-  **Trigger**- Trigger tiles hold contacts until some condition is true, or until a defined amount of time expires. The trigger splits the path, so contacts that fulfil the trigger conditions in time will go down the true path, but contacts that still haven't met the condition when time is up will go down the false path.

-  **Splitter and splitter-branch tiles** - Splitter tiles add a fork to the customer journey pipeline, sending a random selection of contacts down each available path. You'll always use a splitter tile together with at least two splitter-branch tiles. The splitter tile initiates the split and establishes the basis for dividing the contacts (by percentage or absolute value), while each splitter-branch tile establishes the specific portion or number of  contacts travelling down the path it controls. The bottom splitter-branch tile always implements a remaining rule, which applies to all contacts that don't fulfil any of the other available rules. Splitter and splitter-branch tiles are stand-alone, so they can neither contain nor be nested under other tiles.
