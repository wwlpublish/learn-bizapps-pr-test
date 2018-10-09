## Exercise – Anomaly detection

### Building a new query
In this hands-on exercise, you'll build a new query to replace the existing query for the Microsoft Azure Stream Analytics job. You'll building this new query incrementally, so that you can see what the parts do. This exercise is designed to work with your physical device. If you don't have a physical device, you can change the query to use fields from the simulated device.

**Scenario**

In this exercise, you'll use the anomaly detection preview feature of Azure Stream Analytics to make an Internet of Things (IoT) Alert more dynamic by changing the logic that's used to generate it.

Currently, an IoT Alert is generated when the temperature from the device reaches the hard-coded limit. By using the anomaly detection capabilities, you'll change the queries for the Azure Stream job so that they detect both upward and downward trends in the temperature. This type of detection is ideal if you want early notification of any change from an expected state, but you don't have a hard-coded value that indicates when the change becomes a problem.

#### Add an anomaly data collection to Azure
To save the detail scores that are generated from the anomaly detection, you must create another collection in the Azure Cosmos DB that we used in Unit 4. This approach will make it easy to see the values that are generated from the anomaly detection operator.

1. Go to your Azure portal, select **Resource groups**, and then open the resource group that you created when you deployed Connected Field Service.

    ![Resource group](../media/1-ie-unit6.png)

2. Open the Azure Cosmos DB that you created.

    ![Azure Cosmos DB](../media/2-ie-unit6.png)

3. Select **Data Explorer**, select the ellipsis button (**…**) for the **Telemetry** database, and then select **New Collection**.

    ![New Collection](../media/3-ie-unit6.png)

4. In the **Collection Id** field, enter *DeviceData*, change the **Throughput** value to *400*, and then select **OK**. We're changing the throughput to minimize cost.

    ![OK button](../media/4-ie-unit6.png)

#### Add a new output
In this task, you'll add a new output for the AnomalyData collection.

1. Close the Azure Cosmos DB blade.

    ![Close button](../media/5-ie-unit6.png)

2. Find and open the Stream Analytics job.

    ![Stream Analytics job](../media/6-ie-unit6.png)

3. The Stream Analytics job must be stopped before you can change its query and input/outputs. Select **Stop**.

    ![Stop button](../media/7-ie-unit6.png)

4. Select **Yes**.
5. After the job is stopped, select **Outputs**, select **Add**, and then select **Cosmos DB**.

    ![Cosmos DB](../media/8-ie-unit6.png)

6. In the **Output alias** field, enter *AnomalyDB*.
7. Select your subscription, select the Azure Cosmos DB that you created, and select the database that you created.
8. In the **Collection name pattern** field, enter *AnomalyDB*.
9. Select **Save**.

    ![Save button](../media/9-ie-unit6.png)

#### Prepare and build the new query

1. Select **Query**.

    ![Query](../media/10-ie-unit6.png)

2. Copy the existing query, and save it in case you want to reference it later.
3. Clear the existing query. You'll build a new one step by step.

    ![Cleared query](../media/11-ie-unit6.png)

4. Paste the following snippet into the Query editor.

    ```json
    ...
    WITH AlertData AS
    ( 
    SELECT 
        IoTHub.ConnectionDeviceId as Device, 
        System.Timestamp as tumblingWindowEnd, 
            AVG(Stream.temp) as TempC, 
            AVG(((Stream.temp*1.8)+32)) as TempF, 
            AVG(Stream.accelerometerX) as accelerometerX, 
            AVG(Stream.accelerometerY) as accelerometerY, 
            AVG(Stream.accelerometerZ) as accelerometerZ
    FROM 
        IoTStream Stream TIMESTAMP BY IoTHub.EnqueuedTime 
    GROUP BY IoTHub.ConnectionDeviceId, TumblingWindow(second, 10) 
    )
    ...
    ```

    ![New query in the Query editor](../media/12-ie-unit6.png)

    > [!NOTE]
    > This snippet will process the raw data off the device and group it into 10-second tumbling windows. These windows will be evaluated for anomalies. Although we're using averages for the data in the tumbling windows, you can use any aggregation that makes sense for your scenario.

5. Paste the following snippet after the last snippet. This snippet uses the data from that snippet and further augments it.

    ```json
    ...
    FillInMissingValuesStep AS 
        ( 
            SELECT
                System.Timestamp AS hoppingWindowEnd, 
                TopOne() OVER (ORDER BY tumblingWindowEnd DESC) AS lastEvent 
            FROM AlertData 
            GROUP BY HOPPINGWINDOW(second, 300, 5) 
        )
    ...
    ```

    > [!NOTE]
    > To help guarantee uniformity of data, so that there aren't any gaps, we've filled the gaps by taking the last event in every hopping window.

6. Paste the following snippet after the last snippet. This snippet does the actual anomaly scoring.

    ```json
    ...
    AnomalyDetectionStep AS ( 
    SELECT 
        lastevent.Device as lastEventDevice, 
        hoppingWindowEnd, 
            lastEvent.tumblingWindowEnd as lastTumblingWindowEnd, 
            lastEvent.TempC as lastEventTempC, 
            lastEvent.TempF as lastEventTempF, 
            lastEvent.accelerometerY as lastEventaccelerometerY, 
            lastEvent.accelerometerX as lastEventaccelerometerX, 
            lastEvent.accelerometerZ as lastEventaccelerometerZ,
            system.timestamp as anomalyDetectionStepTimestamp, 
        ANOMALYDETECTION(lastEvent.TempC) OVER (PARTITION BY lastevent.Device LIMIT DURATION(mi, 2)) as scores 
    FROM FillInMissingValuesStep 
    ), 
    ...
    ```

    > [!NOTE]
    > This snippet uses the `ANOMALYDETECTION` operator on the `TempC` value. Anomaly detection is done on each device and is measured over a two-minute duration. Therefore, the anomaly detection is trained to be device-specific and can accommodate differences in baseline temperatures at each device location. The output causes scores to be added to the output for evaluation in the next snippet.

