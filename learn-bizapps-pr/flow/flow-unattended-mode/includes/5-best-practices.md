If you plan to run multiple unattended desktop flows, there are a set of strategies you can adopt to distribute load and ensure that all your unattended desktop flows run successfully without overloading the target machine(s) or running into timeouts because multiple unattended desktop flows are running at the same time. You can either:

-   Plan your unattended desktop flows to run at different times of the day, spreading your load over time. This works best if you have a single or a limited set of machines that can run workloads, and you can control the triggers (for example, scheduled flows) that start your desktop flows.

-   Create clusters of machines that can run unattended desktop flows with identical configurations in parallel.

-   Create multiple desktop flows that each use a separate connection to target different machines.

By following these strategies, you can avoid having unattended desktop flows competing to run on the same device and in some cases failing due to timeouts.
