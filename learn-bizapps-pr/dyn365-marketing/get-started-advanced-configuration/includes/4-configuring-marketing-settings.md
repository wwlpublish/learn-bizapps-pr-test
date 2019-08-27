Content settings hold common values, such as subscription center and physical mailing address, that you can place into an email message as dynamic text by using assist-edit. Upon setting up Dynamics 365 for Marketing, a default content setting should automatically be populated. You can either edit the existing one or create a new one. You can create as many content settings as you need. If you want to edit an existing “Live” content setting, you must stop and edit the content setting, then make sure to go live again. 

To create a new content setting, go to **Marketing** \> **Templates** \> **Content Settings.**

Choose an existing content setting to edit, or delete or choose **+ New** from the command bar to create a new one.

> [!NOTE] 
> If you want to edit an existing live content setting, you must first click **edit** or **stop** first

Fill out the required fields and other information as needed.

> [!NOTE] 
> The **Address main** field and **Subscription center** field is required when setting up content settings.

When finished, click **Save**. Then, click **Check for Errors** and **Go Live.**

![Configure content settings](../media/gsm-configurecontentsettings-1.png)

### Configure marketing settings

The Marketing settings section shows you how to configure the core marketing functionality for landing pages, email marketing, and customer-insights services. This includes:

- Matching strategies
- Landing page settings
- Default marketing settings

### Matching strategies

Matching strategies define how form submissions are matched to existing contacts or leads when deciding whether to update an existing record or create a new one. For example:

- For contacts, a simple contact-matching strategy might be based on an email address. When a submission is received, Dynamics 365 will check whether any existing contact has the submitted email address. If a match is found, the submission is used to update that contact; if no match is found, a new contact is created with the received values.

- For leads, if an existing lead record is found to match an incoming form submission, then the new submission will become part of that lead's history and could affect the lead's score.

​When configuring your landing page settings (described in the next section), you will be asked to select a default contact strategy and a default lead strategy, so we recommend setting up your matching strategies before configuring your landing page settings.

To access matching strategies, go to **Settings** \> **Advanced Settings** \> **Marketing Settings** \> **Matching** **Strategy**.

Choose an existing configuration to edit or delete or choose **+ New** from the command bar to create a new one.

Describe your strategy by entering a **Name** and **Description**. Set the **Target** field to the type of entity your strategy applies to (lead or contact). Click **Save** to display the **Attributes** section.

Under **Attributes**, click the three dots (...) then select **+ NEW Matching strategy attributes.** In the mapping field, select the attribute that you want to match on.

>[!NOTE] 
>This list specifies which contact or lead attributes (fields) to consider when looking for a match. The matching record must have identical 
> values for all the attributes shown here, so the more attributes you use, the narrower your search will be. Often the email address is enough
> to use as a unique identifier for contacts, but you might use additional attributes (such as first and last name) if you think some of your contacts
> might share an email address, or if you want tighter control (at the risk of creating extra contact records for the same person).

Click **Save** to save and close, or click **Save & Create New** to continue adding attributes. When finished, click **Save & Close**.

![Configure marketing settings](../media/gsm-configuremarketingsettings-1.png)

### Landing pages

Use the landing page area to configure settings specific to your marketing pages such as the privacy banner, how incoming data is matched to existing records, and portal defaults.

Go to **Settings** \> **Advanced settings** \> **Marketing settings** \> **Landing pages** to access your landing page settings.

Choose an existing configuration to edit or delete, or choose **+ New** from the command bar to create a new one.

The following settings are available on the **General** tab: ​

- **Name** - The name of the default-settings set, as shown on the list page.
- **Default** - Set to **Yes** to activate the current default-settings set on your site.

**Privacy Banner**

We recommend that you include a privacy banner on all your landing pages. This will let your customers know that you take their privacy seriously, and it might also be required in some locations. The following settings are available:

