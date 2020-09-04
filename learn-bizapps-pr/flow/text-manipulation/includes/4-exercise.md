We are going to develop a Process that prompts the user for their first and last names. The Process then generates a username with the first letter of the user’s first name appended to their last name in lower-case, and randomly generates a temporary password. The output is then displayed to the user.
Our process will:

* Prompt a user to input their first and last name
* Split the two names into separate strings of text
* Shift the two strings to lower case
* Get the first letter of the first name
* Randomly generate a password
* Display a message with the user’s username and password

First, use the **Display Input Dialog** Action. Set the **Title** to **Name Input** and **Input Dialog Message** to **Please enter your first and last name (for example, Norbert Varga):**. This Action will display a message, prompting the user for input.
 
![display input dialog exercise](..\media\display-input-dialog-exercise.png)


Use the **Split Text** Action to split the first and last name into two separate strings of text. In **Text to Split** enter **%UserInput%**.
 
![split text exercise](..\media\split-text-exercise.png)

Use the **Change Text Case** Action. In Text to Convert enter %TextList[0]%. With the index of a list type variable, you provide the first item of the list, which will be the first name. Set **Convert to** to **lowercase**.
 
![change text case exercise](..\media\change-text-case-exercise.png)

 
Add another **Change Text Case** Action. This time, set **Text to Convert** to **%TextList[1]%**, thus referencing the last name. **Convert to** should be set to **lowercase** again. 

The output is stored in a different variable than the previous Change Text Case Action.
 
![change text case exercise continued](..\media\change-text-case-exercise-continued.png)

Use the **Get Subtext** Action to get the first character of the first name. Enter **%TextWithNewCase%** (the variable where the first name in lower-case is stored) as **Original Text**. 

For **Start Index** set **Character Position** to **0**, and for **Length**, **Number of Chars** to **1**. This will get the first character of the text string.
 
![get subtext exercise](..\media\get-subtext-exercise.png)

 
To generate a random password, use the **Create Random Text** Action. The Action’s properties can be left at their default values.
 
![create random text exercise](..\media\create-random-text-exercise.png)

 
Lastly, use the **Display Message** Action. This will display a message box with the user’s username and password. For **Message Box Title** enter **Username & Password**, and for **Message to Display** enter:
Hello, %UserInput%, your username is:
%SubText%%TextWithNewCase2%
Your temporary password is:
%RandomText%

This will display the user’s username (first letter of first name combined with last name) and the result of the Generate Random Text Action as the user’s password.
 
![display message exercise](..\media\display-message-exercise.png)

 

The completed process should look like this:
 
![completed process workspace exercise](..\media\completed-process-workspace-exercise.png)