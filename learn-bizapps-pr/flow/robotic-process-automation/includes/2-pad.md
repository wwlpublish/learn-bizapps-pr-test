Power Automate desktop flows are for automation where there's no connector or API available to use. There are many legacy applications that don't have a method for accessing their data or functionality except through their user interface.

Power Automate Desktop flows use Robotic Process Automation (RPA) techniques to automate user actions on these legacy applications. These techniques require software to be installed on the computers where the applications are installed. The software required to create, edit, and run desktop flows is called Power Automate Desktop.

Whether working with modern or legacy apps, on-premises or in the cloud, Power Automate Desktop can automate rule-based UI tasks by recording mouse clicks, keyboard inputs, and data entry. And entering data, Power Automate Desktop can also extract information from the application user interface. Once the actions have been recorded, Power Automate Desktop has a rich editor for adjusting these user actions to create complex desktop flows.

> [!div class="mx-imgBorder"]
> [![alt text](../media/2-desktop-flow-designer.png)](../media/2-desktop-flow-designer.png#lightbox)

Power Automate desktop flows can be run attended with the user manually initiating the flow, or unattended with desktop flows running on Virtual Machines in Azure.

Power Automate desktop flows are a valid way to perform integrations and automation when there's no other alternative, or when developing an integration would be expensive and time consuming.

> [!NOTE]
> Power Automate cloud flows are explained in the Power Automate Architecture module.

## Desktop software

Unlike the rest of the Power Platform tools, Desktop flows require software to be installed on your local computer. You need this software because you need to interact with software applications that aren't accessible from the cloud.

The Power Automate Desktop app is a Windows application that you use to create, edit, and run desktop flows. You can download this tool [here](https://go.microsoft.com/fwlink/?linkid=2102613) or from the Power Automate portal. Microsoft has announced that Power Automate Desktop will, in future, be included with Windows 10 and is free to use on a Windows 10 computer.

You'll need a computer running Windows 10, Windows Server 2016, or Windows Server 2019 to install Power Automate Desktop.

> [!NOTE]
> For unattended flows Windows 10 Home is insufficient and Windows 10 Pro or Windows 10 Enterprise is required.

To start a desktop flow from the cloud, a second application is required to be installed on the computer where Power Automate Desktop is installed. This is the On-premises data gateway. This tool allows desktop flows to be triggered by a Power Automate cloud flow. You can download a gateway from [Install an on-premises data gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install/?azure-portal=true) or from the Power Automate portal.

> [!div class="mx-imgBorder"]
> [![Diagram of the On-premises data gateway.](../media/2-on-premises-data-gateway.png)](../media/2-on-premises-data-gateway.png#lightbox)

As a solution architect, you'll need to liaise with the IT department to arrange for these software applications to be installed. Local software installation can often take much longer to plan and implement than you may think because of IT policies and procedures. If you're planning to use RPA in your solution, you should look to address the deployment of this software as early as possible.

## Browser software

To interact with web applications, a modern web browser is required. The latest version of the Google Chrome browser, Microsoft Edge, and Mozilla Firefox are supported.

A browser extension is required to be installed. These can be installed by the Power Automate Desktop installer but may require more configuration. Again, the solution architect will need to liaise with the IT department as installing browser extensions maybe blocked by corporate IT policies.

There are some further settings for browsers that should be configured. These are described in [Use browsers and manage extensions](https://docs.microsoft.com/power-automate/desktop-flows/using-browsers/?azure-portal=true) and the solution architect will need to arrange for these settings to be applied.

## Requirements

Power Automate Desktop requires access to a Power Platform environment that has a Dataverse database. You may need to create a database for the default environment if one doesn't already exist.

## Solutions

Desktop flows are solution aware and can be included in solutions and application lifecycle management processes.

You should make use of Environment variables for any property used in a Desktop flow that might vary between environments.

## Deployment

Post deployment of a desktop flow via a solution there are manual tasks that may need to be performed:

- Gateways: Configure desktop flows to connect using the gateway(s) for the environment
- Environment variables: Set the values for the environment.
- End-user authentication: Configure end-user authentication so the desktop flow can take actions on the user’s behalf.

The solution architect should ensure that these steps are included in the deployment plan for the solution.
