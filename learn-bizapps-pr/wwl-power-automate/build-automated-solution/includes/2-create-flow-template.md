With the hundreds of triggers, actions and connectors sometimes the hardest part about Power Automate can be figuring out where to get started. To help you get started, there are countless flow templates available to help you build a solution. To see all of the available templates you can sign into [Power Automate](https://ms.flow.microsoft.com/), and select **Templates** from the left-hand menu. 
    [![Power Automate template archive](../media/img1.png)](../media/img1-1.png#lightbox)

From here, you can search by a specific word or phrase like "Common Data Service" or you can browse based on category. 

If you click on a specific template, you will see details about the template including the data sources it will connect to. 
    ![template click in details](../media/img2.png)

Templates are great for getting started and support being customized. So you can take a template and extend it to meet your business needs.

## Create a flow to save email attachments to OneDrive for Business

It can be time consuming to search for attachments through email at Contoso Manufacturing. To alleviate those time consuming searches you can build a flow that stores all of your email attachments in a folder on your Microsoft OneDrive for Business account. Thankfully, there is a template to help you get started. 

1. From the list of templates search for "**Save Office 365 email attachments to OneDrive for Business**" and then **click on the template** to start using it.

2. Click **Create Flow** at the bottom of the screen to create the flow.
    ![Build flow for Office 365 emails](../media/img3.png)

**Save Office 365 email attachments to OneDrive for Business** is one of the one-click templates, in which you can answer questions that are necessary to build the flow, so that you don't have to write a line of code.

On the template graphic, there's a description of what the template does and what it needs to succeed.

You'll be asked to provide credentials for the Microsoft Office 365 Outlook and Microsoft OneDrive for Business services. If you regularly use both services, you'll already be signed in.

- The flow connects to your work email to get any attachments.

- The flow will then create a folder on your OneDrive for Business account to automatically put every attachment that's sent to your work email address in that folder.

Now that the flow is created, you can click Edit to see the details of what was created for you.

From the flow builder, you can now click through the trigger and the actions to see how this flow was built for you. As you can see, there is no code and everything is accessible to customize or extend to better meet your business needs. For example, maybe try configuring the flow to only process for emails from your boss. Here is a hint: Click on Show advanced options for the On new email trigger. 

Now that you have seen how easy it is to start from a template, let's talk about a couple of key concepts.

## Important concepts in Microsoft Flow

Keep these concepts in mind when building flows:

- Every flow has two main parts: a trigger, and one or more actions.

- You can think of the trigger as the starting action for the flow. The trigger can be something like a new email arriving in your inbox or a new item being added to a SharePoint list.

- Actions are what you want to happen when a trigger is invoked. For example, the new email trigger will start the action of creating a new file on OneDrive for Business. Other examples of actions include sending an email, posting a tweet, and starting an approval.

These concepts will come into play later, when you build your own flows from scratch.

## Trigger or run the flow

With Power Automate, you don't think of running a flow the same way as you do with Power Apps. Instead, you perform the activity that triggers the flow to run. In the case of the previous flow, instead of periodically running the flow manually it would automatically run every time use receive a new email with an attachment. This is because that is what the trigger is set to respond to. 

When defining triggers, there are a few different types:

- When something changes: These are triggers that run when data is changed. It could be a new item created in SharePoint, a lead is updated in Dynamics, or when an event has been deleted from Outlook for example.

- On a schedule: You can set up a flow to be triggered at a certain time of a day and with a recurrence. This allows for workflows such as checking every day at 8 AM if there are account renewals pending and if so, sending an email to the necessary people.

- On a button press: This trigger takes shape in many different ways. This can be when a flow virtual button is run through the mobile app, or a physical button is clicked with 3rd party options, or even when a button is pressed inside of Power Apps. This gives you that control to "run" a flow on-demand.