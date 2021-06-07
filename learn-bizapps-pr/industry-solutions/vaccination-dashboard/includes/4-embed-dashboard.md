In this exercise, you will learn how to embed the Vaccination Management Dashboard into the Vaccination Management model-driven application so that users can access the visualizations right from their device. You will first add a Dashboard that connects to the Power BI report you created previously. Then we will add that Dashboard to the Sitemap so vaccination site managers can quickly access the insights and analytics directly alongside registration data. We will make all changes in the MVM in a Day solution for proper management.

1.  Navigate to [Power Apps](https://make.powerapps.com/) (Incognito or InPrivate session).

2.  Log in using the credentials supplied in the training for your user.

3.  Select the correct environment from the upper right **Environment** drop-down.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of selecting the environment](../media/29-environment.png)](../media/29-environment.png)

4.  Select **Solutions** on the left navigation bar. Select **MVM in a Day** solution to **edit**.

    > [!div class="mx-imgBorder"]
    > [![Graphical user interface, table Description automatically generated](../media/30-solution.png)](../media/30-solution.png)

5.  Go to **New** > **Dashboard** > **Power BI embedded**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the embedded report dashboard.](../media/31-dashboard.png)](../media/31-dashboard.png)

6.  Add Dashboard details as follows:

    a.  **Name**: MVM in a Day Report

    b.  **Type**: Power BI report

    c.  **Power BI workspace**: MVM-Dashboard Report

    d.  **Power BI Report**: MVM Dashboard Report

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the new dashboard report view.](../media/32-embed-dashboard.png)](../media/32-embed-dashboard.png)

7.  Select **Save**.

8.  You should now see the new Dashboard in your MVM in a Day Solution component list.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the list of reports in teh dashboard.](../media/33-list.png)](../media/33-list.png)

9.  Select **Add Existing** > **Other** > **Site map**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the site map to add the new dashboard.](../media/34-site-map.png)](../media/34-site-map.png)

10. Select the **Vaccination site management app.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of adding the app to the site map.](../media/35-app.png)](../media/35-app.png)

11. Select **Add**.

12. Select the **Vaccination site management app** in the list and select **Edit.**

    > [!div class="mx-imgBorder"]
    > [![screenshot editing the app within the site map.](../media/36-edit-app.png)](../media/36-edit-app.png)

13. You will be landed in the site map designer. This is where you can define the areas, groups, and subareas shown in the navigation bar in the model-driven application.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the site map designer for groups.](../media/37-design.png)](../media/37-design.png)

14. In the site map designer, select the **Registration** area.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the registration area of the site map.](../media/38-registration.png)](../media/38-registration.png)

15. Select **New** > **Group**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot fo the new group in the site map.](../media/39-new-group.png)](../media/39-new-group.png)

16. You can also drag and drop from the right-hand side **Components** area onto the canvas.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of adding a component to the site map.](../media/40-component.png)](../media/40-component.png)

17. Title the new group **Dashboards**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the new group for the dashboard.](../media/41-group-dashboard.png)](../media/41-group-dashboard.png)

18. While selected on the new Dashboards group, select **Add** > **Subarea**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the sub-area in the dashboard.](../media/42-sub-area.png)](../media/42-sub-area.png)

19. Enter the following details for your new subarea:

    a.  **Type**: Dashboard

    b.  **Default Dashboard**: MVM in a Day Report (The dashboard you created in this exercise)

    c.  **Title**: Vaccination Management Dashboard

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the sub-area added for the management report.](../media/43-subarea-add.png)](../media/43-subarea-add.png)

20. Select **Save**. Then select **Publish**.

21. Now the Sitemap has a new subarea called Dashboards in the Registration area with the MVM Dashboard Report embedded and accessible from the sitemap.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of accessing the site map.](../media/44-site-map-access.png)](../media/44-site-map-access.png)

22. Select **Save and Close** or close the browser window.

23. Navigate back to the MVM in a Day solution in Power Apps. You should now see the two other rows for the Vaccination site management app site map and MVM in a Day Report embedded Power BI. Select **Publish all customizations** while in your MVM in a Day solution.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the MVM customizations publication.](../media/45-publish.png)](../media/45-publish.png)

24. Navigate to **Apps** > **Vaccination site management app**. Select the name or select **Play** to open it.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the new app list for vaccinations.](../media/46-app-list.png)](../media/46-app-list.png)

25. The application will by default open in the Management area. In the bottom-left corner, change the drop-down area to **Registration**. This is where we added the Dashboards group and Vaccination Management Dashboard subarea.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the registration page for the subarea.](../media/47-registration.png)](../media/47-registration.png)

26. Once the area is changed to Registration, you will see the **site map** on the left, which includes the new Dashboards area.

27. Select **Dashboard Report** on the left to navigate to the Power BI embedded report. Once loaded, you will see the report embedded directly as a dashboard in the vaccination site management app.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of completed report view in the dashboard.](../media/48-report-view.png)](../media/48-report-view.png)

**Congratulations!** You successfully embedded the MVM Vaccination Management Dashboard Power BI Report as a Dashboard in the Vaccination site management model-driven application.

