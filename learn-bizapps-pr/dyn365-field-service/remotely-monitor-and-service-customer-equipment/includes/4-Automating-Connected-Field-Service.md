## Automating Connected Field Service

After an IoT alert is generated in Connected Field Service, you need to identify what your next course of action should be. The IoT alert record itself contains several pieces of information, including the type of alert, time, device ID, and alert data. The Alert Data field consists of JSON data that contains the specific detail about the event. The data included can vary depending on the device. The information in the Alert Data field will generally dictate what specific next step should be taken. When starting to build automations around next steps, it is important to understand what tools and information are available, and how those tools allow you to achieve your goal.  


<!--note from editor: not sure if this is the correct way to format a video.-->


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2EbBy]

Out of the box, the Connected Field Service solution contains several actions and workflows that can be leveraged to assist in automating items like creating and registering devices and populating relevant data on records.  

Some of the key actions related to IoT alerts include:

| **Display Name** | **Description** |
| :-------------- | :--- |
| **JSON-Based Field Value - Get Number** | Reads a numeric property in the specified JSON object. |
| **JSON-Based Field Value - Get String** | Reads a string property in the specified JSON object. |
| **JSON-Based Field Value - Get Boolean** | Reads a Boolean property in the specified JSON object. |

The data in the Alert Data field is in the JSON format. The text below represents an example of what would be passed to the Alert Data field when an IoT alert is raised. 

```json
...
{"deviceid":"smt-1298","readingtype":"Temperature","reading":113,"eventtoken":"c802338d-60f2-4a79-b45c-e164e2191ce0","threshold":70,"ruleoutput":"AlarmTemp","time":"2018-09-06T15:58:08.964Z"}
...
``` 

Generally, you cannot directly use the contents of the Alert Data field because you might be looking to query based on one of the properties, not all of them. You must first parse out the relevant parameters that you want to work with, so you can use those to drive query on and drive next steps.    

If we were to parse out the JSON string above, we can see that it is communicating the following:

| **Parameter** | **Value** |
| :-------------- | :--- |
| **deviceid** | Smt-1298 |
| **readingtype** | Temperature |
| **reading** | 113 |
| **eventtoken** | c802338d-60f2-4a79-b45c-e164e2191ce0 |
| **threshold** | 70 |
| **ruleoutput** | AlarmTemp |
| **time** | 09/06/2018 06:58:08 AM |

To assist in parsing out the specific parameter that you may need from the JSON string, you can leverage one of the **JSON-Based Field Value** actions.  

The JSON-Based Field Value actions contain the following parameters:

| **Parameter** | **Type** | **Description** |
| :-------------- | :--- | :--- |
| **JSON** | Input | The JSON object to examine. (In this case the Alert Data field.) |
| **PropertyPath** | Input | Property name or path of the value to ready. (This is case-sensitive.) |
| **DefaultReturnValue** | Input | Default value to return if specified property is not found. |
| **Response** | Output | The response value for the property specified.  |

Depending on the **JSON-Based Field Value** action you specify, the Output Parameter might be a text string (String), numeric value (Number), or Boolean value (Boolean).  


**For example:** If you use the **JSON-Based Field Value – Get Number** action to extract the reading value for the Alert Data JSON string below: 

```json
...
{"deviceid":"smt-1298","readingtype":"Temperature","reading":113,"eventtoken":"c802338d-60f2-4a79-b45c-e164e2191ce0","threshold":70,"ruleoutput":"AlarmTemp","time":"2018-09-06T15:58:08.964Z"}
...
``` 

It might look like the table below:

| **Parameter** | **Value** |
| :-------------- | :--- |
| **JSON** | Alert Data (Field Name) |
| **PropertyPath** | reading  |
| **DefaultReturnValue** | 70 (Represents the current temp threshold)  |
| **Value** | 113 |

The value represents the value that is returned by the action, which in this case would be 113 since that is the value associated with the “reading” property. We use the Get Number action so we can pass the value to a numeric field and then leverage numeric query options on the value to determine what to do with the item.   

Now, a look at a practical application of this concept.

Let’s say that you have a Smart Thermostat that is registered as an IoT device. If the reading on the alert exceeds 70 degrees, an IoT alert is generated in Connected Field Service.  

- If the device reading is between 70 and 85 degrees, have Connected Field Service automatically send a command to the device to reboot it. 
- If the device reading is greater than 85 degrees, require that a technician do some manual troubleshooting.  

You can accomplish this by creating a workflow that does the following: 

- First it executes the **JSON-Based Field Value – Get Number** action to capture the value of the “reading” property.
- Next it writes the output value returned to a custom field on the IoT alert record—for example, Device Reading.
- Another workflow could be triggered on the update of the Device Reading field, then does the following:
	- If the Device Reading field is between 70 and 85 degrees, it will create a command related to the IoT alert that sends a reset command to the device.
	- If the Device Reading field is greater than 85 degrees, the workflow will complete with a status of "succeeded."     
