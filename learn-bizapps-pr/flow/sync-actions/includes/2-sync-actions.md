The **Synchronization** actions are used to ensure that two processes don't affect each other while running simultaneously. This group of actions consists of two actions: the **Lock Handle** and the **Release Handle** actions.

The **Lock Handle** action marks the start of a locked region containing resources that allow only one active instance at a time. This action gets one input that defines the handle's name. The process waits on the handle to become available for locking.

![The Lock Handle action.](..\media\lock-handle-action.png)

The specified handle is used again as an input in the **Release Handle** action to indicate the locked region's end. 

![The Release Handle action.](..\media\release-handle-action.png)

[!NOTE]
To ensure that processes run as fast as possible, avoid enclosing whole processes in locked regions, if not necessary. Enclose only actions that access the proper resources.