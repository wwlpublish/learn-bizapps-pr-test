In this exercise, you will develop a process that prompts the user for their first and last name. The process will then generate a username by using the first letter of the user’s first name, appended to their last name in lowercase. Then, the system will randomly generate a temporary password and display the output to the user.

## Tasks

For this exercise, you'll create a process that will:

- Prompt a user to enter their first and last name.
- Split the two names into separate strings of text.
- Shift the two strings to lowercase.
- Get the first letter of the first name.
- Generate a password randomly.
- Display a message with the username and password.

## Steps

Select the **Display Input Dialog** action, and then follow these steps: 

1. Set the **Title** property to **Name Input** and the **Input Dialog Message** property to **Please enter your first and last name (for example, Norbert Varga)**. This action will display a message that prompts the user for input.
 
![display input dialog exercise](..\media\display-input-dialog-exercise.png)


2. Use the **Split Text** action to split the first and last name into two separate strings of text. In the **Text to Split** field, enter **%UserInput%**.
 
![split text exercise](..\media\split-text-exercise.png)

3. Select the **Change Text Case** action. 

4. In the **Text to Convert** field, enter **%TextList[0]%**. 

5. With the index of a list type variable, provide the first item of the list, which will be the first name. Set the **Convert to** property to **lowercase**.
 
![change text case exercise](..\media\change-text-case-exercise.png)

6. Add another **Change Text Case** action. This time, set the **Text to Convert** property to **%TextList[1]%**, thus referencing the last name. 

7. Set the **Convert to** property to **lowercase** again. 

The output is stored in a different variable than the previous **Change Text Case** action.
 
![change text case exercise continued](..\media\change-text-case-exercise-continued.png)

8. Select the **Get Subtext** action to get the first character of the first name. 

9. In the **Original Text** field, enter **%TextWithNewCase%** (the variable where the first name in lowercase is stored). 

10. In the **Start Index** section, set **Character Position** to **0**.

11. In the **Length** section, set **Number of Chars** to **1**. This setting will get the first character of the text string.
 
![get subtext exercise](..\media\get-subtext-exercise.png)

12. To generate a random password, use the **Create Random Text** action. The action’s properties can be left at their default values.
 
![create random text exercise](..\media\create-random-text-exercise.png)

13. Select the **Display Message** action, which will display a message box with the new username and password. In the **Message Box Title** field, enter **Username & Password**, and in the **Message to Display** field, enter the following content:

**Hello, %UserInput%, your username is: %SubText%%TextWithNewCase2% Your temporary password is: %RandomText%**

The username (first letter of first name, combined with last name) will be displayed and the result of the **Generate Random Text** action will show as the user’s password.
 
![display message exercise](..\media\display-message-exercise.png)

The completed process should look like the following figure.
 
![completed process workspace exercise](..\media\completed-process-workspace-exercise.png)
