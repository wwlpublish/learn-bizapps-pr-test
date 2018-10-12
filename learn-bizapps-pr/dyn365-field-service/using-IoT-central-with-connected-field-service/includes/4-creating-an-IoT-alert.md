## Exercise – Create an IoT Alert

### Create a flow

In this task, you'll create a flow that will register a device.

1. In Microsoft Dynamics 365, select the drop-down arrow next to **Dynamics 365**, and then select **Connected Field Service**.

    ![Connected Field Service](../media/1-ic-unit4.png)

2. Select the **Site Map** button to expand the navigation, and select **Customer Assets**.

    ![Customer Assets](../media/2-ic-unit4.png)

3. Select **Flow**, and then select **Create a flow**.

    ![Creat a flow](../media/3-ic-unit4.png)

4. Select **Sign in**.

    ![Sign in button](../media/4-ic-unit4.png)

5. Enter your credentials.
6. On the **My flows** tab, select **Create from blank**.

    ![Create from blank button](../media/5-ic-unit4.png)

7. Select **Create from blank** again.

    ![Create from blank button](../media/6-ic-unit4.png)

8. Search for *Common Data Service*, and select **Common Data Service – When a record is selected** in the search results.

    ![Common Data Service – When a record is selected](../media/7-ic-unit4.png)

9. In the **Organization Name** field, select *Default*.
10. In the **Entity Name** field, select *Customer Assets*.
11. Select **+New step**.

    ![New step button](../media/8-ic-unit4.png)

12. Select **Add an action**.

    ![Add an action](../media/9-ic-unit4.png)

13. Search for *Create a device*, and select **Azure IoT Central – Create a device** in the search results.

    ![Azure IoT Central – Create a device](../media/10-ic-unit4.png)

14. Select **Sign in**.

    ![Sign in button](../media/11-ic-unit4.png)

15. Sign in by using the credentials that you used to create the Microsoft IoT Central application.
16. Select **Accept**.

    ![Accept button](../media/12-ic-unit4.png)

17. In the **Application** field, enter *Smart Trash Can*.
18. In the **Device Template** field, select the template that you created.
19. Click in the **Display Name** field, and then select **Name** on the **Dynamic content** tab.

    ![Name](../media/13-ic-unit4.png)

20. In the **Device Simulated** field, select *Yes*.
21. Select **+New step**, and then select **Add an action**.

    ![Add an action](../media/14-ic-unit4.png)

22. Search for *Common Data Service*, and select **Common Data Service - Update a record** in the search results.

    ![Common Data Service - Update a record](../media/15-ic-unit4.png)

23. In the **Organization Name** field, enter *Default*.
24. In the **Entity Name** field, enter *Customer Assets*.
25. Click in the **Record identifier** field, and then select **Customer Asset** on the **Dynamic content** tab.

    ![Customer Asset](../media/16-ic-unit4.png)

26. Select **Show advanced options**.

    ![Show advanced options button](../media/17-ic-unit4.png)

27. Click in the **Device ID** field, and then select **Device ID** on the **Dynamic content** tab.

    ![Device ID](../media/18-ic-unit4.png)

28. Select **+New step**, and then select **Add an action**.

    ![Add an action](../media/19-ic-unit4.png)

29. Search for *Common Data Service*, and select **Common Data Service - Create a new record** in the search results.

    ![Common Data Service - Create a new record](../media/20-ic-unit4.png)

30. In the **Organization Name** field, enter *Default*.
31. In the **Entity Name** field, enter *IoT Devices*.
32. Click in the **Name** field, and then select **Name** on the **Dynamic content** tab.
33. Select **Show advanced options**.

    ![Show advanced options button](../media/21-ic-unit4.png)

34. Click in the **Device ID** field, and then select **Device ID** on the **Dynamic content** tab.

    ![Device ID](../media/22-ic-unit4.png)

35. Scroll up, and rename the flow *Register Device*.

    ![Register Device](../media/23-ic-unit4.png)

36. Select **Save** to save the flow.

    ![Save button](../media/24-ic-unit4.png)

### Test the registering device

1. Return to your Connected Field Service application, and go to **Customer Assets**.
2. Select **New**.

    ![New button](../media/25-ic-unit4.png)

3. In the **Name** field, enter *Test Device*, and then select **Save**.

    ![Save button](../media/26-ic-unit4.png)

4. Select **Flow**, and then select the flow that you created.

    ![Flow](../media/27-ic-unit4.png)

5. Select **Continue**.

    ![Continue button](../media/28-ic-unit4.png)

6. Select **Done**.

    ![Done button](../media/29-ic-unit4.png)

7. Refresh the page.

    The flow should enter a value in the **Device ID** field.

    ![Device ID field](../media/30-ic-unit4.png)

### Create IoT Alerts

In this exercise, you'll create an IoT Alert for the trash container pickup request.

#### Create Pickup Request Alert 

1. Go to Microsoft IoT Central, and open the left navigation.

    ![Open the navigation](../media/31-ic-unit4.png)

