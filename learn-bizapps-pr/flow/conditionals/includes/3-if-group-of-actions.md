The **If** group of Actions is used when one or more conditions should be taken into account in order to determine the Process’ next steps. Let’s examine a relevant example.

Consider the following Process: an Excel file contains incoming support ticket information, including urgency, and the customer’s subscription plan. Based on this information, the Process will determine the ticket’s maximum response time, and write it into the corresponding cell.

First, we open the Excel report and determine the range of the data. Then, we will loop through each row, reading the urgency and subscription plan:

![Read from excel loop](..\media\read-from-excel-loop.png)
Now, for each of these rows, the maximum response time must be calculated. The company’s SLAs are as follows:
* Free users get a response within 30 days of their ticket submission
* Basic users get a response within 7 days
* Premium users get a response within 1 day

Also, any ticket marked as Urgent must receive a response within 12 hours, regardless of the user’s subscription plan.

Since the information needed to figure out the maximum response time comes from more than 1 source, we will use an **If** conditional to decide on it. We begin by assessing the ticket’s urgency, since it overrides the subscription plan in this case:

![If cell contains urgent](..\media\if-cell-contains-urgent.png)
![If cell contains urgent write 12 hours](..\media\if-cell-contains-urgent-write-12-hours.png)

Afterwards, we will proceed to add each individual case as an alternative condition:

![Else if cell contains premium](..\media\else-if-cell-contains-premium.png)

Eventually, the Process will look like this:

![If else if final structure](..\media\if-else-if-final-structure.png)

Now, all scenarios have been covered. However, for whatever reason, there might be a value in the Excel file that is not one of the standard values we expect. In such cases, we would like someone to look into the matter personally. For this reason, we will also add a final alternative:

![If else if else final structure](..\media\if-else-if-else-final-structure.png)

Now, in case of unexpected input, the maximum time will be designated as **Undefined**.
