In this exercise, you will learn how to embed the Microsoft Vaccination Management Dashboard into the Vaccination Management model-driven application so that users can access the visualizations from their device. You will first add a dashboard that connects to the Power BI report that you created previously. Then, you will add that dashboard to the site map so that vaccination site managers can quickly access the insights and analytics directly alongside registration data. You will make all changes in the **MVM in a Day** solution for proper management.

1.  Make sure that you are in **Incognito** or **InPrivate** mode and then go to [Power Apps](https://make.powerapps.com/).

2.  Sign in by using the credentials that were supplied in the training for your user.

3.  Select the correct environment from the **Environment** dropdown list in the upper-right corner.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of selecting the environment.](../media/29-environment.png)](../media/29-environment.png)

4.  Select **Solutions** on the left navigation bar. Select the **MVM in a Day** solution to edit.

    > [!div class="mx-imgBorder"]
    > [![Screenshot showing the MVM in a Day solution in the Solutions area.](../media/30-solution.png)](../media/30-solution.png)

5.  Go to **New > Dashboard > Power BI embedded**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the embedded report dashboard.](../media/31-dashboard.png)](../media/31-dashboard.png)

6.  Add dashboard details as follows:

    a.  **Name** - MVM in a Day Report

    b.  **Type** - Power BI report

    c.  **Power BI workspace** - MVM-Dashboard Report

    d.  **Power BI Report** - MVM Dashboard Report

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the new dashboard report view.](../media/32-embed-dashboard.png)](../media/32-embed-dashboard.png)

7.  Select **Save**.

    You should now see the new dashboard in your **MVM In A Day** solution component list.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the list of reports in the dashboard.](../media/33-list.png)](../media/33-list.png)

8.  Select **Add existing > Other > Site map**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the site map to add the new dashboard.](../media/34-site-map.png)](../media/34-site-map.png)

10. Select **Vaccination site management app**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of adding the app to the site map.](../media/35-app.png)](../media/35-app.png)

11. Select **Add**.

12. Select **Vaccination site management app** in the list and then select **Edit**.

    > [!div class="mx-imgBorder"]
    > [![screenshot editing the app within the site map.](../media/36-edit-app.png)](../media/36-edit-app.png)

13. You will be directed to the **Sitemap Designer** page, where you can define the areas, groups, and subareas that are shown in the navigation bar in the model-driven application.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the **Sitemap Designer** page for groups.](../media/37-design.png)](../media/37-design.png)

14. On the **Sitemap Designer** page, select the **Registration** area.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Registration area of the site map.](../media/38-registration.png)](../media/38-registration.png)

15. Select **+ Add > Group**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot for the new group in the site map.](../media/39-new-group.png)](../media/39-new-group.png)

16. You can also drag and drop from the **Components** area onto the canvas.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of adding a component to the site map.](../media/40-component.png)](../media/40-component.png)

17. In the **Title** field, enter **Dashboards** as the new group title.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the new group for the dashboard.](../media/41-group-dashboard.png)](../media/41-group-dashboard.png)

18. While in the new **Dashboards** group, select **+ Add > Subarea**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Subarea selection in the dashboard.](../media/42-sub-area.png)](../media/42-sub-area.png)

19. Enter the following details for your new subarea:

    a.  **Type** - Dashboard

    b.  **Default Dashboard** - MVM in a Day Report (The dashboard that you created in this exercise.)

    c.  **Title** - Vaccination Management Dashboard

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the subarea that is added for the management report.](../media/43-subarea-add.png)](../media/43-subarea-add.png)

20. Select **Save** and then **Publish**.

21. Now, the site map has a new subarea called **Dashboards** in the **Registration** area, with the MVM Dashboard Report embedded and accessible from the site map.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of accessing the site map.](../media/44-site-map-access.png)](../media/44-site-map-access.png)

22. Select **Save and Close** or close the browser window.

23. Return to the **MVM in a Day** solution in Power Apps. Two new rows should now show: the **Vaccination site management app** row, with **site map** listed as its type, and the **MVM in a Day Report** row, with **Power BI embedded** shown as its type. Select **Publish all customizations** while in your **MVM in a Day** solution.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the MVM customizations publication.](../media/45-publish.png)](../media/45-publish.png)

24. Go to **Apps > Vaccination site management app**. Select the name of the app or select **Play** to open it.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the new app list for vaccinations.](../media/46-app-list.png)](../media/46-app-list.png)

25. By default, the application will open in the **Management** area. In the lower-left corner, change the dropdown area to **Registration**, where you previously added the **Dashboards** group and the **Vaccination Management Dashboard** subarea.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Registration page for the subarea.](../media/47-registration.png)](../media/47-registration.png)

26. After you have changed the area to **Registration**, the **site map** will appear on the left and will include the new **Dashboards** area.

27. Select **Dashboard Report** on the left to go to the Power BI embedded report. After the report has loaded, you will see the report embedded directly as a dashboard in the **Vaccination site management** app.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the completed report view in the dashboard.](../media/48-report-view.png)](../media/48-report-view.png)

Congratulations, you have successfully embedded the Microsoft Vaccination Management Dashboard Power BI report as a dashboard in the **Vaccination site management** model-driven application.

