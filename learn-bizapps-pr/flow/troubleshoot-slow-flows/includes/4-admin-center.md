Users generally have good intentions, but they can easily overlook the potential for exposure from data leakage to services and audiences that shouldn't have access to the data.

## Data policies

You can create data loss prevention (DLP) policies that can act as guardrails to help prevent users from unintentionally exposing organizational data. DLP policies can be scoped at the environment level or tenant level, offering flexibility to craft sensible policies that strike the right balance between protection and productivity. For tenant-level policies, you can define the scope to be all environments, selected environments, or all environments except ones you specifically exclude. Environment-level policies can be defined for one environment at a time.

DLP policies enforce rules for which connectors can be used together by classifying connectors as either **Business** or **Non-Business.** If you put a connector in the Business group, it can only be used with other connectors from that group in any given app or flow. Sometimes you might want to block the usage of certain connectors altogether by classifying them as **Blocked**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Platform admin center on the Data policies page on the Assign connectors step.](../media/image-27.png)](../media/image-27.png#lightbox)

When a new policy is created, by default all connectors are placed in the Non-Business group. From there, they can be moved to Business or Blocked based on your preference. You manage the connectors in a data group when you create or modify the properties of a DLP policy from the admin center.

## Confirm connectors are in the same group

Data cannot be shared among connectors that are in different groups. For example, if you place SharePoint and Outlook connectors in the Business group and you place Twitter in the Non-Business group, makers can't create a flow that uses both the SharePoint and Twitter connectors. This in turn restricts data flows between these two services in Microsoft Power Platform.

Although data cannot be shared among services in different groups, it can be shared among services within a specific group. From the earlier example, because SharePoint and Outlook were placed in the same data group, makers can create a flow that uses both SharePoint and Outlook connectors together. This in turn allows data flows between these two services in Microsoft Power Platform.

Here's an example of the error you'll see when you try to use two connectors who aren't part of the same DLP group.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Flow checker errors dialog showing that Create item violates admin data policy.](../media/image-28.png)](../media/image-28.png#lightbox)
