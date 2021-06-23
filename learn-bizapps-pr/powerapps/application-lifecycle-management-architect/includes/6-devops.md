Solution architects lead the effort in defining the process for how changes will be promoted from development to production. This effort includes defining the number of stages, such as **dev > test > production**, and the processes to do the promotion, regardless of whether it's manual or automated.

Microsoft is building tools to support this process with Microsoft Azure DevOps by using continuous integration (CI) and continuous deployment (CD).

This section provides an overview of Azure DevOps and how DevOps can be used with Microsoft Power Platform to automate deployments.

## Azure DevOps

Azure DevOps provides developer services for support teams to plan work, collaborate on code development, and build and deploy applications.

![Diagram that shows the collaboration in Azure DevOps.](../media/6-devops.png)

Azure DevOps contains many features to help the development of applications:

- **Azure Boards** - Plan, track, and discuss work across your teams.
- **Azure Pipelines** - Use to automate continuous integration and continuous deployment (CI/CD) builds and releases.
- **Azure Repos** - Source control to store and track changes.
- **Azure Test Plans** - Plan, implement, and track scripted tests.
- **Azure Artifacts** - Publish solutions that are built by build pipelines.

## Pipelines

Power Apps builds tools to automate the common build and deployment tasks that are related to Power Apps by using Azure Pipelines.

Build pipelines can be used to:

- Create dev environments.
- Commit changes from dev to source control.
- Enable the Solution checker tool.
- Perform automated testing.
- Build output solutions from source control (for example, managed or unmanaged).

Release pipelines can be used to:

- Take solutions from build pipelines and deploy them to one or more test or production environments.
- Perform automated testing as part of the release process.
- Pause for approvals before progressing to the next environment.

Tasks in Microsoft Power Platform Build Tools can be used along with any other available Azure DevOps tasks to compose your build and release pipelines. Pipelines that teams will commonly establish include Initiate, Export from Dev, Build, and Release.

> [![Diagram of Azure DevOps with Microsoft Power Platform.](../media/6-alm-devops.png)](../media/6-alm-devops.png#lightbox)

## Alternative automation tools

Alternatives for automating deployments without using Azure DevOps are:

- Dataverse and admin APIs can be used to automate from any supported language.
- PowerShell can be used instead of build tasks for more control.
- Power Automate can be used with the platform admin connectors to automate deployments.
- GitHub actions are currently in preview.
