An important part of implementing an application lifecycle management for your custom connectors is having a repeatable process that allows to modify connector definitions and have these changes recorded in a source control system. While the steps to accomplish these tasks can be performed manually, having an automated process is better to ensure consistency and repeatability.

To support building these automations Microsoft provides build tasks for Azure DevOps and actions for GitHub. Using these tools, you can build automation to support the following principles:

-   **Development environments are disposable** - Your development environment should just be a workspace where you build your custom connector. You should not rely on it as the source of truth. Source control should be used to store the official latest source. You should be able to recreate a new development environment anytime from source control.

-   **Source control contains the latest source** - When you reach a working version of your connector solution contents should be checked into source control. You can use Azure DevOps or GitHub or your other preferred source control tool. Labeling and branching can be used as appropriate for your process and needs.

-   **Deploy managed solutions** - When your solution containing your custom connector is installed in non-development environments you should deploy a managed solution. The managed solution should be built from the contents of source control and not directly from development. This ensures your source control always contains a copy of what is deployed in your non-development environments.

You can use the Power Platform tooling along with any other available GitHub Actions or Azure DevOps tasks to compose your build and release workflows. Automations that teams commonly put in place include provisioning development environments, exporting from a development environment to source control, generating builds, and releasing solutions. The following diagram illustrates examples of automations you might consider:

> [!div class="mx-imgBorder"]
> [![Diagram illustrates examples of automations you might consider.](../media/automation-diagram.png)](../media/automation-diagram.png#lightbox)

Whether you use Azure DevOps or GitHub actions is up to your preference. Both offer similar capabilities for automating the lifecycles of Power Platform solutions.

## Azure DevOps

Azure DevOps uses build and releases pipelines to implement automation. Pipelines generally are used to build and prepare artifacts and release deploy to downstream environments. Building a Power Platform pipeline is done visually by adding build tasks. The following is an example of a pipeline using the build tasks:

> [!div class="mx-imgBorder"]
> [![Screenshot of the Microsoft Power Platform build tools.](../media/pipeline.png)](../media/pipeline.png#lightbox)

## GitHub

GitHub uses GitHub Actions to create similar workflows. To build a GitHub Action you specify the tasks using YAML. The following is an example of a workflow to export a solution:

> [!div class="mx-imgBorder"]
> [![Screenshot of GitHub action steps.](../media/workflow-export.png)](../media/workflow-export.png#lightbox)

## Common build tasks

Regardless of if you use Azure DevOps or GitHub, the following are some of the common tasks.

|     Task               |     Purpose                                                                                                                                                                                                                             |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Export Solution    |     Export is how you get a copy of your solution   in a zip file format from your development environment.   Export can also be used to support managed   solutions being ready for installation in non-development environments.      |
|     Import Solution    |     Import is how you install a solution zip file   into an environment.   When a solution   already exists in environment this is treated as an upgrade to the existing   solution.                                                    |
|     Unpack Solution    |     The unpack solution tasks takes the zip file   and breaks it down into individual files that are appropriate for storing in   source control                                                                                        |
|     Pack Solution      |     The pack solution task takes the individual   files from source control or any folder and puts them back into a single zip   file ready for import.                                                                                 |

Review the [complete list](https://docs.microsoft.com/power-platform/alm/devops-build-tool-tasks/?azure-portal=true) of the Azure DevOps build tasks for more specifics on each task.

Review the [complete list](https://docs.microsoft.com/power-platform/alm/devops-github-available-actions/?azure-portal=true) of the GitHub actions for more specifics on each action.

## Custom connectors and solutions

One of the important aspects of the connector lifecycle is ability to save connector definitions and configurations in text form as opposed to a simple binary upload of a zip archive. Recording changes in text form allows effective team collaboration because any conflict can be resolved using a standard source control merge process.

Custom connectors can be included in a Dataverse solution and transported between the environments. Solutions are exported as zip archives containing all solution components including custom connectors. Both Azure DevOps and GitHub include custom steps that allow unpacking the solutions down to individual components including custom connectors definitions. That allows to analyze and visualize code commits and pull requests to identify changes and resolve conflicts if necessary.
