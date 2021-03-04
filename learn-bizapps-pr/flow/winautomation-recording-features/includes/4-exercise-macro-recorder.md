As we have seen so far, web browser-related tasks can also be automated using the Web Recorder; any other tasks, including input and output peripherals (mouse, keyboard, monitor) and the use of local applications, can be developed in a similar fashion using the Macro Recorder.

In this exercise, you will automate a desktop-related task, to get a better grasp of the Macro Recorder, and the capabilities that Recorders provide.

1. Create a new Process using the Process Designer.

1. Add a **Run Application** Action, configured as below:

   ![Screenshot of the run application properties exercise.](..\media\run-application-properties-exercise.png)

1. Run the Process to launch Excel.

1. Click on the Macro Recorder button in the Designer:

   ![Screenshot of the macro recorder button exercise.](..\media\macro-recorder-button-exercise.png)

1. Select **Blank Workbook**.

1. Select the entire first row, then assign it a background color:

   ![Screenshot of the excel exercise with the background color property expanded.](..\media\excel-exercise.png)

1. The Preview window should look like this:

   ![Screenshot of the recorded actions exercise.](..\media\recorded-actions-exercise.png)

The automatically generated comment in the beginning can be deleted; highlight it and press the red ‘X’ to delete it:

![Screenshot of the recorded actions exercise continued.](..\media\recorded-actions-exercise-continued.png)

1. You may go ahead and add a comment as well, by pressing the bubble box button on the lower right:

   ![Screenshot of the recorded actions exercise comment.](..\media\recorded-actions-exercise-comment.png)

1. Press **Finish**. Your recorded Actions have been added to the Process:

   ![Screenshot of the recorded actions exercise comment workspace.](..\media\recorded-actions-exercise-comment-workspace.png)

You may also try experimenting with **Based on Coordinates** recording mode to see the differences between the two approaches.
