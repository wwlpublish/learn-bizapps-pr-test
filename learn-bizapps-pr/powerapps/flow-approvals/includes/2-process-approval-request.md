# Approve a request
In a previous topic, you saw how to build an approval process around tweets that are stored in a SharePoint list.  In this topic, you'll see what the experience looks like when an approver receives a new approval request. 

## Step One: Modify the SharePoint list
First we need to add an item to our SharePoint list, then we can process an approval request for that item.

1. Open the SharePoint list **ContosoTweets**, which was configured in the previous topic.  Select **New** to create a new tweet. 
   
    ![SharePoint list](./media/sharepoint-list-home.png)
2. Add the following values to the fields, and select **Save**.
   
   - For **Title**, enter "Promotions".

   - For **TweetContent**, enter "Check out the new line of Contoso Flooring #ohsocontoso". Notice that the tweet contains a hashtag.
   - For **TweetDate**, enter Today’s date.
     
     ![SharePoint new item](./media/sharepoint-new-tweet.png)

## Step Two: Modify the flow
1. In **Microsoft Flow**, select **My Flows**. 
4. Select the **Post list items to Twitter after approval** flow that was configured in the previous topic, then select the running flow under **RUN HISTORY**.
   
    ![Run history](./media/run-history.png)
5. Select the **When a new item is created** trigger. Verify that the information for the list item you just created is displayed.
   
    ![Flow trigger](./media/approval-flow.png)
6. In **Outlook**, open the automated approval mail in the inbox, and then select **Approve**. 
   
    ![Outlook request](./media/outlook-mail.png)
7. In the **Approval Center**, view the details of the request, add a comment, and select **Confirm**. 
   
    ![Approval center](./media/approval-center.png)
8. In **SharePoint**, refresh the **ContosoTweets** list and verify that **ApprovalStatus** is **Yes**, and the comment that you entered is displayed. 
   
    ![SharePoint refresh list](./media/sharepoint-list-approved.png)

In this topic, you saw the experience from the approver’s point of view - from receiving an approval request email, to processing the request in the Approval Center.

