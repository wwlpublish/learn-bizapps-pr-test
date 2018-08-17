## Automate case creation and resolution
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2r0x8]

In many organizations the customer service function is highly structured. Customer service can include entitlement commitments to service level agreements, frequent requirements to track information such as the amount of time spent in resolving cases, and so forth. Because of these characteristics, the interaction of activity and case records has some differences compared to how activities interact with other record types. 

Two of the most important of these differences are:

- A case record can be resolved with incomplete activities. This means that the user will be informed that any open activities will be automatically cancelled.

- When a case record is resolved, the duration of the case resolution process will automatically total the actual duration of time spent in all activities associated with the case.

Keep in mind that although the Microsoft Dynamics 365 for Customer Service will automatically calculate the total time spent on a case, this may or may not accurately reflect the time spent. During the resolution process, the user can enter a different duration that reflects the actual amount of time spent.

The purpose of a case is to track customer issues, questions, and requests and manage them through a resolution. There are times when a customer might submit a request and then change their mind. Microsoft Dynamics 365 for Customer Service users, by default, have two options to handle this. They can either cancel the case or delete it. 

## Resolving Cases 
Cases can be resolved in many ways. Sometimes the issue can be resolved without having to do research or use other resources. However, sometimes the customer service representative needs to perform research on the issue to determine how other representatives resolved similar issues by checking the knowledge base. Sometimes the issue might have to be escalated. 

A case cannot be resolved until all activities that are related to the case, such as telephone calls, letters, appointments, or email messages, are completed. This prevents anyone from accidentally closing a case before all workflow or mandated activities are finished.

### Deleting and canceling cases

There are occasions when the customer no longer wants assistance. Representatives have two choices: cancel or delete the case. 

- **Delete a case**: Deleting a case removes all activities, notes, and attachments that are linked to the case. Keep in mind that this is a permanent action, and the record of the customer's issue is lost. 

- **Cancel a case**: Unless you are sure that the record will not be needed in the future, a better choice is to cancel the case. Keep in mind that many organizations configure the security roles in Microsoft Dynamics 365 for Customer Service so that users cannot delete cases. This helps avoid incorrect deletions. Canceling the case keeps the record in the system for reactivation later if it is necessary. 

### Reactivating cases

If a case was closed, it can be reactivated. For example, if a customer calls back with a related issue, instead of opening a new case, the customer representative can reactivate the original case.

### Assigning Case Records
After a case is created, any customer service representative can assign a case to another representative, or any other user in the system or to a queue. 

In Microsoft Dynamics 365 for Customer Service, many record types have an Owner. Ownership of a record means that either the person or the team that is designated as the owner of a record and is responsible for managing the record. When a business scenario requires that the owner of the record changes, the record is assigned to a different person or team.

### Assigning a Case Record to a Queue
Microsoft Dynamics 365 for Customer Service queues can be used to help in service management scenarios. For example, a queue can be configured to accept incoming email messages, which are then converted to cases.