The Labs and exercises in this module work best when you have some sample data to work with. Depending on if the environment you are working with, you may want to install some sample data to assist with exercises. Dynamics 365 does provide the ability to add sample data as needed. If the environment you are working in does not have any sample data installed, follow the steps below to install the sample data into your environment.

### Enable Sample Data -- Detailed Steps:
1. If necessary, on the main application Navigation Bar, click the drop-down selector next to Dynamics 365 and then click Dynamics 365 -- custom.
2. From the navigation bar, navigate to Settings \> Data Management
3. Select Sample Data.
4. Click the Install Sample Data button.
5. Close the Sample Data window.

## Exercise Overview

Several paragraphs -- or longer -- describing an overview of the lab
including a description of the lab and why certain topics are covered.
This is also called the 'LAB ABSTRACT' that will be used for hand-off to
conferences as part of the content hand-off process

### Scenario

Your company wants to better leverage Dynamics 365's queue
functionality. They want to ensure that all agents have access to a
Queue call support. The support queue will be where most cases will be
directed to. Agents should know how to place items into the queue, claim
responsibility for items on the queue, and resolve items. This exercise
will demonstrate that information to you.

### Learning Objectives

At the end of these exercises, you will be able to accomplish the
following:
-   Create Dynamics 365 Queues.
-   Use Queues to Resolve Cases.

Estimated time to complete this lab: 15 to 20 minutes

### High Level Steps:

-   Create Queues for:
    -   Support
    -   Gold
    -   Silver
    -   Bronze
-   Work through a Queue Item's Lifecycle.

### Detailed Steps:

#### Create the Support, Gold, Silver, and Bronze Queues:

1.  Navigate to Service Management and select Case Settings Queues.
2.  Click the New button to create a Queue.
3.  Configure the Queue as follows:
    -   Name: Support
    -   Type: Public
4.  Save and Close the Support Queue
5.  Click the New button to create a Queue.
6.  Configure the Queue as follows:
    -   Name: Gold
    -   Type: Public
7.  Save and Close the Gold Queue
8.  Repeat Steps 5 through 6 to create a Silver and Bronze queue.

#### Use Queues to manage Queue Items:

1.  If necessary, navigate to the Customer Service Hub application.
2.  Using the Site Map, click the Wrench to select cases.
3.  In the list of My Active Cases, click to select the Information on the Product (sample) case.
4.  Hold down the CTRL key on your keyboard and select the check the following cases
    -   Damaged during shipment (sample)
    -   Shipping Time information (sample)
5.  On the command bar, select Add to Queue.
6.  In the Queue field, select the Support queue, and then select Add
7.  Using the Customer Service Hub Site Map, navigate to Queues.
8.  Using the drop-down arrow, change the queue filter to Support.
9.  Using the drop-down arrow, change the Queue Item Filter view to Cases Available to Work On.
10. Click the check mark column next to the Information on the product (sample) case title to select it.
11. On the command bar, click the Pick button.
12. On the pick screen, confirm the selection by clicking the Pick button.
13. Using the drop-down arrow, change the queue item filter view to Cases I am Working On.
14. Open the Information on the product (sample) case.
15. On the Timeline, click the Add info and Activities button.
16. From the menu that appears select Phone Call.
17. Configure the Phone Call as follows:
    -   Subject: Checking in with Tom 
    -   Leave everything else alone.
18. Click Save
19. Using the Customer Service Hub Site Map, navigate to Queues.
20. Change the items that are displayed to:
- Filter Item: Cases I am Working On
- Queue Filter: Support
21. Click the check mark column next to the Information on the product (sample) case title to select it.
22. On the Command Bar, click the release button.
23. Using the drop-down arrow, change the queue item filter view to Cases available to Work On.
24. Click the check mark column next to the Information on the product (sample) case title to select it.
25. On the command bar, click the Pick button.
26. On the pick screen, confirm the selection by clicking the Pick button.
27. Using the drop-down arrow, change the queue item filter view to Cases I am Working On.
28. Open the Information on the product (sample) case.
29. On the command bar, click the Resolve Case button:
30. On the Resolve a Case resolution window, in the Resolution field, type Talked to customer and sent a new part.
31. In Billable Time, type 1 Hour.
32. Click Resolve to resolve the case.
33. Using the Customer Service Hub Site Map, navigate to Queues.
34. Change the items that are displayed to:
    -   Filter Item: All Items
    -   Queue Filter: Support
35. Notice that the Information on the product (sample) is no longer in the support queue.
36. Change the queue filter to all queues.
37. Notice it is no longer in any queue since it has been resolved.
