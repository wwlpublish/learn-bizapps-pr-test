A Business Process Flow is a visual guide that is meant to help users
complete a business process using a set of predefined stages. There is
no time limit on how long a business process can run and there are no
limits on how long a stage can be open. All data associated with the
Business Process Flow can ONLY be stored in one or more entities in
Common Data Service and you cannot associate a Business Process Flow
with another data source "behind" it. Finally, Common Data Service has
many different out-of-the-box Business Process Flows available that can
be used as-is or modified to fit your needs.

A Power Automate Flow (flow) does not have any visual components like a
Business Process Flow. Power Automate flows can be configured to work
with many different data sources and a flow can connect to many
different data sources within the same flow. A flow can be configured to
"time-out" if not completed in a certain time and can be triggered to
move between steps based upon data or user interaction. Flows support
very complex logic and looping and a Power Automate flow can call
another Power Automate flow as needed.

### Business process flows values to organizations 

Business Process Flows allow organizations to easily and quickly
standardize how processes are completed and what data is collected at
each stage. Business Process Flows support logical branching so they can
be used to standardize many common business processes within an
organization.

Business Process Flows offers the following benefits:

-   Improved outcomes

-   Consistent stages and work steps across all instances of the process

-   Improved data collection and reporting

-   Decreased time to complete the process

-   Predictable outcomes

Business Process Flows are easy to set up and administer. Business
process users close to business operations and processes can easily
create new Business Process Flows or modify out-of-the-box Business
Process Flows using Microsoft Power Automate. Business Process Flows can
be customized based upon security roles allowing access to the
appropriate stages and steps based upon a security role. Finally, the
process of each instance of a Business Process Flow can be monitored and
the data from the Process Flow can be used in PowerBI Dashboards and
reporting for simplified administration.

### Business process flows and the larger Power Platform

Business Process Flows are deeply integrated with the Microsoft Power
Platform. They are created, customized, and managed using Power
Automate. You can manage or create new Business Process flows by
launching Power Automate and selecting the Business Process Flows under
My Flows in Power Automate as shown below.

![Power Automate my flows business process flows](../media/2-power-automate-my-flows-business-process-flows.png)

They can be launched as a as a component of a Model Driven Power App
Application or a stand-alone application within Power Automate (called
an immersive Business Process Flow) as shown below.

![Immersive business process flow](../media/3-immersive-business-process-flow.png)

As mentioned previously, all data associated with the Business Process
Flow is stored in one or more Common Data Service entities (custom or
standard). Note -- you could launch an instant Power Automate flow in
conjunction with a Business Process Flow to store data outside of Common
Data Service if needed. Finally, you can easily create PowerBI
Dashboards from the data collected within the Business Process Flow.

As you have now learned, business Process flows are deeply integrated
within the Microsoft Power Platform and offer very powerful ways to
improve how you manage common business processes.