WinAutomation supports parallel execution of numerous processes, or even of many instances of the same process. Concurrency policies allow you to restrict the number of processes that can be run simultaneously. 

By implementing a concurrency policy, you can ensure that low-performance machines will not run a high number of processes at the same time and you may prevent crashes.

To create a global concurrency policy:

1.	Navigate to **Settings** and then select **Concurrency Policy**.

    ![The Concurrency Policy tab.](..\media\concurrency-policy-tab-settings-options.png)

1.	Enable the **Limit the number of Processes that can run concurrently** option. 

    ![A check box that limits the number of processes running concurrently.](..\media\limit-processes-concurrency-policy-tab.png)

1.	Set the maximum number of simultaneously running processes in the **Max processes limit** field. 

    ![A field that sets the max number of processes that can run concurrently.](..\media\max-processes-concurrency-policy-tab.png)

1.	In the **If this limit is reached** menu, select the desired action to be performed when the limit is reached. You can choose between adding processes in a waiting queue or cancelling them.

    ![A dropdown menu that sets what happens when the limit is reached.](..\media\if-limit-is-reached-concurrency-policy-tab.png)

1.	Optional: If you select **Queue Process** in the previous step, you can enable the **Set Timeout** checkbox to set a period after which the process will be rejected.

    ![A checkbox that enables a timeout for the processes in the queue.](..\media\timeout-concurrency-policy-tab.png)

1.	Populate the **Wait for max _ minutes before being rejected** field with the desired value. 

    ![A field that determines how many minutes a process stays in the queue before being rejected.](..\media\minutes-before-reject-concurrency-policy-tab.png)