- **Insert privacy banner** - Choose **Yes** to enable this feature; choose **No** to disable it. When the privacy banner is enabled, the text and link defined in the other settings in this section will be added to each new marketing page that you create. The banner will also be added to any existing page that you open for editing; however, it won\'t be added to pages that are already published because these are read-only.
- **Privacy policy link URL** - Enter the full URL for your privacy statement.
- **Privacy policy link text** - This text is placed under the privacy banner text and creates a link to the privacy policy link URL you specified. Enter a short string of text that tells users what to expect, such as "Click here to read our complete privacy policy."
- **Privacy banner text** - Enter a summary of your privacy policy here

> [!NOTE] 
> You can use the built-in privacy statement for marketing pages to announce your use of cookies; however, it won't stop the server from
> setting the cookie, this only informs visitors that cookies are being used.

### Contact creation context capture / Marketing page configuration

These sections show where various types of information about the marketing context are stored when a submission results in a new contact
or lead record.

### Default matching strategy

These defaults will be applied to each new marketing form that you create, and they are saved with the form; however, you can override them at the form level. Changing any settings won\'t affect existing forms.
The following settings are available:

- **Update contacts/leads** - When a landing page submission is received, this setting establishes which types of records it can create or update---leads, contacts, or both.
- **Default contact matching strategy** - Shows the name of the field-matching strategy that you have set up to match incoming data against existing contact records. If a match is found according to this strategy, it will update that record. If no match is found, it will create a new contact. You can choose from among existing strategies or select **New** to create a new one.
- **Default lead matching strategy** - Same as the **Default contact matching strategy** setting, but for lead records.

![Default matching strategy](../media/gsm-configuremarketingsettings-2.png)

The settings on the **Portal defaults** tab control how your marketing pages are hosted in Dynamics 365. The following settings are available:

- **Website** - Identifies the portal website where all new marketing pages will be published while the current configuration record is active. This defaults to the event portal that was provisioned for you when you signed up for Dynamics 365, but you can choose another if you have one. If you change the portal default, the pages you\'ve already published will remain on their current portal, but new pages will go to the new portal.
- **Page language** - Sets the default language to use in the portal.
- **Container page** - Sets the container page used for marketing pages.

### Customer Insights sync

The customer-insights services are external services that provide analytical tools for working with customer records. They help you to better understand your customers and help you set up subscription lists and target segments for use in email-marketing campaigns. The customer-insights services also make dynamic field values available for use in marketing email messages as they are processed and sent by the marketing services.

The analytical and data-crunching capabilities of the customer-insights services are very powerful, but also resource-intensive, so the solution maximizes performance by synchronizing the relevant customer and account data between Dynamics 365 for Marketing and these external services. For optimal performance and functionality, choose only the entities that you need---no more and no less.

> [!IMPORTANT] 
> The sync settings are permanent, so after you begin syncing an entity you won't be able to remove it later. Syncing occurs often,
> and each entity that you sync requires storage space and processing time, so you should only sync those entities that you are sure you will need.

The most-used entities (including contacts, accounts, and events) are synced by default, but you can sync any set of entities that you want, including custom entities. The following features require all the relevant data to be present in the customer-insights services:

- **Segmentation** - All entities that you need to query in your segmentation criteria must be present.
- **Dynamic email content** - All entities with field values that you want to show as dynamic data in an email message must be present.
- **Lead scoring** - All entities with field values that you want to use in you scoring models must be present.

To sync an entity with the customer-insights services:

