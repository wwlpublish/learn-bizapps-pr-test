## Exercise Creating and IoT Alert


## Create Flow

In this task, you will create a flow that will register device.

1: Go to your Dynamics 365, switch to another app and click **Connected Field Service**.

![Connected field service](../media/1-ic-unit4.png)

2: Click left navigation and then click **Customer Assets**.

![Customer Assets](../media/2-ic-unit4.png)

3: Click **Flow** and select “Create a flow”.

![Flow](../media/3-ic-unit4.png)

4:Click **Sign in**.

![Flow](../media/4-ic-unit4.png)

5: Provide your credentials.

6: Click **My flows**, and then click **Create from blank**.

![My Flows](../media/5-ic-unit4.png)

7: Click **Create from blank** again.

![Create from blank](../media/6-ic-unit4.png)

8: Search for “Common Data Service” and select “Common Data Service – When a record is selected”.

![Common data service](../media/7-ic-unit4.png)

9: Select “Default” in the **Organization Name** field, “Customer Assets” in the **Entity Name** field, and then click **New step**.

![default](../media/8-ic-unit4.png)

10: Click **Add an action**.

![add an action](../media/9-ic-unit4.png)

11: Search for “Create a device” and select “Azure IoT Central – Create a device”.

![create a device](../media/10-ic-unit4.png)

12: Click **Sign in**.

![sign in](../media/11-ic-unit4.png)

13: Sign in with the credentials you used to create the Azure IoT Central application.

14: Click **Accept**.

![Accept](../media/12-ic-unit4.png)

15: Type “Smart Trash Can” in the **Application** field, select the template you created, click the **Display Name** and select “Name” from the **Dynamic content** window.

![Display](../media/13-ic-unit4.png)

16: Select “Yes” in the **Device Simulated** field.

17: Click **New step** and click **Add an action**.

![New step](../media/14-ic-unit4.png)

18: Search for “Common Data Service” and select “Common Data Service - Update a record”.

![update a record](../media/15-ic-unit4.png)


19: Type “Default” in the **Organization Name** field, “Customer Assets” in the **Entity Name** field, click the **Record Identifier** field, and select “Customer Asset”.

![customer asset](../media/16-ic-unit4.png)

20: Click **Show advanced options**.

![show advanced options](../media/17-ic-unit4.png)


21: Click on the **Device ID** field and select “Device ID”.

![device id](../media/18-ic-unit4.png)

22: Click **New step** and select “Add an action”.

![add action](../media/19-ic-unit4.png)

23: Search for “Common Data Service” and select “Common Data Service - Create a new record”.

![create a new record](../media/20-ic-unit4.png)

24: Provide the information below and click **Show advanced options**.

![advanced options](../media/21-ic-unit4.png)

25: Provide Device ID.

![Device ID](../media/22-ic-unit4.png)

26: Scroll up and rename the flow Register Device

![Flow register device](../media/23-ic-unit4.png)

27: Save the flow.

![Save flow](../media/24-ic-unit4.png)


## Test Registering Device 


1: Return to your Connected Field Service application and navigate to **Customer Assets**.

2: Click **New**.

![New](../media/25-ic-unit4.png)

3: Type “Test Device” in the **Name** field, and then click **Save**.

![Test device](../media/26-ic-unit4.png)

4: Click **Flow** and select the flow you created.

![Flow](../media/27-ic-unit4.png)

5: Click **Continue**.

![Continue](../media/28-ic-unit4.png)

6: Click **Done**.

![Done](../media/29-ic-unit4.png)

7: Refresh the page.

8: The flow should populate the **Device ID** field.

![Device ID](../media/30-ic-unit4.png)


## Create IoT Alerts 

In this exercise, you will create an IoT alert for the trash container pickup request

### Create Pickup Request Alert 

1: Go to your Azure IoT Central and open the left navigation.

![Azure IOT central](../media/31-ic-unit4.png)
 
2: Click **Device Explorer**.

![Device explorer](../media/32-ic-unit4.png)

3: Open the device created by the flow.

