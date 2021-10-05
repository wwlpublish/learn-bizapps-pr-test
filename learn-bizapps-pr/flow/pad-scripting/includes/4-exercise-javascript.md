In this exercise, you'll create a flow that calculates the last day of the current month using JavaScript code.

1. Launch the Power Automate for desktop console and create a new flow named **Last day of the month**.

    ![Screenshot of the Power Automate for desktop Build a flow dialog.](..\media\second-exercise-new-flow.png)

1. Use a **Get current date and time** action to store the current date in a datetime variable.

    ![Screenshot of the Power Automate for desktop Get current date and time action.](..\media\second-exercise-get-current-date-and-time-action.png)

1. Add two **Set variable** actions and initialize them with the month and year properties of the date, respectively.

    ![Screenshot of the Power Automate for desktop Set variable action.](..\media\second-exercise-set-variable-actions.png)

1. Deploy a **Run JavaScript** action and populate it with the code shown in the following image. This action returns a text variable that contains the last day of the given month.

    ![Screenshot of the Power Automate for desktop Run JavaScript action.](..\media\second-exercise-run-javascript-action.png)

1. Add a **Parse text** action in the workspace and use the presented regular expression to remove the date's unnecessary parts.

    ![Screenshot of the Power Automate for desktop Parse text action.](..\media\second-exercise-parse-text-action.png)

1. Use a **Convert text to datetime** action to convert the parsed text into a datetime variable.

    ![Screenshot of the Power Automate for desktop Convert text to datetime action.](..\media\second-exercise-convert-text-to-datetime-action.png)

1. Reconvert the datetime value to text using the **Convert datetime to text** action. We are deploying this action to create a custom format of the date.

    ![Screenshot of the Power Automate for desktop Convert datetime to text action.](..\media\second-exercise-convert-datetime-totext-action.png)

1. To display the final text variable that contains the last day of the month, use a **Display message** action.

    ![Screenshot of the Power Automate for desktop Display message action.](..\media\second-exercise-display-message-action.png)

1. Save the flow and then execute it. You can try different time zones to ensure that the flow can handle all possible scenarios.

    ![Screenshot of the Power Automate for desktop final flow and the save and run buttons.](..\media\second-exercise-final-flow.png)