7. Paste the following snippet after the last snippet.

    ```json
    ...
    AnomalyDetectionFilter AS ( 
    SELECT lastEventDevice as DeviceId, 
        CAST(GetRecordPropertyValue(scores, 'BiLevelChangeScore') as float) as BiLevelChangeScore, 
        CAST(GetRecordPropertyValue(scores, 'SlowPosTrendScore') as float) as SlowPosTrendScore, 
        CAST(GetRecordPropertyValue(scores, 'SlowNegTrendScore') as float) as SlowNegTrendScore, 
        lastEventTempC as Reading, 
        'Tempature' as ReadingType, 
        'Trend Up ' as Threshold, 
        'EventToken' as EventToken, 
        lastTumblingWindowEnd as time 
    FROM AnomalyDetectionStep
    WHERE
        CAST(GetRecordPropertyValue(scores, 'SlowPosTrendScore') as float) >= 10
    union 
    SELECT lastEventDevice as DeviceId, 
        CAST(GetRecordPropertyValue(scores, 'BiLevelChangeScore') as float) as BiLevelChangeScore, 
        CAST(GetRecordPropertyValue(scores, 'SlowPosTrendScore') as float) as SlowPosTrendScore, 
        CAST(GetRecordPropertyValue(scores, 'SlowNegTrendScore') as float) as SlowNegTrendScore, 
        lastEventTempC as Reading, 
        'Tempature' as ReadingType, 
        'Trend Down ' as Threshold, 
        'EventToken' as EventToken, 
        lastTumblingWindowEnd as time 
    FROM AnomalyDetectionStep
    WHERE
        CAST(GetRecordPropertyValue(scores, 'SlowNegTrendScore') as float) >= 10) 
    ...
    ```

    > [!NOTE]
    > This snippet evaluates both `SlowPosTrendScore` and `SlowNegTrendScore`. The value that you're checking is the sensitivity. Although the value can start being meaningful at *3.25*, we're waiting until it's more significant (at least *10*). In the real world, you would tune this query to your specific scenario. Notice that fields are selected for `Reading`, `ReadingType`, `Threshold`, and `EventToken`. The Logic App expects this for any message that is sent to the alerts queue (the next snippet will send messages to this queue). If you don't maintain these fields, you must change that Logic App so that it doesn't expect them.

8. Paste the following snippet after the last snippet.

    ```json
    ...
    SELECT * 
    INTO AlertsQueue 
    FROM AnomalyDetectionFilter data 
    WHERE LAG(data.DeviceID) OVER (PARTITION BY data.DeviceId, CAST(data.Reading as bigint), data.ReadingType LIMIT DURATION(minute, 1)) IS NULL 
    ...
    ``` 

    > [!NOTE]
    > This snippet does the actual insert into the alerts queue. This insert will be picked up by the Logic App to create the IoT Alert record. Notice that we're keeping the `LAG` operator in the `Where` clause to limit how often messages are put into the queue. Messages will be sent to the queue only when the same device for a rounded temperature has new data within the same minute.

9. To help guarantee that the same detail data from the device is logged, add the following snippet.

    ```json
    ...
    SELECT
        * 
    Into CosmosDB 
    FROM IoTStream TIMESTAMP BY IoTHub.EnqueuedTime 
    ...
    ```

10. Add the following snippet. This snippet saves the scores from the anomaly detection operator, so that you can easily see the data via the Azure Cosmos DB Data Explorer.

    ```json
    ...
    SELECT
        * 
    Into AnomalyDB 
    FROM AnomalyDetectionStep
    ...
    ``` 

11. Select **Save**.

    ![Save button](../media/13-ie-unit6.png)

12. Select **Yes**.
13. Select **Overview**, and then select **Start**.

    ![Start button](../media/14-ie-unit6.png)

14. Select **Now**, and then select **Start**.

    ![Start button](../media/15-ie-unit6.png)

Make sure that the job is successfully started.

### Testing the query
In this exercise, you'll try to cause the temperature on your physical device to be changed, so that you can test the anomaly detection.

#### Test the query
Now comes the challenging part. You need something to slowly change the temperature that the device reads. Ice packs and cans of compressed air work well to decrease the temperature. A hair dryer or a hand warmer might work to increase the temperature. Just be sure to protect your device, so that you don't get it wet or otherwise damage it.

1. Close the Stream Analytics blade.

    ![Close button](../media/16-ie-unit6.png)

2. Open the Azure Cosmos DB.

    ![Azure Cosmos DB](../media/17-ie-unit6.png)

3. Select **Data Explorer**, expand **AnomalyData**, and select **Documents**.

    ![AnomalyData](../media/18-ie-unit6.png)

4. You should see a list of alerts. Select one of the alerts.

    ![open an alert window](../media/19-ie-unit6.png)

5. You should see sensor data from your device.

    ![Sensor data](../media/20-ie-unit6.png)

6. Go to Dynamics 365, select **Switch to Another App**, and then select **Connected Field Service**.

    ![Connected Field Service](../media/21-ie-unit6.png)

7. Select **Site Map**, and then select **IoT Alerts**.

    ![IoT Alerts](../media/22-ie-unit6.png)

8. Open one of the alerts.

    ![Alerts](../media/23-ie-unit6.png)

9. In the **Alert Data** section, you should see sensor data from your device.

    ![Sensor data](../media/24-ie-unit6.png)
