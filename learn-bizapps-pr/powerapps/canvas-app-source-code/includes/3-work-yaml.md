After your app is unpacked, extracted formulas are stored in the text files using a subset of [YAML](https://yaml.org/?azure-portal=true). YAML is a human friendly data serialization language. The goal is to make it easy to read and write the source and to determine the differences between the versions. You can also edit these files using any text editor as long as you follow the Power Fx YAML formula conventions that have been adopted.

The following is a label control represented as YAML:
```yml
   LblAppName1 As label:
        Fill: =RGBA(58, 58, 58, 0)
        Height: =88
        Size: =27
        Text: ="Companies"
        Width: =Parent.Width - Self.X - IconSortUpDown1.Width - IconNewItem1.Width - IconRefresh1.Width
        Wrap: =false
        X: =20
        ZIndex: =2
```
YAML uses key-value pairs to represent the data and supports nesting of the pairs. For example, an item like lblAppName1 can have indented key-value pairs for Fill, Height, Size, etc. YAML uses indentation to determine structure. Spaces are used for indentation, but tabs are not allowed.

There are three unique aspects of how Power Fx formulas are embedded in YAML:

-   **Controls are typed with the As keyword** You can see label control in the example above defined using *lblAppName1 as Label:* expression. Normally YAML has only a single name to the left of the : when providing a property value. But there is nothing in the YAML specifications that excludes more complex left-hand side expressions, and the Power Fx YAML syntax takes advantage of this both to name the property and to provide its type.

-   **All formulas start with a leading** Just like Excel, the = introduces a formula rather than a static value. You don't have to type the leading equals in Power Apps Studio but if you notice the formula bar it is always there. The leading = also helps avoid the normal data type interpretation that YAML does for static value, that is not appropriate for formulas.

-   **Some formulas must be expressed in YAML multi-line syntax** If you have a formula that contains a string with an embedded **\#**, it is interpreted by YAML as the start of a comment, and the rest of the line will be truncated. To avoid this, the formula must be expressed using YAML's multi-line syntax, most common is the use of the \| syntax.

Learn more about the Power Apps YAML source file format details in [Microsoft Power Fx YAML Formula Grammar](/power-platform/power-fx/yaml-formula-grammar/?azure-portal=true).

## Folder structure

When you unpack a canvas app a [set of files and folders](/powerapps/developer/data-platform/powerapps-cli?azure-portal=true#folder-structure) is created. The following are the key files and folders you will find after running unpack:

**\src** - the control and component files. This contains the sources.

**\*.fx.yaml** - the formulas extracted from the control.json file. This is the place to edit your formulas.

**CanvasManifest.json** - a manifest file. This contains what is normally in the header, properties, and publishInfo.

**\*.json** - the raw control.json file.

**\EditorState\*.editorstate.json** - cached information for Studio to use.

**\DataSources** - all data sources used by the app.

**\Connections** - connection instances saved with this app and used when reloading into studio.

**\Assets** - media files embedded in the app.

**\pkgs** - A downloaded copy of external references, such as templates, API Definition files, and component libraries. These are similar to nuget/npm references.

**\other** - all miscellaneous files needed to recreate the .msapp

**entropy.json** - volatile elements (like timestamps) are extracted to this file. This helps reduce noisy diffs in other files while ensuring that we can still round trip.

Holds other files from the msapp, such as what is in \references.

The files that end with \*.fx.yaml are the ones where you can edit formulas. As you explore the extracted files you will find that not all of them contain YAML, many are in their native format and are not meant to be edited outside Power Apps Studio.

## Merging source changes

One of the scenarios that is enabled by unpacking is having multiple people edit an app and merge changes in source control. In this scenario, you want to minimize conflicts. For example, editing formulas on the same control will likely cause a conflict, but two people editing different screens is less likely to.

Be aware if you create the app in the cloud, download it and edit it, when you upload the repacked version, it will overwrite any changes done to the cloud version since it was downloaded.

To avoid overwriting and losing any work done online in this scenario you would want to download the app from the cloud again, unpack, commit the file changes, resolve any conflicts, and then repack and upload the new app. The important thing is to make source control contains the master copy of your app.

Some conflicts will occur just by the nature of multiple people editing concurrently. For example, if two people picked the same control name on different screens that would create a merge conflict. You can read more on merging changes with Power Apps studio in [Microsoft Power Platform CLI documentation](/powerapps/developer/data-platform/powerapps-cli?azure-portal=true#merging-changes-with-power-apps-studio).
