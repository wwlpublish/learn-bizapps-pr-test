## Exercise – Create a Microsoft IoT Central application

In this exercise, you'll build an Internet of Things (IoT) solution by using Microsoft IoT Central to integrate with the smart trash containers that are built by Contoso. As part of this exercise, you'll set up the telemetry, including tracking events that are generated when a customer requests on-demand pickup of a container.

### Start the Microsoft IoT Central trial

1. Open the Microsoft Azure portal [https://portal.azure.com](https://portal.azure.com), and select **Create a resource**.

    ![Create a resource button](../media/1-ic-unit2.png)

2. Search for *IoT Central*, and select **IoT Central Application** in the search results.

    ![IoT Central Application](../media/2-ic-unit2.png)

3. Select **Create**.

    ![Create button](../media/3-ic-unit2.png)

4. In the **Application Name** field, enter *Smart Trash Can*.
5. In the **Application URL** field, enter a unique URL in the form *smarttrashcan\<date\>\<initials\>*.
6. In the **Pricing tier** field, select *Free 30-Day trial*.
7. In the **Subscription** field, select your subscription.
8. Select **Create new** beneath the **Resource group** field.

    ![Create new button](../media/4-ic-unit2.png)

9. In the **Name** field, specify *smarttrashcontainerlab*, if it's available, and then select **OK**.

    ![New smarttrashcontainerlab resource group](../media/5-ic-unit2.png)

10. In the **Location** field, select a location that's close to your Microsoft Dynamics 365 location.
11. Select **Create**.
12. After the deployment is finished, go to the resource, and select the URL in the **IoT Central Application URL** field.

    ![IoT Central Application URL field](../media/6-ic-unit2.png)

### Create a device template

1. Select the **Create Device Templates** tile.

    ![Create Device Templates tile](../media/7-ic-unit2.png)

2. Enter *Smart Trash Container* as the name of the template, and then select **Create**.

    ![New device template](../media/8-ic-unit2.png)

### Create a telemetry measurement

1. Select **New Measurement**.

    ![New Measurement button](../media/9-ic-unit2.png)

2. Select **Telemetry**.

    ![Telemetry](../media/10-ic-unit2.png)

3. In the **Display Name** field, enter *Percent Full*.
4. In the **Field Name** field, enter *percentfull*.
5. In the **Units** field, enter *percent*.
6. In the **Minimum** field, enter *0*.
7. In the **Maximum** field, enter *100*.
8. In the **Decimal** field, enter *0*.
9. In the **Color** field, select any color.
10. Select **Save**.

    ![Percent Full measurement](../media/11-ic-unit2.png)

### Create a state measurement

1. Select **New Measurement**.

    ![New Measurement button](../media/12-ic-unit2.png)

2. Select **State**.

    ![State](../media/13-ic-unit2.png)

3. In the **Display Name** field, enter *Lid Sate*.
4. In the **Field Name** field, enter *lidstate*.
5. Select the **Add Value** button (the plus sign).

    ![Lid State measurement](../media/14-ic-unit2.png)

6. In the **Value** field, select *Open*.
7. In the **Display Name** field, enter *Open*.
8. In the **Color** field, select red.
9. Select the **Add Value** button (the plus sign).

    ![Open values](../media/15-ic-unit2.png)

10. In the **Value** field, select *Closed*.
11. In the **Display Name** field, enter *Closed*.
12. In the **Color** field, select green.

    ![Closed values](../media/16-ic-unit2.png)

13. Select **Save**.

    ![Save button](../media/17-ic-unit2.png)
 
### Create a new event

1. Select **New Measurement**.

    ![New Measurement button](../media/18-ic-unit2.png)

2. Select **Event**.

    ![Event](../media/19-ic-unit2.png)

3. In the **Display Name** field, enter *Ready for Pickup*.
4. In the **Field Name** field, enter *readyforpickup*.
5. In the **Default Severity** field, enter *Information*.
6. Select **Save**.

    ![Ready for Pickup event](../media/20-ic-unit2.png)

### Add a setting for odor control

1. On the **Settings** tab, set the **Design Mode** option to *Yes*.

    ![Design Mode option](../media/21-ic-unit2.png)

2. Select **Number**.

    ![Number](../media/22-ic-unit2.png)

3. In the **Display Name** field, enter *Odor Control Level*.
4. In the **Field Name** field, enter *ocl*.
5. In the **Number of Decimal Places** field, enter *0*.
6. In the **Minimum** field, enter *0*.
7. In the **Maximum** field, enter *3*.
8. Select **Save**.

    ![Odor Control Level setting](../media/23-ic-unit2.png)

### Add a property for the trash container location

1. On the **Properties** tab, set the **Design Mode** option to *Yes*.

    ![Design Mode option](../media/24-ic-unit2.png)

2. Select **Location**.

    ![Location](../media/25-ic-unit2.png)

3. In the **Display Name** field, enter *Container Location*.
4. In the **Field Name** field, enter *location*.
5. In the **Initial Value** field, enter *Microsoft, 1 Microsoft Way, Redmond, WA 98052*.
6. Set the **Required** option to *Yes* to make the address required.
7. Select **Save**.

    ![Container Location property](../media/26-ic-unit2.png)

## Exercise – Build a sample dashboard

Now that your device template is built, you'll customize the dashboard for devices to make it more useful.

### Add basic elements to the dashboard

1. On the **Dashboard** tab, set the **Design Mode** option to *Yes*.

    ![Design Mode option](../media/27-ic-unit2.png)

2. Select **Event List**.

    ![Event List](../media/28-ic-unit2.png)

3. In the **Title** field, enter *Pickup Requests*.
4. Select **Ready for Pickup**.

    ![Pickup Requests event list](../media/29-ic-unit2.png)

5. Select **Save**.

    ![Save button](../media/30-ic-unit2.png)

6. Select **Map**.

    ![Map](../media/31-ic-unit2.png)

7. In the **Title** field, enter *Container Location*.
8. In the **Geography Properties** field, select *Container Location.*
9. Select **Save**.

    ![Container Location map](../media/32-ic-unit2.png)

10. Select **Settings and Properties**.

    ![Settings and Properties](../media/33-ic-unit2.png)
 
11. In the **Title** field, enter *Order Level*.
12. Select **Add/Remove**.

    ![Order Level settings and properties](../media/34-ic-unit2.png)

13. In the **Available Columns** list, select **Odor Control Level**, and then select the **Add** button (**\>**) to add it to the **Selected Columns** list.

    ![Add button](../media/35-ic-unit2.png)

14. Select **OK**.
15. Select **Save**.

    ![Save button](../media/36-ic-unit2.png)

16. Add any other controls that you want.
17. When you've finished, set the **Design Mode** option to **No** to turn off Design mode.

    ![Design Mode option](../media/37-ic-unit2.png)

    Your dashboard should now resemble the following image.

    ![Final dashboard](../media/38-ic-unit2.png)
