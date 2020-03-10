While the existing DLP model does support custom connectors, by default,
they don't show up in the DLP policy editor inside the Power Platform
Admin center. The default behavior for
custom connectors is that they're managed as part of the default data
group that you specify. However, the custom connectors won't appear
within the user interface in the Power Automate Admin center. 

Additional actions must be taken by an administrator 
to have custom connectors show up in DLP policies that include either
of the following entities:

-   Power Platform Management connector

-   Power Apps and Power Automate PowerShell cmdlets

Using PowerShell to add custom connectors to a DLP policy is the
simplest way to manage custom connectors. The exercise at the end of
this module demonstrates how this task can be completed.
