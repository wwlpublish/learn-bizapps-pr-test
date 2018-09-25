## Connected Field Service – Process Automation

### Connected Field Service – Hands – on - Lab

#### Terms of Use
**© 2018 Microsoft Corporation. All rights reserved.**

Information in this document, including URL and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place, or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation. 

For more information, see **Microsoft Copyright Permissions** at [http://www.microsoft.com/permission](http://www.microsoft.com/permission")

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The Microsoft company name and Microsoft products mentioned herein may be either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries. The names of actual companies and products mentioned herein may be the trademarks of their respective owners.

**This document reflects current views and assumptions as of the date of development and is subject to change.  Actual and future results and trends may differ materially from any forward-looking statements.  Microsoft assumes no responsibility for errors or omissions in the materials.**
  
**THIS DOCUMENT IS FOR INFORMATIONAL AND TRAINING PURPOSES ONLY AND IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, WHETHER EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT.**

### Lab Environment
During this lab, you will work in a simulated environment with the following computers or virtual machines.

***Computers and Virtual Machines Used in This Lab***

| **Item Name** | **Description** |
| :-------------- | :--- |
| Dynamics 365 Online Non-Production Instance | You should have a Dynamics 365 Online environment that you use for this lab, it should not be your production (live) instance. |
| Dynamics 365 Field Service | You should have Dynamics 365 for Field Service deployed to the Online Trial that you use for this lab. |
| Connected Field Service | You should have Connected Field Service deployed to the Online Trial that you use for this lab. |
| Azure IoT Hub | You should have a Azure IoT Hub setup and deployed that Connected Field Service is talking to.  |

### Lab Overview
***Abstract***

Dynamics 365’s Connected Field Service solution provides the ability to remotely monitor IoT enabled devices to keep track of up time, device statistics, anomalies and more.  After an IoT Device communicates an anomaly or exception, that information is sent to Connected Field Service as an alert.  Once the alert is captured, we can leverage Dynamics 365’s ability to create automation and business process to develop automated processes for acting on, routing, and fixing the issues.  

The purpose of this hands-on-lab is to introduce you to building and automating Connected Field Service processes, as well as demonstrate how these items can be leveraged as part of an overall IoT solution.  

***Learning Objectives***

At the end of these exercises, you will be able to accomplish the following:

- Leverage Connected Field Service’s actions to extract relevant data from the generated alert.  
- Customize Dynamics 365 entities to store necessary alert data. 
- Build workflows to automate capturing alert data and populating it to Dynamics 365 entities. 
- Build workflows to automate the creation of IoT device commands for interacting with devices.
- Create Field Service related business process flows that offer branching options. 

**Estimated time to complete this lab: 45 to 60 minutes**

#### Scenario

You work for a plumbing and heating company that sells and services smart home devices.  Since many of the devices that you service are smart devices, information from those devices can be captured remotely to aid in the servicing of that equipment.  Your organization has several defined scenarios and processes that they use when servicing equipment.  These processes can vary depending on several factors including:

- Type of device in need of service
- Severity of the issue detected
- Age of the device
- Location of the device
- Availability of resources to work on a specific device.

The above items represent only a small portion of factors that your organization uses to determine the process for servicing equipment.  

Lately, you have been installing a lot of smart thermostat devices.  These devices have been very handy in being able to track temperature and humidity readings in areas when it is important to maintain a consistent temperature and humidity.  Now because you have more information available it has forced you to create new processes for handling and resolving issues reported by these devices.  The first area you would like to focus on automating is the process used for temperature related issues.  

Your organization is looking to implement the following process:

- If a device detects a temperature reading of more than 70 degrees, an alert should be surfaced in your Connect Field Service environment.  

- If the temperature reading is between 70 and 85 degrees, a command should be sent to remotely reset the device to see if the issue resolves itself.  

- If the temperature reading is between 86 and 100 degrees, a service agent should be able to create a case to attempt to resolve the issue.  
	- If the issue cannot be resolved by the service agent, a work order should be created, and an on-site technician should be scheduled for the item.  

- If the temperature reading is more than 100 degrees, this is considered a potentially catastrophic event, and a work order should be created, and an on-site technician should be scheduled for the item.  

### Lab Completion Requirements

After completing the tasks in this exercise, you will be able to:

- Customize Connected Field Service entities to needed data for resolving issues. 
- Trigger Dynamics 365 actions that will extract relevant data from triggered alerts.
- Create automations that place the extracted data into the appropriate Dynamics 365 fields.
- Design automations that automatically interact with devices based on specific criteria.
- Design business process flows that provide alternate resolution paths based on specific data. 

### Exercise: Automate and Customize 

**Before you begin:** This exercise assumes that you already have a working Connected Field Service deployment that is connected with either an Azure IoT hub or an IoT Central instance.  If you do not have a Connected Field Service environment available, it is recommended that you take the Introduction to Connect Field Service Module.  This will assist you in setting up and configuring a Connected Field Service environment.  

#### Task 1:  Create a new IoT alert process solution

In this first task, we will be creating a Dynamics 365 solution, that we can use for storing all of the customizations and processes that we will be creating.  Not only will this make it easier for us to potentially transport these customizations later, but it will also assist in cleaning up our environments after you have completed the course.  

1. In **Dynamics 365** navigate to **Settings > Solutions**.
1. Click the **New** button to add a new solution.
1. Name the solution **IoT Alert Processes**.
1. In the **Publisher** field, click the **Lookup** Icon, select **Look up more records**.
1. Click **New**.
1. Configure the **Publisher** as follows.
	- **Display Name:** *Connected Field Service Course*
	- **Prefix:** *cfs*
1. Click **Save and Close**.
![Save and Close](../media/1-rm-unit6.png) 

1. Select the **Connected Field Service Course** publisher, click **Add**.
![Lookup Record](../media/2-rm-unit6.png) 

1. In the **Version** field enter **1.0.0.0**.
1. Your Solution should resemble the image below:
![Solution Screen](../media/3-rm-unit6.png)

1.	Save the solution and leave it open.  
1.	Select **Entities** and click **Add Existing**.
![Add Existing](../media/4-rm-unit6.png)

1.	Select the **Case, IoT Alert**, and **Work Order** entities.
1.	For each entity select **Add All Assets**.  Do not include required components.
![Add All Assets](../media/5-rm-unit6.png)

#### Task 2:  Customize the IoT alert entity
 
To assist in automating items and actions based on IoT alerts, we will need to be able to extract specific information for generated IoT alerts. We can query it and trigger items based on that data.  Since the alert data, contains only a JSON string that contains all the data, we will need to create some additional fields on the IoT alert entity that we can use to send specific data into and build queries off those fields.  

1. In the **IoT Alert Process** solution, expand **Entities**, expand the **IoT Alert entity**, and select **Fields**.
1. Click the **New** button, and configure the field as follows:
	- **Display Name:** *Reading*
	- **Data Type:** *Whole Number*
	- **Minimum Value:** *0*
	- **Maximum Value:** *250*
![New Fields](../media/6-rm-unit6.png)

1. Click the **Save and New** button
1. Repeat the process to add the fields defined below:
	1. **Threshold**
		- **Display Name:** *Threshold*
		- **Data Type:** *Whole Number*
		- **Minimum Value:** *0*
		- **Maximum Value:** *250*
	1. **Reading Type**
		- **Display Name:** *Reading Type*
		- **Data Type:** *Two Options*
		- Change the **No** value to **Temperature**
		- Change the **Yes** value to **Humidity**
		- **Default Value:** *Temperature*
	1. **Rule Output**
		- **Display Name:** *Rule Output*
		- **Data Type:** *Single Line of Text*
1. Click the **Save and New** button
1. Configure the new field as follows:
	1. **Display Name:** *Customer*
	1. **Data Type:** *Lookup*
	1. **Target Record Type:** *Account*
![Configure New Field](../media/7-rm-unit6.png)

1.	Click **Save and Close**.
1.	Select **1:N** Relationships, click the **New** button.
![New 1-to-Many Relationship](../media/8-rm-unit6.png)

1.	Configure the Relationship as follows:
	- **Primary Entity:** *IoT Alert*
	- **Related Entity:** *Case *
	- **Display Name:** *IoT Alert*
![Relationship Definition](../media/9-rm-unit6.png)

1.	Click **Save** to save the relationship and leave the record open.
1.	Under Common, select **Mappings** and click New.
![New Mappings](../media/10-rm-unit6.png)

1.	Configure the mapping as follows and click OK
	1. **Source Entity Field:** *cfs_customer*
	2. **Target Entity Field:** *customerid*
![Create Field Mapping for IoT Alert to Case](../media/11-rm-unit6.png)

1.	Click **Save and Close**.

#### Task 3: Create a workflow to populate values

Now that we have the field available to store the data that we need, we next need to populate those fields with the correct data.  To do this we will be leveraging some of the JSON –based field value actions that are included in the Connected Field Service solution.  We are going to create a workflow that executes a JSON – based field value action, to extract a specific piece of data from the alert data field, and then populate that data to one of the fields we created in the previous task.

1.	In the **IoT Alert Process** solution, select **Processes** and click the **New**.
![IoT Alert Process New](../media/12-rm-unit6.png)

1.	Configure as follows:
	- **Process Name:** *Populate Alert Fields*
	- **Category:** *Workflow*
	- **Entity:** *IoT Alert*
![Create Process](../media/13-rm-unit6.png)

1.	Click **OK**
1.	Set the **Workflow Scope** to **Organization**
1.	Click the **Add Step** button and choose **Perform Action**.
![Perform Action](../media/14-rm-unit6.png)

1.	Enter **Get the Reading Value** into the **Description**.
1.	Choose the **JSON-Based Field Value – Get Number** action, click **Set Properties**.
![Set Properties](../media/15-rm-unit6.png)

1.	Set the Properties as follows:
	- **Json:** *{Alert Data(IoT Alert)}*
	- **PropertyPath:** *reading*
	- **DefaultReturnValue:** *70*
![Process: Populate Alert Fields](../media/16-rm-unit6.png)
1.	Click **Save and Close**
1.	Click the **Add Step** button again and choose **Perform Action**. 
1.	Enter **Get the Threshold Value** into the **Description**.
1.	Choose the **JSON-Based Field Value – Get Number** action, click **Set Properties**. 
1.	Set the Properties as follows:
	- **Json:** *{Alert Data(IoT Alert)}*
	- **PropertyPath:** *threshold*
	- **DefaultReturnValue:** *70*
![JSON Based Field](../media/17-rm-unit6.png)
1.	Click **Save and Close**.
1.	Click the **Add Step** button again and choose **Perform Action**. 
1.	Enter **Get the Reading Type Value** into the **Description**.
1.	Choose the **JSON-Based Field Value – Get Boolean** action, click **Set Properties**. 
1.	Set the Properties as follows:
	- **Json:** *{Alert Data(IoT Alert)}*
	- **PropertyPath:** *readingtype*
	- **DefaultReturnValue:** *false*
![Get Boolean](../media/18-rm-unit6.png)
1.	Click **Save and Close**.
1.	Click the **Add Step** button again and choose **Perform Action**. 
1.	Enter **Get the Rule Output Value** into the **Description**.
1.	Choose the **JSON-Based Field Value – Get String** action, click **Set Properties**. 
1.	Set the Properties as follows:
	- **Json:** *{Alert Data(IoT Alert)}*
	- **PropertyPath:** *ruleoutput*
	- **DefaultReturnValue:** *Alarm*
![Get String](../media/19-rm-unit6.png)
1.	Click **Save and Close**.
1.	Click the **Add Step** button again and choose **Update Record**.
1.	Enter **Populate Values** into the Description.
1.	Make sure **IoT Alert** is selected, click Set Properties.  
1.	Configure as follows:
	- **Customer:** *{Account(Device(IoT Device))}*
	- **Reading:** *{Value(Get the Reading Value)}*
	- **Reading Type:** *{Value(Get the Reading Type Value)}*
	- **Rule Output:** *{Value(Get the Rule Output Value)}*
	- **Threshold:** *{Value(Get the Threshold Value)}*
![IoT Alert Set Properties](../media/20-rm-unit6.png)
1.	Click **Save and Close**.
1.	Your completed workflow should resemble the image below:
![Completed Workflow](../media/21-rm-unit6.png)
1.	**Activate and Close** the **Populate Alert Fields** Workflow.

#### Task 4: Create the remote reset workflow

Now that we have extracted the correct data and placed it in the correct fields, we will need to create a workflow that will determine the temperature value in the reading field and if it falls between 71 and 85 degrees a IoT device command should be automatically created and sent to the device that will perform a device reset.  
 
1.	In the **IoT Alert Process** solution, select **Processes**.
1.	Click the **New** button
1.	Configure as follows:
	- **Process Name:** *Auto Remote Reset*
	- **Category:** *Workflow*
	- **Entity:** *IoT Alert*
![Create Process](../media/22-rm-unit6.png)
1.	Click **OK**
1.	Set the **Workflow Scope** to **Organization**.
1.	Uncheck **Start when Record is Created**, check **Record Fields Change**, and click **Select**.
![Select](../media/23-rm-unit6.png)
1.	Select **Reading** field and click **OK**.
![Select Fields](../media/24-rm-unit6.png)
1.	Click the **Add Step** button, select **Check Condition**.
1.	Enter **Temp between 71 & 85** into the description
1.	Select the condition and configure as follows:
	1. **IoT Alert – Reading – Is Greater Than or Equal To – 71**
	1. **IoT Alert – Reading – Is Less Than or Equal To - 85**
![Check Condition](../media/25-rm-unit6.png)
1.	Click **Save and Close**
1.	Select the row beneath the condition and click the **Add Step** button.
1.	Select **Create Record**, enter **Send Reset Command** in the description field, choose **IoT Device Command**, and select the **Set Properties** button.
![Set Properties](../media/26-rm-unit6.png)
1.	Configure the command as follows:
	1. **Name:** *{IoT Alert(IoT Alert)} Device Reset*
	1. **Customer Asset:** *{Customer Asset(IoT Alert)}*
	1. **Device:** *{Device (IoT Alert)}*
	1. **Device ID:** *{Device ID(Device (IoT Device))}*
	1. **Parent Alert:** *{IoT Alert(IoT Alert)}*
	1. **Message:** *{"CommandName":"Reset Thermostat","Parameters":{}}*
![Configure Commands](../media/27-rm-unit6.png)
1.	**Save and Close** the **Command** record.
1.	Select the **Send Reset Command** row, click the **Add Step** button, and select **Change Status**.
1.	Enter **Deactivate IoT Alert** into the **Description** field, set the **IoT Alert** record status to **Inactive**.
![Send Reset Command](../media/28-rm-unit6.png)
1.	Select the **IoT Alert Reading** condition, click the **Add Step** Button, and select **Default Action**.
1.	Select the new **Row**, click the **Add Step** button, and choose **Stop Workflow**.
1.	Your completed workflow should resemble the image below:
![Completed Workflow](../media/29-rm-unit6.png)
1.	Activate and Close the **Auto Remote Reset** workflow.

















 

