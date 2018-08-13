# Practice with Customer Service

This practice will take you through the fundamentals of the Customer Service Hub for Microsoft Dynamics 365. When you complete the tasks in this practice, you'll be well along your way to helping your customers find solutions to problems with their products and services.

> [!NOTE]
> Keep in mind that for the following scenarios, you must have the Customer Service Manager or Customer Service Representative role, or equivalent permissions. [Find out if you have the correct permissions](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/basics/view-your-user-profile)

Consider the following scenario. HCL is a professional services company and most of their profits come from the support services that they offer to their customers.   HCL offers help desk services to their customers during normal business hours of 8 to 5.  Additionally, they provide their preferred customers with 24-7 support,

Their preferred customers are broken down into three different levels: 
- **Gold**: Highest Priority customers with a guaranteed 15-minute response time.   
- **Silver**: Customer are guaranteed a callback from a customer service agent in 1 hour 
- **Bronze**: Customers are entitled to 24/7 support and a 2-hour agent response time.   

HCL has identified two areas that they would like to focus their attention on: 
 
1. Each customer service representative, should have a centralized dashboard that shows the representatives daily workloads.  The dashboard should contain the following information. 
 
    - A list of all the open cases that they are currently assigned to them 
    - A list of all the open Activities assigned to them   
    - Cases by Origin  
    - Cases by Priority 

1. Agents can take cases from either new of existing customers.  Agents should be able to easily identify if the customer is new or existing prior to creating a case.   
    - If the customer is an existing customer, they can create the case directly.  
    - If the customer is a new client, they must first create a new record for the customer and then, create a case for them.

## Scenario one: Create a new account

A new customer name Wendy Smith who works for Coho Consulting has just contacted HCL about the following issue:
- A network backup from the previous evening has failed. 

Tasks to Accomplish in this Exercise: 
- Add a new account for Coho Consulting.
- Add a contact record from Dennis Smith to Coho Consulting.
- Create a new case for Coho Consulting with the following information:
    - **Origin**: Phone 
    - **Title**: Network backup Failed 
    - **Contact**: Dennis Smith. 
    - **Product**: leave blank 
    - **Entitlement**: leave blank 
    - **Priority**: High 


**Task one**: Add a new account for Coho Consulting.
1. In the Customer Service Hub, Go to **Service**, and then select **Accounts**.
1. On the command bar, select **New**.
1. Fill in information about the account.
1. Select **Save**.

**Task two**: Add a contact record from Wendy Smith to Coho Consulting.
1. Locate the **Contacts** table.
1. Select the **+** to add a new contact.
1. Fill the contact information into the Contact Quick Create form.
1. Select **Save**.

**Task three**: Create a new case for Coho Consulting
1. Go to **Service** > **Cases**.
1. Select **New Case**.
1. For **Case title** enter “Network Backup Failed”.
1. For **Customer** enter “Coho Consulting”.
1.For **Contact** enter "Wendy Smith”.
1. For **Origin** enter “Phone”.
1. Select **Save**.

## Scenario two: Create a case
HCL generally bills their customers based on the total amount of time an agent spends on a call.  The total time spent is a summary of all the activities attached to a specific case.  It is important that all activities related to the case are documented as agents work through the calls.

After doing some research, the agent identifies that the problem is because the previous day was a holiday.  Because it was a holiday, the previous back-up media was not replaced.  The backup will not overwrite media that was written to in the last 48 hours.  

Since no business was conducted on that day, the agent can skip the back-up job.

Tasks to Accomplish in this Exercise:
 
- Add an incoming phone call activity from Wendy Smith to the case.
- Add a task to the case to be performed by the agent.
- Add an outgoing phone call activity to Wendy Smith task called "Inform Dennis on Resolution".
 
**Task one**: Add an incoming phone call activity from Wendy Smith to the case.
1. Locate **Activities**.
1. Choose **Add Phone Call**.
1. Set the duration to 15-minutes.
1. Add the following notes: "Initial call from Wendy to report the discovery of a failed backup."
1. Select **OK**.

**Task two**: Add a task called "Research problem" to the case.
1. Locate **Activities**.
1. Choose **Task**. 
1. Set the duration to 20-minutes.
1. Add the following notes: "Because it was a holiday, the previous back-up media was not replaced.  The backup will not overwrite media that was written to in the last 48 hours."
1. Select **OK**. 

