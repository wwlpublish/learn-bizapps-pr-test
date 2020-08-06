As stated above, Loops enable the user to repeat a block of Actions, in order to perform certain tasks on large amounts of data.

In this exercise, you will apply Loop Actions in order to perform certain Actions over multiple iterations, and access the elements of a list.

Before starting, you should create two empty folders, named **PDF** and **DOCX**, inside the **My Documents** folder.

## Step 1
Use the **Get Special Folder** Action to retrieve the **Desktop** and **My Documents** folder paths:

![get special folder action properties](..\media\get-special-folder-action-properties.png)

![get special folder action properties continued](..\media\get-special-folder-action-properties-continued.png)

## Step 2
Use the **Get Files in Folder** Action to retrieve all .pdf and .docx files in the Desktop:

![get files in folder action properties](..\media\get-files-in-folder-action-properties.png)

## Step 3
Add a **For Each** loop in order to loop through the list of retrieved files. The loop will iterate through each one of the retrieved files, storing it in the %CurrentItem% variable:
 


![for each action properties](..\media\for-each-action-properties.png)

## Step 4
Within the loop, use the **If** and **Else** Actions to determine whether the current file is a .pdf or a .docx file, and move it to the appropriate subfolder inside **My Documents**:
 


![for each if workspace example](..\media\for-each-if-workspace-example.png)

## Step 5
As before, retrieve all the .txt files in the Desktop:
 


![get files in folder action properties continued](..\media\get-files-in-folder-action-properties-continued.png)

## Step 6
This time, instead of using a **For Each** loop to cycle through each of the retrieved files, we will add a **Loop** Action, to make use of the Loop Index. The loop will start at 0, and end after the number of iterations is equal to the number of files retrieved. To achieve this, we will use the list variable’s **count** property:
 


![loop action properties select variable popout](..\media\loop-action-properties-select-variable-popout.png)

 


![loop action properties continued 2](..\media\loop-action-properties-continued-2.png)

## Step 7
Within the loop, add a **Write Text to File** Action to add the Loop Index number to the contents of the .txt file. Since the **Loop** Action only increases the Loop Index, the file in question will have to be retrieved using the %Files% variable and the Loop Index:
 


![write text to file action properties](..\media\write-text-to-file-action-properties.png)

