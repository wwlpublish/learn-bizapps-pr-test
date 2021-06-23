The If group of actions is used when one or more conditions should be taken into account in order to determine the next steps of a process.

Consider the following example: an Excel file contains incoming support ticket information, including urgency, and the customer’s subscription plan. Based on this information, the process will determine the ticket’s maximum response time, and write it into the corresponding cell.

First, we open the Excel report and determine the range of the data. Then, we will loop through each row, reading the urgency and subscription plan:

![Screenshot of the following Read from Excel Loop action.](..\media\read-from-excel-loop.png)

```console
Launch Excel
Launch Excel and open document
C:\Users\x\Desktop\Test.xlsx

Get First Free Column/Row from Excel Worksheet
Get the first free column/row in the active worksheet of the Excel document whose Instance is stored in %ExcelInstance%

Loop
Loop starting from 1 to %FirstFreeRow-1% In each iteration increment the current index by 1 Store current index into %LoopIndex%

  Read from Excel Worksheet
  Read the Value of the cell in column 4 row %LoopIndex% and store it into %UrgentCell%

  Read from Excel Worksheet
  Read the Value of the cell in column 3 row %LoopIndex% and store it into %SubscriptionCell%

End Loop
```

Now, for each of these rows, the maximum response time must be calculated. The company’s service level agreements (SLAs) are as follows:

* Free users get a response within 30 days of submitting a ticket
* Basic users get a response within seven days
* Premium users get a response within one day

Also, any ticket marked as urgent must receive a response within 12 hours, regardless of the user’s subscription plan.

Since the information needed to figure out the maximum response time comes from more than one source, we will use an If conditional. We begin by assessing the ticket’s urgency, since it overrides the subscription plan in this case:

![Screenshot of Properties of 'If' action. First Operand is %UrgentCell%, Operator is =, Second Operand is Urgent, and the OK button is highlighted.](..\media\if-cell-contains-urgent.png)

![Screenshot of the following Read and write to Excel Loop action. If the cell contains urgent, write 12 hours.](..\media\if-cell-contains-urgent-write-12-hours.png)

```console
Launch Excel
Launch Excel and open document
C:\Users\x\Desktop\Test.xlsx

Get First Free Column/Row from Excel Worksheet
Get the first free column/row in the active worksheet of the Excel document whose Instance is stored in %ExcelInstance%

Loop
Loop starting from 1 to %FirstFreeRow-1% In each iteration increment the current index by 1 Store current index into %LoopIndex%

  Read from Excel Worksheet
  Read the Value of the cell in column 4 row %LoopIndex% and store it into %UrgentCell%

  Read from Excel Worksheet
  Read the Value of the cell in column 3 row %LoopIndex% and store it into %SubscriptionCell%

  If %UrgentCell% = Urgent then
    Write to Excel Worksheet
    Write the value 12 hours into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%
  End If

End Loop
```

Afterward, add each individual case as an alternative condition:

![Screenshot of Properties of 'Else If' action. First Operand is %SubscriptionCell%, Operator is =, Second Operand is Premium, and the OK button is highlighted.](..\media\else-if-cell-contains-premium.png)

Eventually, the process will look like this:

![Screenshot of the following If, Else if final structure.](..\media\if-else-if-final-structure.png)

```console
Launch Excel
Launch Excel and open document
C:\Users\x\Desktop\Test.xlsx

Get First Free Column/Row from Excel Worksheet
Get the first free column/row in the active worksheet of the Excel document whose Instance is stored in %ExcelInstance%

Loop
Loop starting from 1 to %FirstFreeRow-1% In each iteration increment the current index by 1 Store current index into %LoopIndex%

  Read from Excel Worksheet
  Read the Value of the cell in column 4 row %LoopIndex% and store it into %UrgentCell%

  Read from Excel Worksheet
  Read the Value of the cell in column 3 row %LoopIndex% and store it into %SubscriptionCell%

  If %UrgentCell% = Urgent then
    Write to Excel Worksheet
    Write the value 12 hours into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else If %SubscriptionCell% = Premium then
    Write to Excel Worksheet
    Write the value 1 Day into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else If %SubscriptionCell% = Basic then
    Write to Excel Worksheet
    Write the value 7 Days into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else If %SubscriptionCell% = Free then
    Write to Excel Worksheet
    Write the value 30 Days into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  End If

End Loop
Close Excel
Save the Excel document and close the Excel Instance stored into %ExcelInstance%
```

Now, all scenarios have been covered. However, the process should also address the case that there might be a value in the Excel file that is not one of the standard values. In such cases, we would like someone to look into the matter personally. For this reason, we will also add a final alternative:

![Screenshot of the following If, Else if, Else final structure.](..\media\if-else-if-else-final-structure.png)

```console
Launch Excel
Launch Excel and open document
C:\Users\x\Desktop\Test.xlsx

Get First Free Column/Row from Excel Worksheet
Get the first free column/row in the active worksheet of the Excel document whose Instance is stored in %ExcelInstance%

Loop
Loop starting from 1 to %FirstFreeRow-1% In each iteration increment the current index by 1 Store current index into %LoopIndex%

  Read from Excel Worksheet
  Read the Value of the cell in column 4 row %LoopIndex% and store it into %UrgentCell%

  Read from Excel Worksheet
  Read the Value of the cell in column 3 row %LoopIndex% and store it into %SubscriptionCell%

  If %UrgentCell% = Urgent then
    Write to Excel Worksheet
    Write the value 12 hours into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else If %SubscriptionCell% = Premium then
    Write to Excel Worksheet
    Write the value 1 Day into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else If %SubscriptionCell% = Basic then
    Write to Excel Worksheet
    Write the value 7 Days into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else If %SubscriptionCell% = Free then
    Write to Excel Worksheet
    Write the value 30 Days into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  Else
    Write to Excel Worksheet
    Write the value Unspecified into cell in column 4 and row %LoopIndex% of the Excel Instance stored into %ExcelInstance%

  End If

End Loop
Close Excel
Save the Excel document and close the Excel Instance stored into %ExcelInstance%
```

Now, in case of unexpected input, the maximum time will be designated as Unspecified.
