In many organizations, the customer service function is highly structured. Customer service can include entitlement commitments to service level agreements (SLAs), requirements to track information like the amount of time spent in resolving cases, and much more.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2r0x8]

Because of these characteristics, activity records interact somewhat differently with case records than with other record types. Here are two of the most important differences:

- A case record can be resolved if it has incomplete activities. The user will be informed that any open activities will be automatically canceled.
- When a case record is resolved, the duration of the case resolution process is automatically calculated by adding the actual time spent on all activities that are associated with the case.

Keep in mind that although Microsoft Dynamics 365 for Customer Service automatically calculates the total time spent on a case, that value might not accurately reflect the time that was spent. During the resolution process, the user can enter a different duration that reflects the actual amount of time spent.

The purpose of a case is to track customer issues, questions, and requests, and to manage them through a resolution. Occasionally, customers might submit a request but then change their mind and decide they no longer want help. By default, Customer Service users have two ways to handle this situation: they can cancel the case or delete it. 

## Resolving cases 
Cases can be resolved in many ways. Sometimes, the issue can be resolved without having to do research or use other resources. Other times, the customer service representative needs to research the issue and check the Knowledge Base to learn how other representatives resolved similar issues. Sometimes, the issue might have to be escalated. 

A case can't be resolved until all activities that are related to it, like telephone calls, letters, appointments, or email messages, are completed. This prevents anyone from accidentally closing a case before all workflow or mandated activities are finished.

### Deleting and canceling cases

Sometimes, customers decide that they no longer want help. When this happens, representatives have two choices: they can cancel the case or delete it. 

- **Delete a case**: Deleting a case removes all activities, notes, and attachments that are linked to the case. Keep in mind that this is a permanent action. The record of the customer's issue will be lost.
- **Cancel a case**: Unless you're sure the record won't be needed in the future, a better choice is to cancel the case. Canceling a case keeps the record in the system, so that it can be reactivated later if it's needed again. Keep in mind that many organizations configure the security roles in Customer Service so that users can't delete cases. This helps avoid incorrect deletions.

### Reactivating cases

If a case was closed, it can be reactivated. For example, if a customer calls back with a related issue, the customer representative can reactivate the original case instead of opening a new one.

### Assigning case records
After a case is created, any customer service representative can assign it to another representative, to any other user in the system, or to a queue. 

In Customer Service, many record types have an owner. Ownership of a record means that the person or team that's assigned as the owner of a record is responsible for managing that record. If a business scenario requires a change in ownership for a record, the record is assigned to a different person or team.

### Assigning a case record to a queue
Customer Service queues can be used to help with service management scenarios. For example, a queue can be configured to accept incoming emails, which are then converted to cases.