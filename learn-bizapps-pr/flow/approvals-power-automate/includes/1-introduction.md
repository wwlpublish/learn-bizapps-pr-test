It's important that we understand the fundamental information about the approval connector, specifically, what type of connector it is, can we block it in the data loss prevention policy and are both actions and triggers available for it.

## Is it a standard or premium connector?

Power Automate gives you the flexibility to connect to either data or service using a connector. Connectors come in two tiers, standard and premier. Approval connectors are a part of the standard tier. Standard connectors are part of your Microsoft 365 licenses and no other license is needed. Premier connectors require either a per flow or a per user license. For more information on flow licenses, see the links Summary Unit at the end of this module.

##  Is it blockable?

An organization's data is critical to its success. Data needs to be readily available for decision-making, but also needs to be protected so that it isn't shared with audiences who shouldn't have access to it. To protect data, you can use **Power Automate** to create and enforce **data loss prevention (DLP)** policies that define the consumer connectors that specific business data can be shared with.

Connectors can be added to either one of the three groups available in DLP, **Business, Non-Business and Blocked**. The **Approval** connector cannot be added to Blocked, it can only be added to Business or Non-Business.

> [!div class="mx-imgBorder"]
> [![Screenshot of approvals connector noted as no for blockable.](../media/approval-connector.png)](../media/approval-connector.png#lightbox)

## Can it be used as an action and trigger?

Approval connector does not have a trigger option. This means approvals cannot be the first step in the flow, that is, the reason why the flow was initiated.

> [!div class="mx-imgBorder"]
> [![Screenshot of triggers with message none were found.](../media/no-trigger-approval.png)](../media/no-trigger-approval.png#lightbox)

There are three actions available for **Approvals.**

> [!div class="mx-imgBorder"]
> [![Screenshot of the actions list with three available.](../media/actions-approval.png)](../media/actions-approval.png#lightbox)