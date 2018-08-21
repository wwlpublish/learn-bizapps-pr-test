## Dynamics 365 for Customer Service core components

Now we'll look at the basic record types that are used for service management.

**Customer records**: In Microsoft Dynamics 365 for Customer Service, customer service requests are typically managed in relation to an existing contact or account record. These contacts and accounts are also used by other areas of business operations, like sales or marketing. 

- A *contact* represents a person, just as it does in Microsoft Outlook. 
- An *account* represents a company, organization, or group of people. 

Although these are the typical uses of accounts and contacts, different Customer Service deployments might use these record types differently. But they're both typically referred to as *customers*. For example, when entering the customer on a case, you can select either an account or a contact.

**Cases**: Cases are the fundamental record type in service management and represent a single incident of service. Different organizations might use different terms to refer to cases: incidents, tickets, service requests, and so on. 

In other words, cases are anything in the context of a customer interaction that requires some type of resolution or answer. Many cases can be associated with a single customer record at the same time. In Customer Service, users can view open and resolved cases from the customer record.

**Activities**: Interactions between a business and its customers that are considered important enough to track in Customer Service are known as *activities*. Activities can be associated with many kinds of records in Customer Service. Here are some things you can do with accounts and activities:

- The user can open the record and find the activities under **Closed activities** or **Open activities**. 
- Closed activities are those that have marked as been completed.
- Open activities either haven't been marked as completed or are pending completion at a different date and time.

**Entitlements**: Entitlements can be used to specify the amount of support services a customer is entitled to. For example, a customer's entitlement in Customer Service might allot ten support cases that the customer can use at his or her discretion. 

**Entitlement channels**: Entitlement channels can be used to specify the type of service a customer is entitled to. There are five entitlement channels:

- Phone
- Email
- Web
- Facebook
- Twitter

**Knowledge Base articles**: The Knowledge Base in Customer Service is a repository of informational articles that help customer service representatives resolve cases. In some organizations, the information in the Knowledge Base helps employees not only resolve issues but also ask follow-up questions.

Typically, this information is about the company, product questions and answers, and any other kind of information that can help employees better handle customer inquiries, requests, or issues.

**Resolution activities**: After all the activities for a case are resolved, the case itself can be resolved. After the case is resolved, an activity of the **Resolution Activity** type is created. This activity is found in the closed activities associated with a case. Resolution activities show the case's resolution and how much time was spent on the case.

**Queues**: A queue is a place to organize and store activities and cases that are waiting to be processed.

For example, an organization might have a support team that has the email address `support@contoso.com`. If the support team receives an email that's sent to this address, a member of the team handles the support case and works to resolve the issue for the customer. 

Queues in Microsoft Dynamics work the same way.

**Products**: Products in the Microsoft Dynamics CRM Product Catalog can be related to a customer service case. Therefore, they can help provide a more detailed view of cases, resolutions, and customer feedback at a product level.

Although products can be associated with cases to better categorize the types of cases, it's important to note that there are no transaction aspects of cases that leverage products for pricing or invoicing. In addition, using products together with cases is optional and might not be applicable to all organizations.

**Goals**: In addition to reporting on and analyzing the information in Customer Service, organizations can use the Goal Management features to establish and track progress against target values for key performance indicators (KPIs). For service management, these KPIs might include metrics like resolved cases or in-progress cases.

**Service level agreements**: Service level agreements (SLAs) are a way of tracking and defining what should happen when a case is opened. You can track things like when a case was first taken by a support engineer and how long it took to resolve the case. You can also send emails based on specific warning and failure timelines.