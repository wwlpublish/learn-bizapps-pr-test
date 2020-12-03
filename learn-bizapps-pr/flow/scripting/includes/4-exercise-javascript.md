In this exercise, you'll create a process that calculates the last day of the current month using JavaScript code. 

1. Launch WinAutomation and create a new process named **Last day of the month**.

    ![The New Process dialog box.](..\media\new-process-javascript-example.png)

1. Use a **Get Current Date and Time** action to store the current date in a **DateTime** variable.

    ![The Get Current Date and Time action with populated fields.](..\media\get-current-date.png)

1. Add two **Set Variable** actions and initialize them with the month and year properties of the date, respectively. 

    ![The Set Variable actions in the workspace.](..\media\set-variables.png)

1. Deploy a **Run JavaScript** action and populate it with the code shown in the following image. This action returns a text variable that contains the last day of the given month.

    ![The Run JavaScript action with populated fields.](..\media\run-javascript-example.png)

1. Add a **Parse Text** action in the workspace and then use the presented regular expression to remove the date's unnecessary parts. 

    ![The Parse Text action with populated fields.](..\media\parse-text.png)

1. Use a **Convert Text to DateTime** action to convert the parsed text into a **DateTime** variable.

    ![The Convert Text to DateTime action with populated fields.](..\media\convert-text-date.png)

1. Reconvert the datetime value to text using the **Convert DateTime to Text** action. You are deploying this action to create a custom format of the date.

    ![The Convert DateTime to Text action with populated fields.](..\media\convert-date-text.png)

1. To display the final text variable that contains the last day of the month, use a **Display Message** action.

    ![The Display Message action with populated fields.](..\media\display-message.png)   

1. Save the process and then run it. You can try different time zones to ensure that the process can handle all possible scenarios.

    ![The final process.](..\media\final-process-javascript.png)   
