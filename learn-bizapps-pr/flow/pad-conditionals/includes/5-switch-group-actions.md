The **Switch** group of actions is used when a flow's next steps depend on the value of a specific variable. Let’s clarify this with an example.

The following flow retrieves a list of all the files in the **Documents** folder, and produces a file count based on 3 types of filenames: those containing the word **Payments**, those containing the word **Employees**, and those containing the word **Schedule**. A message containing the file counts is then displayed on the screen for the user to review.

First, we will retrieve the path to the Documents folder, retrieve all the files inside, and initialize four variables to act as file counters:

![Initializing file counters](..\media\initializing-file-counters.png)

Because the files located in the Documents folder are stored in a list, we will use a **For Each** loop to iterate through each file:

![For each action added](..\media\for-each-action-added.png)

Now, each file must be checked for the required keywords. To achieve this, we will use a **Switch** action:

![Switch current item](..\media\switch-current-item.png)

![Switch action added](..\media\switch-action-added.png)

Next, we will add the alternative cases, using **Case** actions. The **Contains** comparison is used, since filenames may contain more characters than our keywords:

![Case contains payments](..\media\case-contains-payments.png)

Eventually, the flow should look like this:

![Cases added](..\media\cases-added.png)

We will also add an unconditional alternative, in case some files contain none of our keywords:

![Default case added](..\media\default-case-added.png)

Inside each case, we will increase the respective counter variable; finally, we will add a message box to be displayed:

![Increasing counters based on switch value](..\media\increasing-counters-based-on-switch-value.png)
