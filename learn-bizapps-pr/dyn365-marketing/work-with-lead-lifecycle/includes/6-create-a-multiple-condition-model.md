You want to prioritize leads who are Consultants and in the San Francisco area. You want to score the leads automatically to determine the hot leads and invite them to the event. Make sure to set the Job Title (Consultant) grade as 60, San Francisco as 40, and the Sales Ready
grade as 100.

1. Go to **Marketing** > **Lead Management** > **Lead Scoring Model**.
2. Select **New**.
3. On the **Design** tab, drag a **Condition** tile from the **Toolbox** tab.
4. On the **Properties** tab of the condition that you added, enter the **Display name** as **City**.
5. Expand the **Condition** tile.
6. Select the child **Condition** tile, on the **Properties** tab enter the **Display Name** as **San Francisco**.
7. Select the **Entity** field. Choose the **Lead** entity.
8. In the **Expression** box, use the **Field**, **Operator** and **Value** fields to establish an expression that evaluates to true where **City = San Francisco**.
9. On the Toolbox, drag an **Action** tile to the right of the **Condition** tile you set up.
10. On the **Properties** tab for **Action** tile, set **Score  Update** to +40.
11. Add a new rule below the first one and set it to give +60 points to leads with Consultant as Job title.
12. Open the **Grades** tab in the rightmost column. Set this to **100**.
13. Go to the **Summary** tab and give your rule a name.
14. **Save**.
15. Select **Check for Errors**.
16. Select **Go Live** to activate the model.

Now create a lead using the attributes listed above:

1. Go to **Marketing** > **Lead Management** > **Leads**. Select **+ New** to create a new lead.
2. In the **Contact** section, fill out the **Topic**, **First Name**, and **Last Name** fields. Then, fill out Job Title as Consultant.
3. In the **Company** section, set the **City** to **San Francisco**.
4. **Save**
5. When saved, page is refreshed and a business process flow (BPF) is added, several new sections will be added to the body
6. Choose the first step of the business process flow to open its menu and make an assignment in the **Existing Contact** field. Choose any contact (the one you choose isn\'t important for this exercise). Then, save the lead. The associated contact is now listed in the **Stakeholders** section for the lead
7. Look for the Lead Scores section near the lower-right corner of the page. After a few minutes, you should see it shows a score of 100 points.

>[!Note]
>It may take several hours for the calculation to complete.
