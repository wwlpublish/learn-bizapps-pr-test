WinAutomation supports parallel execution of many instances of the same process. Process concurrency policy allows you to restrict the number of instances that can be executed simultaneously. 

By implementing a process concurrency policy, you can ensure that low-performance machines will not execute an excess number of processes concurrently. Also, you can limit the number of process instances that access resources at any given time. 

To create a process concurrency policy:

1.	Navigate to the **Concurrency Policy** tab inside the **Process Properties** dialog.

    ![The Concurrency Policy tab in the Process Properties dialog.](..\media\concurrency-policy-tab-process-properties.png)

1.	Enable the **Limit the number of Processes Instances that can run concurrently** checkbox. 

    ![A checkbox that limits the number of processes instances that can run concurrently.](..\media\limit-instances-concurrency-policy.png)

1.	Set the max number of simultaneously executed processes in the **Max instances limit** field. 

    ![A field that specifies the max instances of the Process that can run concurrently.](..\media\max-instances-concurrency-policy.png)

1.	In the **If this limit is reached** dropdown menu, select the desired action to be performed when the limit is reached. You can choose between adding processes in a waiting queue or cancel the execution of them.

    ![A dropdown menu that determines what action will be performed when the limit is reached.](..\media\if-limit-is-reached-concurrency-policy.png)

1.	Optional: If you select **Queue Process** in the previous step, you can enable the **Set Timeout** checkbox to set a period after which the process will be rejected.

    ![A checkbox that enables a timeout for the processes in the queue.](..\media\timeout-concurrency-policy.png)

1.	Populate the **Wait for max _ minutes before being rejected** field with the desired value. 

    ![A field that determines how many minutes a process stays in the queue before being rejected.](..\media\minutes-before-reject-concurrency-policy.png)