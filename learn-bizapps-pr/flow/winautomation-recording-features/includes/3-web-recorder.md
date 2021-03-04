Let’s use the Web Recorder to automate a web-based Process. This Process includes logging into a web portal, configuring and generating a report, and logging out.

First, we will have to launch our browser of choice, and visit the web portal. Then, we may start the Web Recorder - either by creating a new Process, or through an already open Designer window - and attach it to the browser:

![Screenshot of the web recorder instance selection continued.](..\media\web-recorder-instance-selection-continued.png)

When the Recorder window appears, we proceed with performing the task manually; first, enter the necessary credentials and press the Login button:

![Screenshot of the live web recorder recording browser actions.](..\media\live-web-recorder.png)

Notice that, as the fields are populated, the relevant Actions are added to the preview. Any actions that the user performs outside the web browser are ignored.

After logging in, we will continue with our task, as usual; we press the **Reports** button:

![Screenshot of the software solutions dashboard.](..\media\software-solutions-dashboard.png)

Use the filters to view all unpaid entries, and generate the report:

![Screenshot of the software solutions reports.](..\media\software-solutions-reports.png)

Now the report is generated, we wish to extract certain columns of data. We will do so by right-clicking on the required data and selecting **Extract Element Value** and then clicking on the appropriate value:

![Screenshot of the element extraction context menu.](..\media\element-extraction-context-menu.png)

To extract the entire column, we will repeat this for the second element in the column as well; the entire column will automatically be extracted:

![Screenshot of the element extraction context menu continued.](..\media\element-extraction-context-menu-continued.png)

Now, simply extracting one element from another column, that column will also be extracted in its entirety, and our end result will be a table:

![Screenshot of the extract element value option.](..\media\element-extraction.png)

![Screenshot of the recorded actions continued.](..\media\recorded-actions-continued.png)

When we have extracted all the required data, we log out of the web portal:

![Screenshot of the software solutions logout.](..\media\software-solutions-logout.png)

![Screenshot of the final recorded actions.](..\media\final-recorded-actions.png)

The Logout button has no description; if we so wish, we may click on it to assign it a name. All Actions in the Recorder window may be edited in the same way at any time:

![Screenshot of the recorded actions description.](..\media\recorded-actions-description.png)

Finally, we press the **Finish** button, to add all the automatically generated Actions to our Process:

![Screenshot of the recorder region workspace.](..\media\recorder-region-workspace.png)

These Actions are now no different from any others: they can be moved, edited, and deleted; other Actions may be added to them, and so forth.
