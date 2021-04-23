The easiest way to build out Robotic Process Automation (RPA) is to take one small step at a time and build and test that step. First, you created the desktop flow to perform actions on the invoicing app. Next, you created the input and output variables, or the information that would change every time the flow ran. Then you configured a gateway and built a cloud flow that will allow you to connect to the other resources, which exist in your organization. Finally, you have created a solution and a trigger starting in Outlook. Let's test these new steps to ensure everything is performing as expected.

Select **Test** at the top-right of the screen and then select **Manually** and **Save & Test**.

> [!div class="mx-imgBorder"]
> [![Screenshot of manually selected for test flow.](../media/test-manually.png)](../media/test-manually.png#lightbox)

Open the Power Automate Desktop Application and send yourself an email with an attachment and the subject "new invoice". The flow will appear with indications on each step to show you where your flow is in the process. Try not to interact with your mouse or keyboard while the flow is running as it may interrupt the process. When the testing is complete, you will see the following to denote that your flow ran successfully.

> [!div class="mx-imgBorder"]
> [![Screenshot of the successful flow message.](../media/success.png)](../media/success.png#lightbox)

Now you have completed the process to build a solution with a cloud flow that is triggered with Outlook!