1. Go to **Settings** \> **Advanced settings** \> **Marketing settings** \> **Customer insights sync**
2. Select the check box for each entity that you want to sync
3. Select **Publish changes** and confirm your setting when prompted
4. Wait for up to a minute, until you see an announcement near the top of the page that **"Your changes have been accepted...".** If you don't see the announcement, select **Publish changes** again and then wait; repeat until you see the message
5. Depending on how much data needs to be synced (and other factors), you may need to wait for several minutes (or *up to six hours*) before your data is available for use in your segments, messages, and scoring models. Here are some ways that you'll be able to determine if a new entity is synced and ready for use (you only need to verify one of these scenarios):
    - The check box for the relevant entity on the **Customer insights sync** page is selected and grayed out when you first enter the page. The check box is gray to indicate that you can't turn-off the sync process once it has started. You must reload the page manually to see this change.
    - The relevant entity is shown in the [assist-edit menu](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/dynamic-email-content#assist-edit)for marketing email messages.
    - The relevant entity is shown in the **Profiles** list in the [segment designer](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/segmentation-lists-subscriptions). (Note that you must either create a new query group or remove all clauses from the existing query group to see the **Profiles** drop-down list here---otherwise the contact entity is already selected by default.)
    - The relevant entity is shown in the **Entity** list when you are editing a condition for a [lead scoring rule](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/score-manage-leads).

### Default marketing settings

The default marketing settings define a series of defaults used throughout the application. You can create your own, but only the one marked as Default will be active. ​

Go to **Settings** \> **Advanced Settings** \> **Marketing Setting**s \> **Default Marketing Settings** to access your marketing settings. ​

Choose an existing configuration to edit or delete, or choose **+ New** from the command bar to create a new one.

The following settings are available on the **General** tab: ​
- **Name** - The name of the default-settings set, as shown on the list page.
- **Owner** - The user that owns the record.
- **Default** - Set to Yes to activate the current default-settings set on your site.

The settings on the **Marketing Email** tab are defaults that apply to your marketing email messages. You will always be able to override these defaults for individual messages, but it will be more convenient for users if you set the defaults to their most-used values. The following settings are available:

- **Default Content Settings** - Choose a default content-settings record for providing dynamic values for the preview feature of the marketing-email designer.
- **Default Contact** - Choose a default contact record for providing  dynamic values for the preview feature of the marketing-email designer.
- **Enable Litmus integration** - Set to **Yes** to enable the inbox preview feature, which provides pixel-perfect renderings of how your email messages will look on specific client and platform combinations. The feature is provided by a Microsoft partner called Litmus Software, Inc. (litmus.com), and is optional.

The following settings on the  **Customer Journey** tab:
- **Default time zone** - The time zone selected will be used when starting and stopping your customer journeys.

The settings on the **Double Opt-In** tab are global features for your Dynamics 365 instance. When it's enabled, all new-subscription and increase-consent requests will require double opt-in and the same settings will apply everywhere.

Before you start to set up and enable double opt-in, you will need to have the following elements available.

- A subscription confirmation-request email message.
- An increase consent confirmation-request email message.
- A content-settings record for use with all confirmation-request messages.
- A thank-you page to redirect to after a contact confirms each type of request.

After the above elements are created, fill out the following settings:

- **Enable double opt-in** - Set to **Yes** to enable double opt-in on your instance. Set to **No** to disable it.
- **Subscriptions** - Select the confirmation message to send to contacts requesting to join a new mailing list.
- **Consent** - Select the confirmation message to send to contacts requesting to increase their consent level.
- **Thank-you page for newsletters** - Select a marketing page to show to contacts after they confirm a new subscription.
- **Thank-you page** - Select a marketing page to show to contacts after they confirm an increase of their consent level.
- **Content settings** - Identify the content-settings record that you want to use for all double opt-in messages.

The settings on the **Bypass Email Deduplication** tab are intended to de-duplicate outgoing marketing email messages to ensure that each message is only sent one time to each unique email address. This means that if more than one contact record in the target segment has the same email address, only one of those contacts will receive the message. Duplicate email addresses probably indicate that the same person is represented by two different records in your database (for example, because they registered at different times using two different first-name variants, such as \"Bob\" and \"Robert\"), so this is the desired behavior.

However, some organizations need to send separate copies of the same email messages to multiple contacts who use the same email address. In this case, personalized content, such as account details, would probably be different for each recipient. If your organization requires this, then set **Bypass email deduplication** to **Yes**. Set it to **No** to revert to the standard de-duplication behavior.

### Data protection tools

Dynamics 365 for Marketing is prepared to help organizations work in
compliance with the European Union's General Data Protection
Regulation (GDPR) when using the system, but some development work,
consultancy assistance, or both, is still necessary. You must customize
your Dynamics 365 system to enable its built-in GDPR compliance tools to
function correctly.

Dynamics 365 for Marketing allows you to request, capture, and store
consent. You can design your marketing activities to respect the consent
given by your audience. It is important that you include relevant
information in your marketing objects (like landing pages and email
marketing message) that unambiguously informs your audience about the
data that you collect and the purpose of your processing. Your audience
must have the option to give consent freely, make an informed decision,
and be able to review, update, or revoke consent at any time.

>[!IMPORTANT] 
>The accounts entity does not store any GDPR consent information---only contact entities include it. Lead-scoring
> models that operate on the account level can't respect the consent of the contacts that belong to that account, but they can still score account
> leads based on interactions generated by all of those contacts. This means that you must be careful not to use automatic lead scoring for 
> automated decision making (profiling) related to account-based leads if those decisions affect individuals. You can still use the feature to 
> score account leads, but you must not use it for indirect contact scoring if the score is used for automated decision making.

By default, GDPR features such as consent management are disabled on new
Dynamics 365 for Marketing installations. To enable or disable the
features:

1.  Go to **Settings** \> **Advanced settings** \> **Marketing settings** \> **Data protection tools**.

2.  A list of **Active GDPR configurations** opens. If a configuration
    > already exists, then select it. If no configuration exists, then
    > select **+ New** on the command bar. You can have *at most* one
    > GDPR configuration.

3.  The **GDPR Configuration** page opens. Set the following options:

	-   **Name** - Enter a name.

	-   **Respect consent** - Set to **Yes** to enable GDPR features
    throughout your app. Set to **No** to disable them.

4.  Select **Save**.

To view and set a consent level for each contact, you will need to open
a contact record, go to the **Details** tab, and scroll down to find the
**Data protection** section.

The following settings and information are available:

-   **Consent given** - Read or set the maximum consent level granted by
    this contact. This contact will only be able participate in
    marketing initiatives permitted for this consent level or lower. You
    should only change this setting after receiving explicit consent
    from this contact. Usually, you should allow contacts to change this
    themselves using a subscription center.

-   **Is a child** - Select to indicate that this contact is a minor
    (usually, under 18 years old), and therefore requires extra
    protection.

-   **Parent or custodian** - If the contact is a child, then select
    their legal parent or custodian (guardian) in this field. The parent
    or custodian must also be saved as a contact in your database.

You can filter segments by consent level similar to other contact
values. Use the **Consent Given** field on the Contact entity to filter
by consent level.

You can set minimum required consent levels for customer journeys, lead
scoring models, and include a consent selector in a subscription center.
Using a subscription center, you can set up a marketing form field that
maps the GDPR consent field to the contact entity. You can also set up a
double opt-in to confirm changes in consent level and subscriptions to
ensure that all requests to change a consent level were made
specifically by a person who can read that contact's email.

Oftentimes you may be asked to demonstrate that your organization
complies with the GDPR regulations. Therefore, you must be able to
identify all data structures (including tables, entities, and fields)
that contain personal information. You should establish mechanics that
allow you to easily discover, deliver, update, and/or delete this data
when requested by your customer.

-   For more information about how Dynamics 365 Customer Engagement apps help you with essential data tasks like discovering, managing, protecting, and reporting for your GDPR compliance, see [Microsoft Dynamics 365 helps enable data privacy for GDPR compliance](https://www.microsoft.com/TrustCenter/CloudServices/dynamics365/GDPR) in the [Microsoft Trust Center](https://www.microsoft.com/trustcenter).

-   For details about how to use the Dynamics 365 API to implement custom GDPR-related functionality for your Dynamics 365 for Marketing system, see [Developer Guide (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

There are several scenarios in Dynamics 365 for Marketing that allow you
to demonstrate compliance. One scenario is to view a history of
consent-level changes for each contact. To do this, open the contact
record, select the **Related** tab, and select **GDPR consent change
records.** Another scenario is to enable auditing to log all record
changes. You can access the auditing features by opening the Dynamics
365 -- custom application and then going to **Settings** \> **System**
\> **Auditing** to open the **Audit** page.
