# Automatic Execution
Manually starting processes, while, useful, isn't always optimal. Ideally, an automated task should be completed autonomously. In WinAutomation, processes can be executed automatically, using Schedules and Triggers.
## Schedules
Schedules allow users to configure the execution of processes based on date- and time-based information – information like the date, day of week/month, time of day, time intervals, and so on.

To  access the schedules, navigate to the **Scheduler** tab of the Console. Upon pressing the **New** button, two options become available: **Schedule** and **Recurring Schedule**:
 

![scheduler process execution](..\media\scheduler-process-execution.png)

Schedules are based on absolute date & time values; a Schedule is activated daily, weekly, monthly, or on specified dates, and at specified times during the day:
 

![schedule properties](..\media\schedule-properties.png)

Additional configuration options for each Schedule type appear when the type is selected.

For instance, a process that must be executed on the 1st, 15th, and last work day of each month, at noon, would be configured as below:
 

![schedule properties continued](..\media\schedule-properties-continued.png)

Contrary to simple Schedules, Recurring Schedules are based on time intervals. After the chosen interval has passed, the process is executed:
 

![recurring schedule properties](..\media\recurring-schedule-properties.png)

## Triggers
As opposed to Schedules, Triggers are used to execute processes in response to certain events, rather than date or time. That's why they are used to automate a task that does not adhere to a strict schedule, but depends another factor, for example a specific kind of email message, a file or database change, etc.

Triggers can be accessed through the **Triggers** tab of the Console. Press the **New** button to choose between the different available Triggers:
 

![trigger types](..\media\trigger-types.png)

Selecting a trigger opens its properties window, which allows more detailed configuration of the trigger:
 

![file monitor trigger properties](..\media\file-monitor-trigger-properties.png)

## Assigning processes for automatic execution
When using either a schedule or a trigger, once you are done with its configuration, a window will appear, prompting you to assign a process to it:
 

![assign process to schedule](..\media\assign-process-to-schedule.png)

In this window, simply choose the process to be executed automatically, and press OK.

All existing schedules and triggers can be found in their respective tab in the Console, where they may also be enabled or disabled:
 

![enable disable schedule](..\media\enable-disable-schedule.png)

 