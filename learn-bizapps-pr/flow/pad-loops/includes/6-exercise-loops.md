As stated above, loops enable the user to repeat a block of actions, in order to perform certain tasks on large amounts of data.

In this exercise, you will apply loop actions in order to perform certain actions over multiple iterations, and access the elements of a list.

Before starting, you should create two empty folders, named **PDF** and **DOCX**, inside the **My Documents** folder.

1. Use the **Get Special Folder** action to retrieve the **Desktop** and **My Documents** folder paths:

    ![Screenshot of the get special folder action properties dialog for Desktop.](..\media\get-special-folder-action-properties.png)

    ![Screenshot of the get special folder action properties dialog for Documents.](..\media\get-special-folder-action-properties-continued.png)

2. Use the **Get Files in Folder** action to retrieve all .pdf and .docx files in the desktop:

    ![Screenshot of the get files in folder action properties dialog for Desktop.](..\media\get-files-in-folder-action-properties.png)

3. Add a **For Each** loop in order to loop through the list of retrieved files. The loop will iterate through each one of the retrieved files, storing it in the **%CurrentItem%** variable:

    ![Screenshot of the for each action properties dialog.](..\media\for-each-action-properties.png)

4. Within the loop, use the **If** and **Else** actions to determine whether the current file is a .pdf or a .docx file, and move it to the appropriate subfolder inside **My Documents**:

    ![Screenshot of the for each if workspace example.](..\media\for-each-if-workspace-example.png)

5. As before, retrieve all the .txt files in the desktop:

    ![Screenshot of the get files in folder action properties dialog.](..\media\get-files-in-folder-action-properties-continued.png)

6. This time, instead of using a **For Each** loop to cycle through each of the retrieved files, we will add a **loop** action, to make use of the loop Index. The loop will start at 0, and end after the number of iterations is equal to the number of files retrieved. To achieve this, we will use the list variable’s **count** property:

    ![Screenshot of the loop action properties select variable pop-out.](..\media\loop-action-properties-select-variable-popout.png)

    ![Screenshot of the loop action properties dialog.](..\media\loop-action-properties-continued-2.png)

7. Within the loop, add a **Write Text to File** action to add the loop Index number to the contents of the .txt file. Since the **loop** action only increases the loop index, the file in question will have to be retrieved using the %Files% variable and the loop Index:

    ![Screenshot of the write text to file action properties dialog.](..\media\write-text-to-file-action-properties.png)