2. Select **Device Explorer**.

    ![Device Explorer](../media/32-ic-unit4.png)

3. Open the device that was created by the flow.

    ![Open the device](../media/33-ic-unit4.png)

4. On the **Rules** tab, select **New Rule**.

    ![New Rule](../media/34-ic-unit4.png)

5. Select **Event**.

    ![Event](../media/35-ic-unit4.png)

6. In the **Name** field, enter *Pickup Requested*, and the select the **Add Conditions** button (the plus sign).

    ![Add Conditions button](../media/36-ic-unit4.png)

7. In the **Measurement** field, select *Ready for Pickup*, and then select **Save**.

    ![Save button](../media/37-ic-unit4.png)

8. Select the **Add Actions** button (the plus sign).

    ![Add Actions button](../media/38-ic-unit4.png)

9. Select **Microsoft Flow**.

    ![Microsoft Flow](../media/39-ic-unit4.png)

10. Select **Sign in**.

    ![Sign in button](../media/40-ic-unit4.png)

11. On the **My flows** tab, select **Create from blank**.

    ![Create from blank button](../media/41-ic-unit4.png)

12. Select **Create from blank** again.

    ![Create from blank button](../media/42-ic-unit4.png)

13. Search for *IoT Central*, and select **Azure IoT Central - When a rule is fired** in the search results.

    ![Azure IoT Central - When a rule is fired](../media/43-ic-unit4.png)

14. In the **Application** field, select *Smart Trash Can*.
15. In the **Rule** field, select *Pickup Requested*.
16. Select **+New step**.

    ![New step button](../media/44-ic-unit4.png)

17. Select **Add an action**.

    ![Add an action](../media/45-ic-unit4.png)

18. Search for *Common Data Service*, and select **Common Data Service - List records** in the search results.

    ![Common Data Service - List records](../media/46-ic-unit4.png)

19. In the **Organization Name** field, select *Default*.
20. In the **Entity Name** field, select *Customer Assets*.
21. Select **Show advanced options**.

    ![Show advanced options button](../media/47-ic-unit4.png)

22. In the **Filter Query** field, enter *msdyn_deviceid eq ''*, and then put the curser inside the single quotation marks.

    ![Filter Query field](../media/48-ic-unit4.png)

23. On the **Dynamic content** tab, select **Device ID**.

    ![Device ID](../media/49-ic-unit4.png)

24. Select **New Step**, select **More**, and then select **Add an apply to each**.

    ![Add an apply to each](../media/50-ic-unit4.png)

25. On the **Dynamic content** tab, select **value**.

    ![value](../media/51-ic-unit4.png)

26. Select **Add an action**.

    ![Add an action button](../media/52-ic-unit4.png)

27. Search for *Common Data Service*, and select **Common Data Service - Create a new record** in the search results.

    ![Common Data Service - Create a new record](../media/53-ic-unit4.png)

28. In the **Organization Name** field, enter *Default*.
29. In the **Entity Name** field, enter *IoT Alerts*.
30. Click in the **Description** field.

    ![Description field](../media/54-ic-unit4.png)

31. On the **Dynamic content** tab, select **Device Name**. Then, in the **Description** field, type a hyphen (*-*) after it.

    ![Device Name](../media/55-ic-unit4.png)

32. On the **Dynamic content** tab, select **Rule Name**, and then select **Show advanced options**.

    ![Show advanced options button](../media/56-ic-unit4.png)

33. Click in the **Alert Data** field, and then select the **Expression** tab.

    ![Expression tab](../media/57-ic-unit4.png)

34. Enter *utcNow()*, and then select **OK**.

    ![OK button](../media/58-ic-unit4.png)

35. Click in the **Alert Time** field, and then select **Timestamp** on the **Dynamic content** tab.

    ![Timestamp](../media/59-ic-unit4.png)

36. Click in the **Device ID** field, and then select **Device ID** on the **Dynamic content** tab.

    ![Device ID](../media/60-ic-unit4.png)

37. Click in the **Customer Asset** field, and then select **Customer Asset** on the **Dynamic content** tab.

    ![Customer Asset](../media/61-ic-unit4.png)

38. Scroll up, and rename the flow *Create Alerts*.

    ![Create Alerts](../media/62-ic-unit4.png)

39. Select **Save** to save the flow.

    ![Save button](../media/63-ic-unit4.png)

#### Test alerts

1. Return to Microsoft IoT Central, open the test device that was created by the flow, and then select the **Measurements** tab.

    ![Measurements tab](../media/64-ic-unit4.png)

    The simulator should generate a new pickup request every few minutes.

    ![Pickup requests in the simulator](../media/65-ic-unit4.png)

2. Go to your Connected Field Service application.
3. On the **Menu** button, select **IoT Alerts**.

    ![IoT Alerts](../media/66-ic-unit4.png)

    You should see the alerts that are generated by the simulator.

    ![Alerts generated by the simulator](../media/67-ic-unit4.png)