![Open Device](../media/33-ic-unit4.png)

4: Click the **Rules** tab and click **New Rule**.

![New rule](../media/34-ic-unit4.png)

5: Click **Event**.

![Event](../media/35-ic-unit4.png)
 
6: Type “Pickup Requested” in the **Name** field, and the click **add Conditions**.

![add condition](../media/36-ic-unit4.png)
 
7: Select “Ready for Pickup“ in the **Measurement** field and click **Save**.

![measurement](../media/37-ic-unit4.png)

8: Click **add Actions**.

![add action](../media/38-ic-unit4.png)

9: Click **Microsoft Flow**.

![Microsoft flow](../media/39-ic-unit4.png)

10: Click **Sign in**.

![sign in](../media/40-ic-unit4.png)
 
11: Click the **My flows** tab and then click **Create from blank**.

![create from blank](../media/41-ic-unit4.png)

12: Click **Create from blank** again.

![create from blank again](../media/42-ic-unit4.png)
 
13: Search for “IoT Central” and select “Azure IoT Central - When a rule is fired”.

![when a rule is fired](../media/43-ic-unit4.png)

14: Select “Smart Trash Can” in the **Application** field, “Pickup Requested” in the **Rule** field, and then click **New step**.

![new step](../media/44-ic-unit4.png)
 
15: Click **Add an action**.

![add action](../media/45-ic-unit4.png)

16: Search for “Common Data Service“ and select “Common Data Service - List records”.

![list records](../media/46-ic-unit4.png)
 
17: Select “Default” in the **Organization Name** field, “Customer Assets” in the **Entity Name** field, and then click **Show advanced options**.

![entity name](../media/47-ic-unit4.png)
 
18: Type “msdyn_deviceid eq ‘’ and place your curser inside the single quotation marks.

![msdyn device](../media/48-ic-unit4.png)
 
19: Select “Device ID”.

![device id](../media/49-ic-unit4.png)

20: Click **New Step**, **More**, and select “Add an apply to each”.

![add an apply](../media/50-ic-unit4.png)
 
21: Select “value”.

![select value](../media/51-ic-unit4.png)
 
22: Click **Add an action**.

![add an action](../media/52-ic-unit4.png)

23: Search for “Common Data Service” and select “Common Data Service - Create a new record”.

![create a new record](../media/53-ic-unit4.png)
 
24: Type “Default” in the **Organization Name** field, “IoT Alerts” in the **Entity Name** field, and then click **Description**.

![IOT alerts](../media/54-ic-unit4.png)

25: Select “Device Name” and type “-“ at the end of it.

![device name](../media/55-ic-unit4.png)
 
26: Select “Rule Name” and click **Show advanced options**.

![rule name](../media/56-ic-unit4.png)

27: Click the **Alert Data** field and click the **Expression** tab.

![alert data](../media/57-ic-unit4.png)
 
28: Type “utcNow()” and click **OK**.

![click ok](../media/58-ic-unit4.png)

29: Click the **Alert Time** field and select “Timestamp”.

![timestamp](../media/59-ic-unit4.png)
 
30: Locate the **Device ID** field and select “Device ID”.

![Device ID](../media/60-ic-unit4.png)
 
31: Locate the **Customer Asset** field and select “Customer Asset”.

![Customer asset](../media/61-ic-unit4.png)

32: Rename the flow "Create Alerts".

![rename create alerts flow](../media/62-ic-unit4.png)
 
33: Save the flow.

![save flow](../media/63-ic-unit4.png)


### Test Alerts 


1: Return to your Azure IoT Central, open the Test Device created by the flow, and click the **Measurements** tab.

![measurements tab](../media/64-ic-unit4.png)
 
2: The simulator should generate a new Pickup Request every few minutes.

![pickup request simulator](../media/65-ic-unit4.png)

3: Go to your Connected Field Service application.

4: Click the **Menu** button and then click **IoT Alerts**.

![connected field service app](../media/66-ic-unit4.png)

5: You should see the alerts generated by the simulator.


![alerts generation](../media/67-ic-unit4.png)