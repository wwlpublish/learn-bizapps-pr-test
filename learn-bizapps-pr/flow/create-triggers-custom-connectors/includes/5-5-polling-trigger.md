If an underlying API does not support webhooks, polling triggers can be a good alternative. They can be implemented using standard retrieve methods that support result filtering for example, List Invoices after a certain date.  

System will call your API regularly to check if there are any changes in the data. Polling interval is controlled by the system and is usually around 2 minutes. Polling triggers also support batch result processing that could be beneficial for processing large volumes of changes. 

In this video, we add a polling trigger to our WooCommerce custom connector we have created earlier. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyYqC/]