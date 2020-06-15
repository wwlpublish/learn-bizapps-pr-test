The Community Portal starter portal is meant to be used as a platform for an online community. 

> [!NOTE]
> The Community Portal is only available on Common Data Service environments with Dynamics 365 apps enabled.

These communities are often built around the fact that the community members use services of the same organization. Perhaps, it's a local city council, providing ongoing services to its constituents, or may be it's a community of people who purchased products from a manufacturer and they use the community site to share tips and tricks between themselves, or assist other members to troubleshoot.

When you consider interactions between an organization and community members, they often fall into two channels: 

### Self-service
Community Portal extends organization's self-service capabilities including:

- Knowledgebase access
- Access to blog posts that share relevant information
- Advanced search across the site content

### Assisted service
Community Portal allows organization to tap into Dynamics 365 Service support channels: 

- Submit cases/tickets via configurable web forms
- Review, update, and comment on existing cases
- Participate in discussion / community forums

Community Portal caters for both self-service and assisted service scenarios and portal visitors are able to do the following: 

## Forums

Forums allow members of a particular community with common interests to post questions, start discussions or ask for help.  

Forums are set up and configured using the Portal Management App.  For information on how to configure Forums, please refer to: [Set up and manage forums](https://docs.microsoft.com/dynamics365/customer-engagement/portals/setup-manage-forums/?azure-portal=true).

> [!NOTE]
> Forums feature is also available on the Community, Customer Self-Service, Employee Self-Service and Partner portals.

An organization will choose Forums as a way for their community to be able to interact with each other by asking questions, starting discussions or by looking for help.

Different Forums are created within the Portal Management App in the Community Area by creating a Forum record.  Forums can be set up to represent different high-level topics based on the needs and goals of an organization, for example;  General Discussions, Support, etc.

Forums fully support multi-lingual deployments and can be either language-agnostic or linked to a specific language. That allows you to create portals encouraging both global and local conversations between the participants. 

When published, the Forums are surfaced on the Portal to allow visitors to create new discussion threads or respond to existing discussions.  The visitor can also subscribe to threads to receive updates or new responses to the discussions.

Portal visitors will create new Threads (stored in the Power Apps portal Metadata as Forum Threads) and will contain at least one Post (Post record).  The Post will contain the discussion details as well as optional file attachments.  Other Portal visitors (depending on permissions) can read or respond to particular threads (this will add additional Post records).  The collection of Posts under a Thread will represent a particular discussion or answer to a posted question.  

Having an active and engaging forum will strengthen a particular community as well as potentially alleviate customer and community support resources.

The organization can control who and how Forum Threads and posts are created determined by the related Forum Access Permission, which will link to specific Web Roles.

## Blogs

The Community Portal has the ability for members of its online community to post Blog articles.  

See [Manage blogs](https://docs.microsoft.com/dynamics365/customer-engagement/portals/manage-blogs/?azure-portal=true) on how to configure and set up Blogs on the Power Apps portal.

The organization must first create the Blog using the Portal Management App.  Once the particular Blog has been created, then the organization can grant a Portal User the Blog Author web role.  The Portal User will then be able to use the front side editing tools to create Blog articles by writing text, inserting images and reference links.

Blogs can also be configured to allow authenticated, unauthenticated, moderated, and unmoderated comments in response to the Blog article.

Having an engaging Blog will provide updated and engaging content to help promote the community or an organization's products and services.

The Blog feature is unique to the Community Starter Portal but can be surfaced on other starter portal types.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrtZx]

## Ideas

The Ideas feature of the Community Portal is an extension of the Forum feature where it will allow members to of the public to "crowd source" particular ideas or suggestions.

The Ideas feature is available on the Community Portal, Customer Self-Service Portal and the Employee Self-Service Portal.

To configure Ideas on the Community Portal, please refer to: [Crowdsource ideas](https://docs.microsoft.com/dynamics365/customer-engagement/portals/crowdsource-ideas/?azure-portal=true).

In order for an organization to best serve their customers or constituents, it is important to allow an easy feedback mechanism.  The Ideas portal allows for portal visitors to submit a particular suggestion to the organization.  This may be for a policy change, a new feature, or even a whole new product or service suggestion. 

When a user is adding a new idea, the autocomplete on the Topic field can be configured to allow visibility of existing ideas to reduce the number of duplicate or similar ideas.  

Once the idea has been posted, other portal visitors will be able to vote on the idea or add their own comments or feedback.  The policies of feedback and voting are configured from the Dynamics 365 Portal App such as the ability to up vote or down vote an idea, number of votes and comment policies.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrrm5]

## Knowledge articles

An effective way to maximize the use of helpful content is the ability to search and surface Knowledge Articles on a Power Apps portal.  This feature uses the Dynamics 365 Customer Service Knowledge articles (used for internal customer Service Management) and provides a mechanism to surface on the Power Apps portal.

The Power Apps portals Knowledge Article feature is available on the Community, Customer Self-Service, Employee Self-Service and Partner Portals.

To configure the Power Apps portals Knowledge Article feature, please refer to the [Documentation](https://docs.microsoft.com/dynamics365/customer-engagement/portals/configure-knowledge-categories-articles/?azure-portal=true).

An organization can determine which of its existing Knowledge Articles should be surfaced on the Portal by setting the Internal flag and by associating the Knowledge Article to the appropriate Categories.

A Portal visitor will be able to navigate through the category structure to locate a specific Knowledge Article or by using the keyword search features of the Portal.

When entering a support case (See Support Cases) the portal user may be redirected to browse potentially related Knowledge Articles to provide a more immediate response to a question and also reduce the case load of the support organization.

## Support cases

The Dynamics 365 Customer Service Case functionality is surfaced on the Power Apps portal using the Support Case portal feature.

This is a common use-case for Power Apps portals and is available on the Community, Customer Self-Service, Employee Self-Service and Partner Portals.

To set up and configure the Power Apps portals Case Management features, please refer to the [Manage cases in portals](https://docs.microsoft.com/dynamics365/customer-engagement/portals/case-management/?azure-portal=true).

An organization can allow customers to log in to the portal and begin the support process by first seeing if the particular question or issue can be resolved with existing information in Forum posts or Knowledge Articles.  

If the information provided is not sufficient to resolve the issue, the customer can create a new support case through the portal.  This will create a corresponding Case record in Dynamics 365 Customer Service.  The case can be assigned to a particular support representative or team following the same business processes defined for using the Customer Service Hub.

The support representative can follow existing processes and procedures to resolve the case, such as referring to a Knowledge Article or providing steps to resolve the issue using traditional support channels (phone, email).  The support representative can also associate a Portal Comment activity record to the Case, which is visible on the Case timeline in both Dynamics 365 and the Portal.  Additional configuration using Common Data Service workflow and email integration will allow the customer to be notified of updates to the case with a hyperlink to the Portal.

A customer can also respond and update the case by creating Portal Comments to the case.  When the case is resolved, the customer could have the option to reopen the case if the issue was not resolved.

