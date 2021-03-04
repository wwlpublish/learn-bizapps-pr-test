As stated above, loops enable the user to repeat a block of actions, in order to perform certain tasks on large amounts of data.

In this exercise, you will apply loop actions in order to perform certain actions over multiple iterations, and access the elements of a list.

Before starting, you should create two empty folders, named **PDF** and **DOCX**, inside the **My Documents** folder.

1. Use the **Get Special Folder** action to retrieve the **Desktop** and **My Documents** folder paths:

    ![Screenshot of Properties of 'Get Special Folder' action dialog with Special Folder Name set to DesktopDirectory.](..\media\get-special-folder-action-properties.png)

    ![Screenshot of Properties of 'Get Special Folder' action dialog with Special Folder Name set to Personal.](..\media\get-special-folder-action-properties-continued.png)

2. Use the **Get Files in Folder** action to retrieve all .pdf and .docx files in the Desktop:

    ![Screenshot of Properties of 'Get Files in Folder' action dialog with File Filter set to star dot P D F; star dot DOC X.](..\media\get-files-in-folder-action-properties.png)

3. Add a **For Each** loop in order to loop through the list of retrieved files. The loop will iterate through each one of the retrieved files, storing it in the %CurrentItem% variable:

    ![Screenshot of Properties of 'For Each' action dialog.](..\media\for-each-action-properties.png)

4. Within the loop, use the **If** and **Else** actions to determine whether the current file is a .pdf or a .docx file, and move it to the appropriate subfolder inside **My Documents**:

    ![Screenshot of for each if workspace example.](..\media\for-each-if-workspace-example.png)

5. As before, retrieve all the .txt files in the Desktop:

    ![Screenshot of Properties of 'Get Files in Folder' action with File Filter set to star dot T X T.](..\media\get-files-in-folder-action-properties-continued.png)

6. This time, instead of using a **For Each** loop to cycle through each of the retrieved files, we will add a **loop** action, to make use of the loop Index. The loop will start at 0, and end after the number of iterations is equal to the number of files retrieved. To achieve this, we will use the list variable’s **count** property:

    ![Screenshot of Properties of 'Loop' action with the Select a variable for property "End To" dialog open.](..\media\loop-action-properties-select-variable-popout.png)

    ![Screenshot of Properties of 'Loop' action with the End To property set to %Files.Count%.](..\media\loop-action-properties-continued-2.png)

7. Within the loop, add a **Write Text to File** action to add the loop Index number to the contents of the .txt file. Since the **loop** action only increases the loop Index, the file in question will have to be retrieved using the %Files% variable and the loop Index:

    ![Screenshot of Properties of 'Write Text to File' action dialog.](..\media\write-text-to-file-action-properties.png)
