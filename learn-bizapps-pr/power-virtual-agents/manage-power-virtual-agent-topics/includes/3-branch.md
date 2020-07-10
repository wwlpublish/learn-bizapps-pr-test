Adding branching into to topic is what truly turns them from a one-way path to a multi-layer conversation. Different forks and paths ensure the customer is provided data and resolutions based the current situation.

Branching allows you to evaluate conditions to initiate conversation nodes to launch another topic, display a message node, or trigger a Power Automate Flow. You can manually add branching conditions between nodes, such as inserting a branch after you ask a question such as "what country do you live in?" The customer's response to the question is stored as a variable, and branch conditions can be built based on that. This is done by selecting **+** to add a node, and then selecting add a condition and selecting the Branch based on a condition option.

> [!div class="mx-imgBorder"]
> [![Add a condition, either for a branch based on a condition or for all other conditions.](../media/3-1.png)](../media/3-1.png#lightbox)

You select how the bot conversation should branch at this point. For example, if you have set up [end-user authentication](https://docs.microsoft.com/power-virtual-agents/advanced-end-user-authentication/?azure-portal=true), then you might want to specify a different message if the user is signed on (which may have happened earlier in the conversation).

> [!div class="mx-imgBorder"]
> [![Choose a variable](../media/3-1-1.png)](../media/3-1-1.png#lightbox)

Depending on what you select in the Identify field of the question node, branching many occur automatically. This is always the case when you select Multiple Choice options. Each option will have a branch created for it. For example, if you have a question node that asks a customer for their preferred store location and provides them with "Seattle" and "Bellevue" as options, a condition branch for each option will be created. You will need to ensure that you are providing a completed path resolution for both items.

> [!div class="mx-imgBorder"]
> [![Branching conditions are automatically created based on the options defined.](../media/3-2.png)](../media/3-2.png#lightbox)
