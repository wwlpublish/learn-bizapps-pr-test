Manually starting processes, while useful, isn't always optimal. Ideally, an automated task should be completed autonomously. In WinAutomation, processes can be run automatically, using schedules and triggers.

## Schedules
Schedules allow users to configure when processes will run based on date and time information (such as date, day of week or month, time of day, time intervals, and so on).

To  access process schedules, navigate to the Scheduler tab in the console. After you select New, you can choose either: Schedule or Recurring Schedule. 
 

![scheduler process execution](..\media\scheduler-process-execution.png)

Schedules are based on absolute date and time values; a schedule is activated daily, weekly, monthly, or on specified dates, and at specified times during the day.
 

![schedule properties](..\media\schedule-properties.png)

Additional configuration options for each schedule type appear when the type is selected.

For instance, a process that must run on the 1st, 15th, and last work day of each month, at noon, would be configured as shown: 
 

![schedule properties continued](..\media\schedule-properties-continued.png)

Recurring schedules are based on time intervals. After the chosen interval has passed, the process is run.
 

![recurring schedule properties](..\media\recurring-schedule-properties.png)

## Triggers

Triggers are used to run processes in response to certain events, rather than at a specified date or time. That's why they are used to automate a task that does not adhere to a strict schedule, but depends another factor, for example a specific kind of email message, a file or database change.

Triggers can be accessed through the Triggers tab of the console. Select New to choose between the different available triggers.
 

![trigger types](..\media\trigger-types.png)

Selecting a trigger opens its properties window, which allows more detailed configuration of the trigger.
 

![file monitor trigger properties](..\media\file-monitor-trigger-properties.png)

## Assigning processes for automatic execution

When using either a schedule or a trigger, once you are done with its configuration, a window will appear, prompting you to assign a process to it.
 

![assign process to schedule](..\media\assign-process-to-schedule.png)

All existing schedules and triggers can be found in their respective tab in the console, where they may also be enabled or disabled. 
 

![enable disable schedule](..\media\enable-disable-schedule.png)

 