After you have created your desktop flow in Power Automate Desktop, you can run it from a cloud flow in Power Automate through desktop flows, in either attended or unattended mode.

Create a desktop flow in Power Automate Desktop, and add input and output variables.

![input output variables](..\media\input-output-variables.png)

Input variables will retrieve their values from the ones provided in the Power Automate cloud flow.

![new input variable](..\media\new-input-variable.png)

Values of output variables can be passed to the Power Automate cloud flow.

![new output variable](..\media\new-output-variable.png)

The external name field determines the names the variables use in Power Automate. This way, you can avoid conflicts with existing variable names, as well as provide more UI-appropriate names for variables in Power Automate, depending on your requirements.

When running the desktop flow from the console, a dialog prompts the user for the values of the input variables.

   ![input variable dialog](..\media\input-variable-dialog.png)

You can call this dekstop flow to run from Power Automate.

## Run a Power Automate Desktop flow in Power Automate

1. Open a cloud flow in Power Automate and select **New step**

   ![new step](..\media\new-step.png)

1. Search for and select the **Run a flow built by Power Automate Desktop** action.

   ![run flow built by pad](..\media\run-flow-built-by-pad.png)

1. Choose an existing desktop flow or create a new one, and select the run mode.

   Choosing a desktop flow with input variables will display fields where values for these variables can be entered. When the Power Automate Desktop flow runs, it will use the values provided here.

   ![run flow pad action properties](..\media\run-flow-pad-action-properties.png)

1. Edit the desktop flow by selecting **Edit**. Select **Launch app** in the confirmation dialog.

   ![run pad](..\media\run-pad.png)

1. Your browser may prompt you to allow the launch of Power Automate Desktop. Select **Open** to continue.

   ![browser launch pad](..\media\browser-launch-pad.png)

1. When the flow in Power Automate Desktop process designer is complete, save it, and select **Keep Working** in this dialog.

   ![launched dialog](..\media\pad-launched-dialog.png)

1. Actions in the Power Automate cloud flow can retrieve the values of output variables.

   ![external variable](..\media\external-variable.png)

