In the overview, we discussed how Connected Field Service handles anomaly detection with the default template application. In this unit, we will discuss options for tailoring how detection is done. 

The first thing to consider is the type of rules or intelligence you need to handle generating insights for your scenario.  The simplest form is stateless and static.  For example, if the controlled room temperature goes over 20c or below 10c raise an alert.  This type of evaluation doesn’t require historical data to know how much it has changed since the last data point, it simply is a point in time comparison.  For this type of analysis, you don’t really need the Stream Analytics Job, you could even consider replacing it with a simple Azure Function. 

As rules become more complex, they often become stateful and dynamic.  These types of rules become more challenging to implement in simple code because the state that must be maintained across the set of devices you are monitoring.  Azure Stream Analytics helps by providing the concept of time-based windows that you can evaluate without having to code specifically for those scenarios. 

One of the things the Azure IoT Reference Architecture highlights is the concept of breaking insight detection into a fast and slow path.  Where the slow path is not constrained by the limitations of real-time analysis.  Building on our example of storing the detail telemetry in Azure Storage in the prior unit, the architecture in the following example highlights using a fast and slow path.  Where the slow path can take the detail data from Azure Storage into Azure ML to generate more in-depth training or insights.

![Fast and slow path diagram](../media/1-ie-unit5.png)
 
 
Since Azure Stream Analytics (ASA) is built-in to the template let’s look at a few of the things it is able to do to help analyze the data stream.  Let’s start by looking at the default Where clause that is used.  This Where processes any of the records that are out of range of detection and ensures that only one alert is generated unless it has been longer than a minute.  

WHERE LAG(data.DeviceID) OVER (PARTITION BY data.DeviceId, data.Reading, data.ReadingType LIMIT DURATION(minute, 1)) IS NULL 

This clause does this by using the LAG analytic operator which allows lookup of a previous event in the event stream.  The OVER (PARTITION… will return the previous reading for that specific device if it occurred in the last minute defined by the DURATION.  This is an example of the stateful nature of Azure Stream Analytics, and how it manages state for us. 

Another example of this is the ability use the windowing capabilities.  ASA has four types of windows to choose from: Tumbling, Hopping, Sliding, and Session. The output from the window will be a single event based on the aggregate function used. The following example changes our query to produce averages across a 10 second tumbling window.  This ensures that there is no overlap, and an event cannot belong to more than one window.  

![Windows Output](../media/2-ie-unit5.png)
 
The following is a visualization of the tumbling window across 30 seconds.

![Windows Output](../media/3-ie-unit5.png)
 
Using this approach our detection could be done on averages over a period of time and not just a point in time observation.  We could further take this to the next level by using the Anomaly detection feature of ASA. 
The anomaly detection feature is currently in preview, but it adds the AnomalyDetection operator to the query capabilities.  Currently the operator can detect three types of anomalies: Bi-directional Level Change, Slow Positive Trend and Slow Negative Trend.  Take our example of our controlled room, where previously we checked if the temperature reached our range thresholds, that is point in time and only detects when we have reached our outer limits.  If we changed that to use the AnomolyDetection operator we could be more proactive when we detect a rise in the temperature over time well before it reached a panic level. 

The operator uses an unsupervised learning approach to train the models.  In general, there are two models maintained in parallel, one used for scoring and the other is trained in the background. The training is done from data in the current stream rather than using out-of-band data. 

As you can see there are many possibilities for how you can identify exceptions and raise alerts.  We have only scratched the surface on the potential of Azure Stream Analytics, and the custom possibilities though Azure Functions or microservices are endless.  In the next unit you will put to work the AnomolyDetection operator in the hands on exercise. 