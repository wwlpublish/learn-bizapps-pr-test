While attended desktop flows require a user to be logged in to execute the actions associated with the flow, an unattended desktop flow can't run if there are any active Windows user sessions present, even a locked one. For this reason, many users choose to run unattended flows on a virtual machine. It allows users to run unattended workflows while keeping all physical devices free for use. For an unattended desktop flow to run smoothly, you need to have:

-   All users logged out completely

-   A locked screen (enabling the flow to run without any users seeing the actions performed)

-   A gateway with the user sign-in information to the desktop

You can choose to run multiple unattended desktop flows sequentially on the same device by viewing and manually changing the run queue, but desktop flows that don't run within 3 hours of being requested will time out. This means that if you trigger multiple unattended desktop flows, they'll perform one after another unless the queue gets backed up by more than 3 hours. While you can't run desktop flows concurrently with the same user, since multiple users can be signed in simultaneously on Windows Server 2016 and Windows Server 2019, Power Automate can run several unattended desktop flows simultaneously on a single device. With this feature, your organization can save on infrastructure costs by using two or more user accounts to create desktop flow connections targeting the gateway on a single device.

Now that you understand some of the details and benefits of unattended desktop flows, let's learn how to run them.