**Task four**: Add an outgoing phone call activity to Wendy Smith task called "Inform Dennis of Resolution".
1. Locate **Activities**.
1. Choose **Add Phone Call**.
1. Set the duration to 15-minutes.
1. Add the following notes: "Called Dennis to inform him on the Resolution".
1. Select **OK**. 

## Scenario three: Resolve a case
Once a case has been resolved, the agent needs to resolve the case.  When a case is resolved, they need to note what they did to resolve the case.  The time they spent working on the case activities also need to be accounted for.  
 
**Task one**: Ensure that all case related activities are completed.
1. Open each activity on the Case. Ensure all case-related activites are complete.
1. Select **Mark Complete**.

**Task two**: Resolve the case.
1. On the command bar, select **Resolve case**.
1. In the Resolve Case dialog box, select the **Resolution Type** list, and the select how the case was resolved. 
1. In the **Resolution** box, type a short explanation of the resolution. 
1. Select **Resolve**.
 
## Scenario four: Route a case
HCL will need four queues that they can use to route cases for agents to work on.  Those 4 queues are:   
- Gold 
- Silver 
- Bronze 
- Standard 

When a new case is created the service level of the case needs to be captured on the case.  Based on the service level, the case will automatically be routed to the correct queue. Rules need to be created that allow the automatic routing: 

- Route any cases with a service level of Gold to the Gold Queue.
- Route any cases with a service level of Silver to the Silver Queue.
- Route any cases with a service level of Bronze to the Bronze Queue.
- Route any cases that do not have a service level defined to the Standard Queue. 

**Task one**: Create the queues.
Create four Queues in the application: Gold, Silver, Bronze, and Standard.
1. Go to **Settings** and the select **Service Management**. 
1. Choose **Queues**.
1. 1. Select **New**.
1. Enter the name of the Queue.
1. Select **Save**.

**Task two**: Create the rules.
Create a routing rule that routes cases to the appropriate queue based on the service level of the case. 
1. Go to **Settings** and then select **Service Management**.
1. Select **Routing Rule Sets**.
1. Select **New**. 
1. Select **Rule Case Routing**.
1. Select **Save**. 
1. In the **Rule Items** section, select **Add Rule** to specify conditions for routing cases to a queue. 
1. In the **Rule Item** form, type a descriptive name for the rule item, for example: Gold.
1. Under **Rule Criteria**, in the If Conditions section, specify the conditions for which the case will be routed. For example, Case – Service Level – Equals - Gold.
1. Under **Then Conditions**, specify the queue to route the case to.  For example: Select the Gold Queue
1. Select **Save** and then **Close**.
1. Repeat for each Queue you want to route items to.
1. In the **Routing Rule Set** record, select **Activate**.

## Scenario five: Manage a case

This scenario continues the previous scenario by applying the tasks to the Coho Consulting company. Assume Coho Consulting has just become a gold customer with your company. Wendy Smith has contacted you about a printer problem she is having.

- She is having a problem with a printer that was recently installed, and a case needs to be logged into Dynamics 365 Customer Service Hub. 
- Because the company is a Gold customer, the case needs to be routed to the Gold queue. 
- You need to find the case and pick it so you can work on it.

**Task one**: Create the case.

1. Go to **Service** and then select **Cases**.
1. Select **New Case**. 
1. For **Case title** enter “Printer Issue”.
1. For **Customer** enter “Coho Consulting”.
1. For **Contact** enter “Wendy Smith”.
1. For **Origin** enter “Phone”.
1. For **Service Level** enter “Gold”.
1. Select **Save**.

**Task two**: Route the case to the Gold Queue.
- One the Command Bar, select **Save** and the **Route**. 

**Task three**: Work on the case. You need to locate the case in the Gold Queue, and Pick it so you can work on it.
1. Go to **Service** and then select **Queues**.
1. Select a view and a filter to see the items that you want.
1. To see all cases from the selected queue, in the **View** list, select **All Cases in Selected Queues**.
1. In the Queue list, select the **Gold Queue**.
1. Select the case or item that you want to work on, and on the command bar, select **Pick**.