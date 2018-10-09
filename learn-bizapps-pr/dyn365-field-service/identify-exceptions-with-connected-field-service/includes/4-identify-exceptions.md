## Exercise - Identify Exceptions

### Exercise 1: Azure Cosmos DB 
In this exercise, you will be pre-creating an Azure Cosmos DB that will be used in the next exercise.  This database will be used to store detail telemetry from the device.  

### Scenario 
 
In this unit we are going to modify the Stream Analytics job to work with the data from our physical device that comes in a different format than the simulated device.  We will also be adjusting the stream job to store the data into an Azure Cosmos DB in addition to evaluating it for anomalies 

#### Task 1: Create Azure Cosmos DB 

1. Go to your Azure portal and click Create a Resource. 
![Create a resource](../media/1-ie-unit4.png)
2. Search for Azure Cosmos DB and select it. 
![Field Resource Hub](../media/2-ie-unit4.png)
3. Click Create. 
![Create Button](../media/3-ie-unit4.png)
4. Enter a unique ID, select SQL for API, select your Subscription, select your Resource Group, select your Location, and click Create. 
![Unique ID](../media/4-ie-unit4.png)
5. Wait for the Azure Cosmos DB to be created.
6. Open the Azure Cosmos DB you created, select Data Explorer, and click New Database. 
![New Database](../media/5-ie-unit4.png)
7. Enter Telemetry for Database ID and click OK. 
![OK Icon](../media/6-ie-unit4.png)
8. Click on the … button of the database you created. 
![SQL API Window](../media/7-ie-unit4.png)
9. Select New Collection. 
![New collection drop down](../media/8-ie-unit4.png)
10. Enter DeviceData for Collection ID, change the Throughput to 400, click OK. We are changing the throughput to minimize cost. 
![add collection window](../media/9-ie-unit4.png)
 
### Exercise 2: Adjust Stream Analytics Job  
In this exercise, you will be modifying the Azure Stream Analytics job to accommodate for the different telemetry sent by your MXChip device. 
 
#### Task 1: Add Cosmos DB as an Output 

1. Select Resource Groups and open the Resource Group you created. 
![Resource Group](../media/10-ie-unit4.png)
2. Locate and open the Stream Analytics Job.
![Steam Analytic](../media/11-ie-unit4.png) 
3. Click Stop. The Stream Analytics Job must be stopped before you can change its query and input/outputs. 
![Stop Icon](../media/12-ie-unit4.png)
4. Click Yes. 
5. After the Job stops, select Outputs. 
![Outputs in Navigation](../media/13-ie-unit4.png)
6. Click Add and select Cosmos DB. 
![Add Cosmos DB](../media/14-ie-unit4.png)
7. Enter CosmosDB for Output Alias, select your subscription, select the Cosmo DB you created, select the Database you created, enter DeviceData for Collection NAME Pattern, and click Save. 
![Collection Name](../media/15-ie-unit4.png)

#### Task 2: Adjust the Query for the Device 


1. Select Query. 
![Query](../media/16-ie-unit4.png)
2. Place your cursor at the end of line 14 and <ENTER> 
![Cursor placement](../media/17-ie-unit4.png)
3. Paste the query snippet below. This will allow the query to support both the real and simulated devices. 


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
 
Notice that we are not only adjusting for field names but converting the temperature from Celsius to Fahrenheit. 

![Field name call out in code](../media/18-ie-unit4.png)
 

4. Click Save 
![Save Icon](../media/19-ie-unit4.png)
5. Click Yes. 
 
#### Task 3: Add Saved Data to Azure Cosmos DB 


1. Scroll down to the end of the query and add the below snippet to the Query. This will save a copy of the ingested data. 
![query window](../media/20-ie-unit4.png)
2. Click Save again.
3. Click Yes.
4. Select the Overview tab and restart the job.
![Overview Tab, Start](../media/21-ie-unit4.png) 
5. Wait for the Stream Analytics Job to start.
6. Click on the Resource Group. 
![Resource Group](../media/22-ie-unit4.png)
7. Open the Azure Cosmos DB you created. 
![Select DB](../media/23-ie-unit4.png)
8. Select DATA Explorer, expand Telemetry, expand DeviceData, and select Documents. 
![Documents](../media/24-ie-unit4.png)
9. You should get list of documents. Click on one of the documents. 
![List of Documents](../media/25-ie-unit4.png)
10. You should get sensor data from your device. 