## Exercise – Identify exceptions

### Exercise 1: Azure Cosmos DB
In this exercise, you'll create the Microsoft Azure Cosmos DB database that you'll use in the next exercise. This database will be used to store detail telemetry from the device.

**Scenario**

The data that comes in from our physical device is in a different format than the data from our simulated device. Therefore, you must change the Azure Stream Analytics job to work with the data from our physical device. You'll also adjust the Stream Analytics job so that it stores the data in an Azure Cosmos DB in addition to evaluating it for anomalies.

#### Task 1: Create the Azure Cosmos DB

1. Go to your Azure portal, and select **Create a resource**.

    ![Create a resource](../media/1-ie-unit4.png)

2. Search for *Azure Cosmos DB*, and select it in the search results.

    ![Azure Cosmos DB](../media/2-ie-unit4.png)

3. Select **Create**.

    ![Create button](../media/3-ie-unit4.png)

4. Enter a unique ID, select *SQL* as the application programming interface (API), select your subscription, resource group, and location, and then select **Create**.

    ![Create button](../media/4-ie-unit4.png)

5. Wait for the Azure Cosmos DB to be created.
6. Open the Azure Cosmos DB that you just created, select **Data Explorer**, and then select **New Database**.

    ![New Database button](../media/5-ie-unit4.png)

7. In the **Database id** field, enter *Telemetry*, and then select **OK**.

    ![OK button](../media/6-ie-unit4.png)

8. Select the ellipsis button (**…**) for the database that you created.

    ![Ellipsis button](../media/7-ie-unit4.png)

9. Select **New Collection**.

    ![New Collection](../media/8-ie-unit4.png)

10. In the **Collection Id** field, enter *DeviceData*, change the **Throughput** value to *400*, and then select **OK**. We're changing the throughput to minimize cost.

    ![OK button](../media/9-ie-unit4.png)
 
### Exercise 2: Adjust the Stream Analytics job
In this exercise, you'll change the Stream Analytics job to accommodate the different telemetry that's sent by your MXChip device.

#### Task 1: Add an Azure Cosmos DB as output

1. Select **Resource groups**, and open the resource group that you created.

    ![Resource group](../media/10-ie-unit4.png)

2. Find and open the Stream Analytics job.

    ![Steam analytics job](../media/11-ie-unit4.png)

3. The Stream Analytics job must be stopped before you can change its query and input/outputs. Select **Stop**.

    ![Stop button](../media/12-ie-unit4.png)

4. Select **Yes**.
5. After the job is stopped, select **Outputs**.

    ![Outputs](../media/13-ie-unit4.png)

6. Select **Add**, and then select **Cosmos DB**.

    ![Cosmos DB](../media/14-ie-unit4.png)

7. In the **Output alias** field, enter *CosmosDB*.
8. Select your subscription, select the Azure Cosmos DB that you created, and select the database that you created.
9. In the **Collection name pattern** field, enter *DeviceData*.
10. Select **Save**.

    ![Save button](../media/15-ie-unit4.png)

#### Task 2: Adjust the query for the device

1. Select **Query**.

    ![Query](../media/16-ie-unit4.png)

2. Put the cursor at the end of line 14, and press Enter.

    ![Cursor placement](../media/17-ie-unit4.png)

3. Paste the following query snippet. This code will let the query support both the real and simulated devices.

    ```json
    ...
    UNION 
    -- MX Chip 
    SELECT 
        GetMetadataPropertyValue(Stream, '[IoTHUB].[ConnectionDeviceId]') as DeviceID, 
        'Temperature' AS ReadingType, 
        (((Stream.temp *9) / 5)+32) AS Reading, 
        GetMetadataPropertyValue (Stream, 'EventId') as EventToken, 
        Ref.Temperature AS Threshold, 
        Ref.TemperatureRuleOutput AS RuleOutput, 
        Stream.EventEnqueuedUtcTime AS [time] 
    FROM IoTStream Stream
    JOIN DeviceRulesBlob Ref ON Ref.DeviceType = 'Thermostat' 
    WHERE 
        Stream.temp IS NOT NULL AND Stream.temp > Ref.Temperature 
    ...
    ```

    Notice that we're not only adjusting for field names but also converting the temperature from Celsius to Fahrenheit.

    ![Conversion from Celsius to Fahrenheit called out in code](../media/18-ie-unit4.png)

4. Select **Save**.

    ![Save button](../media/19-ie-unit4.png)

5. Select **Yes**.

#### Task 3: Add saved data to the Azure Cosmos DB

1. Add the following snippet to the end of the query. This code will save a copy of the ingested data.

    ```json
    SELECT
        *
    Into CosmosDB
    FROM IoTStream
    ```

    ![Query](../media/20-ie-unit4.png)

2. Select **Save** again.
3. Select **Yes**.
4. Select **Overview**, and then select **Start** to restart the job.

    ![Start button](../media/21-ie-unit4.png)

5. Wait for the Stream Analytics job to be started.
6. Select the resource group.

    ![Resource group](../media/22-ie-unit4.png)

7. Open the Azure Cosmos DB that you created.

    ![Azure Cosmos DB](../media/23-ie-unit4.png)

8. Select **Data Explorer**, expand **Telemetry**, expand **DeviceData**, and select **Documents**.

    ![Documents](../media/24-ie-unit4.png)

9. You should see a list of documents. Select one of the documents.

    ![List of documents](../media/25-ie-unit4.png)

    You should now see sensor data from your device.
