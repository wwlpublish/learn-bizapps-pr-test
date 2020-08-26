The first two levels concern exception handling; namely, the failure of individual actions in a process, and the attempt to handle such failures so that the process may resume running.

In this unit, you will learn how to utilize the exception handling capabilities of WinAutomation.

## Action-level exception handling (Level 1)

Exceptions may occur from virtually any action. For this reason, most actions’ properties contain a dedicated Exception Handling tab.

In the initial example, we mentioned that the client's database may be inaccessible, causing the action that communicates with the database to produce an exception.

To prevent this, open the action’s properties, and navigate to the **Exception Handling** tab.

![The Exception Handling tab in the Open SQL Connection action's properties.](..\media\open-sql-connection-action-properties.png)

In this tab, you will be able to configure each action’s exception handling behavior. These rules come into effect if this specific action fails, and in the order in which they are arranged:

![The populated Exception Handling tab in the Open SQL Connection action's properties.](..\media\open-sql-connection-action-properties-all-exceptions.png)

In the above case, for example, when this action fails, it will retry two more times, three seconds apart, and then run a function that will send an email to notify the administrator about the database status.

By default, exception handling takes effect when any exception occurs while this action is running - however, you can configure it so that exception handling occurs only on a specific type of exception. Each action has specific exception types that it may produce:

![The populated Exception Handling tab in the Open SQL Connection action's properties.](..\media\open-sql-connection-action-properties-selected-exception.png)

In this example, the exception handling rules will only apply when the **Cannot connect to Data Source** exception occurs.

## Block-level error handling (Level 2)

There are cases where one cannot be certain which action is at risk of failing, and it is not practical to apply the same exception handling rules to every single action.

For example, consider a process in which WinAutomation interacts with the web portal. If at any point during this task the portal or browser becomes unresponsive, the preferred action is to close the browser, launch it again, and restart the entire web portal interaction from the beginning. However, a web portal interaction can span tens, or even hundreds of actions; so assigning the same exception handling rules to each action individually is impractical.

The **Begin Exception Block** and **End Exception Block** actions allow you to apply one set of exception handling rules to an entire block of actions:

![The Begin Exception Block action's properties.](..\media\begin-exception-block-action-properties.png)

Actions in between the **Begin Exception Block** and **End Exception Block** actions are affected by the exception block’s rules:

![The Workspace with an example using the The Begin Exception Block action.](..\media\exception-block-workspace.png)

In this example, if any of the actions within the exception block fails, the exception block’s rules will take effect; a function that closes the web browser will run, and the entire block will be repeated, thus preventing the process from crashing due to a non-responsive web page or browser.

## Exception handling priorities

As mentioned earlier, the order in which the exception handling levels are applied is:

- Level 1: Individual action exception handling
- Level 2: Exception handling for action blocks
- Level 3: Individual processes error handling
- Level 4: Global process error handling

Therefore, any action-level exception handling rules run before the respective block-level rules:

![The Exception Handling tab in the Launch New Edge action's properties.](..\media\launch-new-edge-action-properties.png)

![The Workspace with an example using the The Begin Exception Block action.](..\media\launch-new-edge-action-workspace.png)

In the above example, if the sixth action fails, its individual exception handling rules will be considered first. If the exception persists, the exception block will be activated.