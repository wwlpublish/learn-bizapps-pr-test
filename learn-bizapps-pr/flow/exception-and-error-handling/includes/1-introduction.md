The ability to handle and recover from unexpected circumstances is a critical factor in automating business processes. The risk of errors is present in any automated task - this risk may come from multiple factors, such as changes in the applications used, changes in business processes, unavailability of hardware, software, files, and services. A robustly automated task should be able to handle, and potentially overcome, such issues during runtime, should the need arise.

Consider the task of updating a client database based on a report downloaded through a web portal. The report is downloaded as an .xlsx file, while the database is hosted on a remote server. This relatively simple task contains quite a few risk factors: the web portal may be down, the report may be empty, or the database may be inaccessible, to name a few. These are all circumstances that could cause the process to crash. To ensure business continuity, the process should contain steps, which would allow it to recover from such scenarios in a meaningful way. This is achieved through the use of exception and error handling.

In this module, you'll learn about the four levels of exception and error handling, and how each level can be used, and apply exception handling actions on an already automated process to prevent crashes, as well as configure the error handling behavior of a process.

By the end of this module, you will be able to understand and apply the available exception and error handling tools, to minimize the risk of process failure.

## Learning objectives

In this module, you will:

- Configure the exception handling properties of individual actions.
- Set up exception blocks, which will handle possible exceptions from groups of actions.
- Configure the error handling properties of individual processes.
- Apply global error handling properties, which will come into effect when any process fails.

## Prerequisites

- Basic familiarity with the WinAutomation Console and Process Designer.
