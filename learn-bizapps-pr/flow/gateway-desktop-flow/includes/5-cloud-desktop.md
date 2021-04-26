Once you have connected to your desktop, Power Automate will prompt you for information specific to your desktop flow. Use the dropdown to select the name of your desired flow and choose Attended for your Run Mode.

> [!div class="mx-imgBorder"]
> [![Screenshot of desktop flow and run mode menus.](../media/choose-desktop-flow.png)](../media/choose-desktop-flow.png#lightbox)

Once you have chosen your desktop flow, any input variables you have defined in your flow will be requested. You can see that the Invoice flow below requests an Amount, a Contact email, and an Account name to feed into the Contoso Invoicing App. Put some placeholders in these fields to test your flow before connecting it to other data sources such as Teams, Outlook, or SharePoint. **Save** your flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of placeholders entered for amount, email, and name fields.](../media/placeholders.png)](../media/placeholders.png#lightbox)

Now that you have configured your desktop connection and created a cloud flow to trigger your desktop flow and provide inputs, you can test that everything is functioning properly.