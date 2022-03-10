Using an @ mention, you can tag other co-owners of the flow. This can be a great way to ask for help or to request feedback.

> [!div class="mx-imgBorder"]
> ![Screenshot showing a comment with a user requesting help with a flow.](../media/co-owner.png)

You can also tag multiple users in a single comment or reply. They'll be notified of each mention by a separate email. Keep that in mind if you're going to mention them in multiple comments.

> [!div class="mx-imgBorder"]
> ![Screenshot showing the email received when you're mentioned in a comment.](../media/at-email.png)

When the receiving user selects Go to comment, the cloud flow designer will load, and the comment will be highlighted. If the user receives multiple mentions, each Go to comment selected will open the flow in a new browser tab.

## Refresh comments

Comments are loaded in the flow designer when the edit session starts for a flow. Any new comments you add will be visible immediately. Comments added by other users while your session is in progress won't be visible immediately. You should close and reopen the edit session to refresh the comment pane.

## Co-presence

As you start collaborating with other flow owners using comments, multiple users can be editing the same flow simultaneously. You can know in near real-time which other users are currently editing the flow. A list of users editing the flow can be found in the upper right corner by the Comments button.

> [!div class="mx-imgBorder"]
> ![Screenshot showing the list of users currently editing the flow.](../media/co-presence.png)

The list is updated periodically as users open and close their edit sessions.

The flow designer allows one primary editor and multiple users to be viewing and commenting on a flow. It's up to the users to self-select who is the primary editor. This is determined by who saves the flow first. After a user saves the flow, any subsequent attempt to save by another user will see the following options to save a copy, discard changes, or overwrite.

> [!div class="mx-imgBorder"]
> ![Screenshot showing this isn't the latest content when there's a conflict in saving the flow.](../media/conflict.png)

Discarding your changes is the safest option but will result in the loss of your changes. **Save a copy** can be helpful if you have made numerous changes and you don't want to lose them. After saving a copy, you can integrate your changes into the original flow later on. In some cases, you can copy and paste your changes from the saved copy into the original flow. The main negative of saving a copy is if it's done frequently and not cleaned up. You can end up with many extra copies cluttering your environment. Use the **Overwrite** button with caution since all other user's changes will be lost. Ideally, use the list of users currently editing the flow to contact them and coordinate a resolution.

The best option is to coordinate ahead of time and avoid conflicting saves. Often teams use work item assignments to designate an owner of a change and assign all work items for the same flow to the same user. Commenting on a flow isn't considered a conflicting save. That is, one can work, others can comment (though the comments won't be immediately visible to others).

Co-owners of flows can also agree if they're responding to a mention in a comment from another user in a flow. They're only viewing and not editing.

Using comments and co-presence can help you build flows as a team and solve more complex automation challenges by using team members' strengths.
