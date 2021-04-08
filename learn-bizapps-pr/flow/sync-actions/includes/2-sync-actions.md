Synchronization actions help to ensure that two processes don't affect each other while they are running simultaneously. This group of actions consists of two actions: **Lock Handle** and **Release Handle**.

The **Lock Handle** action marks the start of a locked region that contains resources that allow only one active instance at a time. This action gets one input that defines the handle's name. The process waits on the handle to become available for locking.

![Screenshot of the Lock Handle action dialog.](..\media\lock-handle-action.png)

The specified handle is used again as an input in the **Release Handle** action to indicate the locked region's end.

![Screenshot of the Release Handle action dialog.](..\media\release-handle-action.png)

> [!NOTE]
> To ensure that processes run as quickly as possible, avoid enclosing whole processes in locked regions, if it's not necessary. Only enclose actions that access the proper resources.
