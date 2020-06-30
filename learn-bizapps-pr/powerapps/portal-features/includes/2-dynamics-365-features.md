Portal templates provide additional features that extend the functionality of Microsoft Dynamics 365 apps. The following sections describe the features that can be found in portal templates.

## Case management

The case management capabilities extend Dynamics 365 Customer Service by allowing portal users to log and update support cases, tickets, and questions. This information is stored in the Dynamics 365 case entity and communications are tracked by using portal comments.

This feature is a common use case for portals and provides customer service organizations with a key channel to interact with their customers. A key benefit is that customers who want to submit a ticket are presented with options to review existing knowledge articles and forum posts because these items might resolve the customer's question in a faster manner.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrBLh]

## Knowledge management

One way for an organization to provide its external stakeholders with access to corporate information is to use the knowledge management features of Power Apps portals.

Knowledge articles can be created, approved, and curated in Dynamics 365 Customer Service and will then appear on the portal. Portal users will be able to browse and search knowledge articles, as needed.

Portal users who attempt to log a support case might be presented with a list of potential knowledge articles that could answer the specific query, deflecting the need to log a support case.

Knowledge management is available by default on the Customer self-service, Partner, Employee, and Community portal templates.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrEmA]

## Forums

Forums allow members of a particular community who share common interests to post questions, start discussions, or ask for help.  

Forums are set up and configured by using the Portal Management app. For information on how to configure forums, see [Set up and manage forums](https://docs.microsoft.com/dynamics365/customer-engagement/portals/setup-manage-forums/?azure-portal=true). The **Forums** feature is also available on the Community, Customer self-service, Employee self-service, and Partner portals.

An organization will choose forums as a way for their community to interact with each other by asking questions, starting discussions, or by looking for help.

Different forums are created within the Portal Management app in the Community Area by creating a forum record. Forums can be set up to represent different high-level topics that are based on the needs and goals of an organization, such as general discussions, support, and so on.

Forums fully support multilingual deployments and can be language-agnostic or linked to a specific language, which allows you to create portals that encourage global and local conversations between participants. 

When published, the forums are shown on the portal so that visitors can create new discussion threads or respond to existing discussions. The visitor can also subscribe to threads to receive updates or new responses to the discussions.

Portal visitors will create new threads (which are stored in the Power Apps portals metadata as **Forum Threads**) and will contain at least one post (post record). The post will contain the discussion details and optional file attachments. Other portal visitors (depending on permissions) can read or respond to particular threads (which will create additional post records). The collection of posts under a thread will represent a particular discussion or answer to a posted question.  

Having an active and engaging forum will strengthen a particular community and potentially alleviate customer and community support resources.

The organization can control from whom and how forum threads and posts are created, as determined by the related Forum Access Permissions, which will link to specific web roles.

## Blogs

The Community portal has the ability for members of its online community to post blog articles.  

See [Manage blogs](https://docs.microsoft.com/dynamics365/customer-engagement/portals/manage-blogs/?azure-portal=true) to learn how to configure and set up blogs on Power Apps portals.

The organization must first create the blog by using the Portal Management app. After the blog has been created, the organization can grant the Blog Author web role to the portal user. The portal user will then be able to use the front side editing tools to create blog articles by writing text and inserting images and reference links.

Blogs can also be configured to allow authenticated, unauthenticated, moderated, and unmoderated comments in response to the blog article.

Having an engaging blog will provide updated and compelling content to help promote the community or an organization's products and services.

The **Blog** feature is unique to the Community portal but it can be shown on other portal types.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrtZx]

## Ideas

The **Ideas** feature of the Community portal is an extension of the **Forums** feature in that it will allow members of the public to crowdsource particular ideas or suggestions.

The **Ideas** feature is available on the Community, Customer self-service, and Employee self-service portals.

To configure ideas on the Community portal, see [Crowdsource ideas](https://docs.microsoft.com/dynamics365/customer-engagement/portals/crowdsource-ideas/?azure-portal=true).

For an organization to best serve their customers or constituents, it is important that they allow an easy feedback mechanism. The Ideas portal allows portal visitors to submit a particular suggestion to the organization. This suggestion might be for a policy change, a new feature, or a new product or service recommendation. 

When a user adds a new idea, the autocomplete feature on the **Topic** field can be configured to allow visibility of existing ideas to reduce the number of duplicate or similar ideas.  

After the idea has been posted, other portal visitors will be able to vote on the idea or add their own comments or feedback. The policies of feedback and voting are configured from the Dynamics 365 Portal app. These policies could include the ability for users to vote on an idea, the number of votes allowed, and types of comments that are permitted.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrrm5]

## Project Service Automation 

The **Project Service Automation** feature is specific to the Partner portal template. To provide the **Project Service Automation** features, the Dynamics 365 Project Service app will need to be provisioned. The **Project Service Automation** portal extensions can be selected during the Partner portal installation or it can be installed later from the Portal admin center.

> [!div class="mx-imgBorder"]
> [![enable packages](../media/2-project-service-provision.png)](../media/2-project-service-provision.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Power Apps Portals admin center, install Project Service automation extension](../media/2-project-service-admin.png)](../media/2-project-service-admin.png#lightbox)

The key features of the **Project Service Automation** extension are:

- Ability for external stakeholders to view project information
- Process to confirm bookable resources
- Approve quotes
- View invoices
- Review contract and order forms

For more information, see the [Project Service Portal Extension](https://docs.microsoft.com/dynamics365/portals/integrate-project-service-automation/?azure-portal=true) documentation.

## Field Service integration 

The Partner Field Service portal integration extends the Dynamics 365 Field Service module to the Partner portal template. To add the Field Service portal extension, the Dynamics 365 Field Service app will need to be provisioned. The Field Service portal features can be selected during the Partner portal installation or they can be installed later by using the Portal admin center.

> [!div class="mx-imgBorder"]
> [![Power Apps Portals admin center, install Field Service extension(../media/2-field-service-admin.png)](../media/2-field-service-admin.png#lightbox)

The main features of the Field Service extension are:
- Ability for external stakeholders to view customer assets
- Allow customers to view and request work orders from the portal
- Customers can view invoices on the portal

For more information, see the [Field Service Portal Extension](https://docs.microsoft.com/dynamics365/portals/integrate-field-service/?azure-portal=true) documentation.


