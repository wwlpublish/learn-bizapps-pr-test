In this exercise, you will be embedding the **Omnichannel Chat Widget** into the Power Apps Customer self-service portal using Portal Management configuration. In your environment, you created a Lamna Healthcare Company Portal using the **Customer self-service portal** template before deploying Microsoft Cloud for Healthcare. Now we will configure the chat widget to show on the customer website.

**Customer self-service portal**: A customer self-service portal enables customers to access self-service knowledge, support resources, view the progress of their cases, and provide feedback.

**Portal Management**: Application to help you get started with the advanced portal configuration. In this walk-through, you will learn how to configure Chat widget in **Portal Management** app.

1. In <https://make.powerapps.com/>, open the **Portal Management** app.

    1. > [!div class="mx-imgBorder"]
    > [![Screenshot of the Apps menu with the Portal Management option selected.](../media/71-portal-management.png)](../media/71-portal-management.png#lightbox)

1. Select **Content Snippets** in the left navigation pane

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Content section on the left navigation menu with the Content Snippets option selected.](../media/72-content-snippets.png)](../media/72-content-snippets.png#lightbox)

1. In **Active Content Snippets**, type "**Chat**" in the **Search** box and press enter.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Active Content Snippets displaying the Customer Self-Service and Healthcare Patient Portal options available.](../media/73-content-snippets-chat.png)](../media/73-content-snippets-chat.png#lightbox)

1. You will see two **Chat Widget Code** records retrieved in the list. Click to open the Chat Widget Code record related to **Customer Self-service.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Active Content Snippets  with the Chat Widget Code Customer Self-Service option selected.](../media/74-chat-widget-customer-self-service.png)](../media/74-chat-widget-customer-self-service.png#lightbox)

1. In the **Chat Widget Code** record associated with Customer self-service, select **Value (HTML)** > **Html** Tab and then paste the **Chat Widget Code snippet** that you copied and stored in the previous task.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Chat Widget HTML code snippet on the General tab.](../media/75-chat-widget-code-snippet.png)](../media/75-chat-widget-code-snippet.png#lightbox)

1. Click **Save & Close**.

    > [!div class="mx-imgBorder"]
    > [![Image of the Save and Close option highlighted on the horizontal navigation bar.](../media/76-chat-widget-save-close.png)](../media/76-chat-widget-save-close.png#lightbox)

1. Now open the other **Chat Widget Code** associated with **Healthcare Patient Portal**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Active Content Snippets with the Chat Widget Code for the Healthcare Patient Portal name selected.](../media/77-healthcare-patient-portal.png)](../media/77-healthcare-patient-portal.png#lightbox)

1. In the **Chat Widget Code** record associated with the Healthcare Patient Portal, paste in **Value** (HTML) the same **Chat Widget Code snippet** that you copied and stored previously and added to the customer self-service chat widget code. Replace any value that may have already populated the field.

    > [!div class="mx-imgBorder"]
    > [![Image of the HTML value code on the Chat Widget Code General tab.](../media/78-value-code-snippet.png)](../media/78-value-code-snippet.png#lightbox)

1. Select **Save and Close**.

**Congratulations!** In this exercise you have successfully updated the chat widget in the Power App Portal Content Snippets. With this configuration, the Health Bot will be visible on the Power Apps portal, for both the customer self-service template and the healthcare patient portal template.
