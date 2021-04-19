This unit introduces Robotic Process Automation (RPA) and the use cases for Power Automate desktop flows.

There are many legacy applications that don't have a method for accessing their data or functionality except through their user interface. RPA solutions operate by generating a list of actions by capturing the steps a user performs in an application's user interface. The RPA solution then performs the automation by repeating the steps in the application's UI, effectively simulating the user's actions in software. RPA enables the automation of applications that don't have an API that can be used for such automation tasks.

Robotic Process Automation (RPA) is garnering much interest and attention. By automating simple tasks, RPA solutions promise to lower costs while reducing errors.

## Legacy automation issues

When analyzing work performed by users, the following has been observed:

- 60% of all occupations have at least 30% automatable activities.
- Almost 50% of work activities globally can be automated using current technology.
- Data collection and processing times can improve by 64% with automation.

The best organizations are powered by strategic and creative people, but they're often forced to spend nearly half their time on repetitive tasks that could be automated with current technology.

A major roadblock in automating systems and workflows can be that legacy and other third-party applications have no modern API data access that allows tools such as Power Automate to include them in their cloud flows.

It isn't always possible to replace the legacy applications either because of difficulty or the costs to replace them. In addition, many legacy applications are on-premises and it can be hard to link to the on-premise applications and combine them with cloud services in an end-to-end automation process.

Many RPA solutions have been developed to solve this problem. Power Automate desktop flows are Microsoft's answer to this problem.

## Automation with Power Automate

There are many SaaS services that can be accessed with modern REST APIs that automation tools such as Power Automate can connect to and orchestrate for the purposes of integration and automation of tasks.

Using Power Automate, a solution architect can create innovative solutions. However, what happens when there isn't a connector available. If the service has a modern REST API, then you can create a custom connector. If there isn't an API, then Power Automate desktop flows are available.

Microsoft's approach to automation is:

- Accelerate productivity: Minimize repetitive, manual, time-consuming tasks and create more time for your teams to focus on strategic work.
- Automate at scale: Allow everybody in your organization to automate workflows using connectors for their favorite on-premises and cloud-based apps and services. From end users, professional developers, to IT.
- Apply intelligent automation: Streamline how you work by combining the power of AI with automated workflows and business process.
- Integrate automation, more securely: Enable end users to build automated workflows that comply with established policies and focus your skilled IT resources on more complex, strategic work.

This flowchart can help you determine how to architect your automation.

Decision-making flowchart for your design.](../media/1-decision-making-flow.png)

## Use cases for Power Automate desktop flows

Power Automate desktop flows automate repetitive tasks and there are many scenarios that Power Automate desktop flows can be employed in. Some use cases for desktop flows are as follows:

- Invoice processing: Processing invoices includes many repetitive tasks, which, if performed incorrectly, can lead to delayed or incorrect payments. For instance, invoices need to be checked against the corresponding purchase orders. Desktop flows can process invoices and automatically perform the required validation checks.
- Recruitment: Desktop flows could gather and collate applications from multiple job portals into a single applicant list.
- New user onboarding: New joiners to an organization must be set up on many systems. While you can use tools such as PowerShell to perform some setup, there are some applications for which there's no automation available. Desktop flows can be used to add users and configure their settings automatically through the applications' user interfaces.

## Solution architect’s role

By using Power Automate cloud and desktop flows, a solution architect can design end-to-end processes that encompass modern cloud services, legacy desktop, and web applications.

The solution architect should look for opportunities for automation. Good opportunities exhibit the following characteristics:

- Standard process: Is the process well understood and consistent in how it needs to be executed?
- High frequency: Is this a process that runs frequently and the ROI exists to spend build cycles on it?
- Predictable processes: Are the outcomes predictable or do they require any judgment calls by humans?
- Prone to human error: Is there a risk that a human may introduce errors as a result of manually completing this process? Are there many steps that are easy to perform out of order?
- High risk of failures and impact: Is the risk and/or impact of a failure high that could be mitigated through automation?

There are many uses for desktop flows. You can consider any scenario where there's the processing of forms, extracting data from systems, or processing claims where the data needs to be verified for automation with desktop flows. If you have rule-based processing, desktop flows are a viable candidate for automating those processes.

The introduction of Power Automate Desktop opens up many scenarios that wouldn't have been possible or would have been difficult and expensive to achieve.

Desktop flows can also be used for situation where there's an API but the API doesn't expose all of the operations available in the application's UI. In such circumstances, Power Automate Desktop maybe the answer.

During design, the solution architect should separate flows into smaller automations so that you don't have a single automation that covers the entire process. There are several reasons why you should make multiple, smaller flows:

- Multiple people can work on the automation.
- Small flows with common steps may be able to be reused.
- Error handling doesn't need to be as sophisticated.
- Maintenance is easier.
- Easier to manage the automation if a step fails.
