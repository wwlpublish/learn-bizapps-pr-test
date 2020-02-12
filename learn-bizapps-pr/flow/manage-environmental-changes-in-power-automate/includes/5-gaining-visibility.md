In this section, we will explore some of the different Power
Automate PowerShell Cmdlets that provide administrators with visibility
into how makers are using Power Automate.

**Note:** In the exercise found at the end of this module, we will
walk through how an administrator can use the Power Automate PowerShell
Cmdlets to identify all the connections that have been created within
the tenant. We will also walk through setting up the prerequisite
PowerShell modules.

**Read connection permissions:**
Get-AdminPowerAppConnectionRoleAssignment

In this Cmdlet, administrators can retrieve all connection permissions
for Power Apps and Power Automate. The data returned includes whether
the connection belongs to an owner or if the connection has been shared
with another user.

![Get-AdminPowerAppConnectionRoleAssignment](../media/9-connectionroleassigment.png){width="3.2089555993000873in"
height="3.6726301399825023in"}

**Read and delete custom connectors:** Get-AdminPowerAppConnector

In this Cmdlet, administrators can retrieve all the custom connectors
that have been deployed in the tenant.

![Get-AdminPowerAppConnector](../media/10-customconnectors.png){width="3.152222222222222in"
height="3.2238801399825023in"}

**Read environments:** Get-FlowEnvironment

In this Cmdlet, administrators can retrieve all the environments that
have been created within the tenant. The information returned will also
include the name of the person who created the environment, when it was
created and its location.

![Get-FlowEnvironment](../media/11-environments.png){width="3.238805774278215in"
height="2.5716590113735784in"}

**Read default environment:** Get-FlowEnvironment -Default

This is the same Cmdlet that we previously discussed, but the difference
is that we can provide a parameter of **-Default** that will result in
only the default environment being returned.

![Get-FlowEnvironment -Default](../media/12-default.png){width="3.2761198600174977in"
height="1.8633366141732284in"}

**List all flows in tenant:** Get-AdminFlow

This Cmdlet will list all flows that exist within the tenant. The
information returned includes when the flow was created, who created it
and the environment that it was created in.

![Get-AdminFlow](../media/13-listflows.png){width="3.9701487314085737in"
height="2.3093022747156606in"}

If you would like to export this information in CSV format, you can use
the following command that will write this information to disk.

**Get-AdminFlow \| Export-Csv -Path \'.\\FlowExport.csv\'**

Since the output of PowerShell Cmdlet is a CSV file we can load the
results into a business intelligence tool, like Power Bi or Microsoft
Excel, where we can further analyze the results.
