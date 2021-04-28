The cmdlets are available on PowerShell Gallery and can be installed in an elevated PowerShell session.

Some of the common and most frequently used Power BI Cmdlets are provided below. 

## Installation

> [!div class="mx-imgBorder"]
> [![Screenshot of the PowerShell install module code.](../media/installation.png)](../media/installation.png#lightbox)

For example, if you only wanted the Workspaces module, you could install individual modules (based on your needs) instead of the rollup module.

> [!div class="mx-imgBorder"]
> [![Screenshot of the PowerShell install module code for workspaces module only.](../media/individual-install.png)](../media/individual-install.png#lightbox)

## Log in to Power BI

> [!div class="mx-imgBorder"]
> [![Screenshot of the PowerShell connect to Power BI service account code.](../media/power-bi-signin.png)](../media/power-bi-signin.png#lightbox)

## Get workspaces

Get workspaces for the user. By default, for example - without -first parameter, it shows the first 100 workspaces assigned to the user.

> [!div class="mx-imgBorder"]
> [![Screenshot of the PowerShell Get Power BI Workspace code.](../media/get-workspace.png)](../media/get-workspace.png#lightbox)

Use the -All parameter to show all workspaces assigned to the user.

> [!div class="mx-imgBorder"]
> [![Screenshot of the PowerShell Get Power BI Workspace all parameter code.](../media/get-all-workspace.png)](../media/get-all-workspace.png#lightbox)

If you are a tenant administrator, you can view all workspaces in your tenant by adding -Scope Organization.

> [!div class="mx-imgBorder"]
> [![Screenshot of the PowerShell Get Power BI Worksapce Scope Organization code.](../media/get-all-workspace-scope-organization.png)](../media/get-all-workspace-scope-organization.png#lightbox)

For additional commonly used Power BI cmdlets, see [Microsoft Power BI Cmdlets for Windows PowerShell and PowerShell Core](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps/?azure-portal=true).
