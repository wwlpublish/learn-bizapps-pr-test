## Dynamics 365 for Customer Service Core Components ##

Now we'll look at the basic record types that are used for service management.

**Customer records**:  Typical customer service requests using Microsoft Dynamics 365 for Customer Service are managed in relation to an existing contact or account record. These contacts and accounts are the same contacts and accounts used by other areas of business operations such as sales or marketing. 

- A Contact represents a person, just as it does in Microsoft Outlook. 
- An Account, on the other hand, represents companies, organizations, or groups of people. 

While these are the typical uses of accounts and contacts, different Microsoft Dynamics 365 for Customer Service deployments might use these record types differently. But typically they are referred to as "customers". When entering the customer value on a case, for example, you can choose either an account or a contact.

**Cases**:  Cases are the fundamental record type in service management, and represent a single incident of service. Different organizations may refer to cases using different terms, including incident, ticket, service request and so forth. 

In other words, cases are anything in the context of a customer interaction that require some type of resolution or answer. A customer can have many cases that are associated with his or her record at any time. Within Microsoft Dynamics 365 for Customer Service, users can see open and resolved cases from the customer record.

**Activities**: Interactions between a business and their customers are called activities that are deemed important enough to track within Microsoft Dynamics 365 for Customer Service. Activities can be associated with many kinds of records within Microsoft Dynamics 365 for Customer Service. Here are things you can do with accounts and activities:

- The user can open the record and find the activities located under Closed activities or Open activities. 
- Those activities that are closed are those that have been completed.
- Open activities are those that have either not been marked as completed or are pending completion on a different date and time.

**Entitlements**: Entitlements can be used to specify the amount of support services a customer is entitled to. For example, a customer’s entitlement in Microsoft Dynamics 365 for Customer Service might allot ten support cases that they can use at their discretion. 

**Entitlement channels**: Entitlement channels can specify the type of service a customer is entitled to.  There are five different entitlement channels:
- Phone
- Email
- Web
- Facebook
- Twitter

**Knowledge base articles**: The Knowledge Base is a repository of informational articles that are used to help customer service representatives resolve cases. 

In some organizations, the Knowledge Base is also used to provide Microsoft Dynamics 365 for Customer Service users with information about how to not only resolve issues, but to ask follow-up questions as well. Typically, this is information about the company, product questions and answers, and any other kind of information that can be used to better equip employees to better handle customer inquiries, requests, or issues.

**Resolution activities**: After all activities regarding a case are resolved, the case itself can be resolved. Once the case is resolved, an activity type named Resolution Activity is created. This activity is found in the closed activities associated with the case. The Resolution Activity displays the case’s resolution as well as how much time was spent on the case.

**Queues**: A queue is a place to organize and store activities and cases that are waiting to be processed. For example, an organization might have a support team whose email address is support@contoso.com. 

If the support team receives an email message that is sent to this address, a member of the team handles the support case and works to resolve the issue for the customer. 

Queues in Microsoft Dynamics work the same way.

**Products**: Products within the Dynamics CRM Product Catalog can be related to a customer service case and can help provide a more detailed view of cases, resolutions, and customer feedback at a product level. It is important to note that while products can be associated to a case to better categorize types of cases, there are no transaction aspects of cases that leverage products for pricing or invoicing. In addition, the use of products along with cases is optional and might not be applicable to all organizations.

**Goals**: In addition to reporting on and analyzing the information contained within Microsoft Dynamics 365 for Customer Service, organizations can use the Goal Management features to establish and track progress against target values for key performance indicators. For service management, these might include metrics such as resolved or in-progress cases.

**Service level agreements (SLAs)**: SLA stands for Service Level Agreement. Service Level Agreements are a way of tracking and defining what should happen when a case is opened. You can track items related to your cases, such as when the case is first taken by a support engineer, and how long it took to resolve the case.  You can also send emails based on certain warning and failure timelines.