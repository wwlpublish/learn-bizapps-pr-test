Monitor supports three options for collaborating with others using
Monitor.

-   **Download/Upload** - This allows collaboration by saving a Monitor
    session to a local file that could be reloaded later or shared with
    someone else to collaborate. For example, the session could be saved
    locally and then uploaded and attached to a work item that could be
    assigned to another developer. The assigned developer could reload
    this session into Monitor on their own schedule to see the events
    that occurred.

-   **Invite User** - This allows you to collaborate in real-time with
    another person to watch the Monitor event log as you run the
    application from Power Apps Studio. Because the app is run from
    Power Apps Studio this is intended for user during development of
    the app and not for supporting deployed apps. For example, this
    might be helpful in a scenario where another colleague on your team
    created a custom connector and you\'re having problems using it. You
    could invite that colleague to view your application\'s use of the
    connector and monitor it using the Invite user feature.

-   **Connect User** - This allows you to use Monitor to connect to a
    remote user running a published Power Apps canvas app. For example,
    a user might be experiencing a problem that you aren\'t able to
    reproduce in your development environment. Using connect user you
    can invite them to run the application while you watch the event log
    in Monitor.

Regardless of which option you choose collaboration can speed up
resolution of app problems. In all these scenarios users that you
collaborate with will have access to the events and the data that was
used in the app. In the rest of this module will look at some other
things to consider when you\'re using each of the options.

## Using Download/Upload

Built into Monitor is the ability to download the current session's
events to a local file. The downloaded file can be loaded back into any
Monitor session using the upload feature. Don't be concerned
with the contents of the file, it's simply to allow the events to be
reloaded later. You can initiate these actions from any Monitor session
using the command bar buttons.

:::image type="content" source="../media/download-monitor.png" alt-text="![Screenshot showing upload and download command bar buttons]":::

The simplest use of the downloaded file is to load it back up later into
your own Monitor session. For collaboration the file can be shared
(email, OneDrive, GitHub Issues, or Azure DevOps Work items, etc.) with
anyone that has Monitor access and they can reload the file even if they
don't have edit access to the app that was monitored. This can allow you
to consult with a colleague that might be more familiar with some of the
interactions of specific connectors.

This option can also be useful to save a baseline of an app that you can
use to compare to in the future. For example, imagine you were having
slow queries. Wouldn\'t it be nice to look at what those queries were
the last time you did some testing?

Using the download and upload process is best for collaborating when you
don\'t need real-time collaboration. It can work well where the people
involved are in different time zones.

## Using Invite user

When you use Invite user, you are inviting the other user in your
organization to access Monitor and see the events you are generating by
previewing the app in Power Apps Studio. You can initiate the invite by
selecting Invite user from the command bar. The invite link is generated
when you provide the user information.

:::image type="content" source="../media/invite-user.png" alt-text="![Screenshot showing the invite people to session link]":::

You must copy the link and provide it to the user for them to launch
Monitor listening to your session. The link is only good for 60 minutes.
If you need longer, you must remove and re-invite the user. If you
invite the wrong user, simply remove the invite. They are not notified
when you invite them.

The following diagram illustrates what is happening. You are User A, the
other user is User B.

:::image type="content" source="../media/invite-process.png" alt-text="![Screenshot showing what happens when you invite a user]":::

Each user receives their own copy of the events. That means you can
browse, view, and inspect the app events independently, without
interfering with each other or handing control back and forth to
identify the problem. For example, if you select Clear data, it only
clears your event log and not for other users.

Keep in mind that while the other user sees the Monitor events, they do
not see what you are doing in the application. In many cases, it can be
helpful to have also a screen sharing session where the user that is
watching the Monitor events can also watch what you\'re doing in the
app.

Since the user that is invited to Monitor your app session doesn\'t
actually run the app, they do not require the app to be shared with them
or any specific app permissions.

## Using Connect user

The Connect user feature allows you to select a published app that is
enabled for debug and invite a user to run the app while you use Monitor
to listen to the events it generates.

:::image type="content" source="../media/connect-user.png" alt-text="![Screenshot showing what happens when you connect a user and they play the app]":::

To enable the app, you must turn on the Debug published app setting.
After changing this setting, you must save and republish the app.

:::image type="content" source="../media/debug-published.png" alt-text="![Screenshot showing the debug published app option]":::

Since this option adds debug information to the application, it can slow
the execution and should only enabled when necessary.

To use the Connect user feature, you must launch Monitor from the app
list and not from Power App Studio.

:::image type="content" source="../media/launch-monitor.png" alt-text="![Screenshot showing launching monitor from the app list]":::

When Monitor launches from there the Connect user button will be visible
in the command bar.

:::image type="content" source="../media/connect-user-button.png" alt-text="![Screenshot showing clicking connect user from the command bar in the monitor app]":::

Similar to Invite, you provide the user information, and a link is
generated to share with the user you wish to run the app.

Unlike Invite, the user will be running the application so the app must
be shared with the user and the user must have any permissions
necessary to use the app.

When the user runs the app using the link your Monitor session will show
the events generated by the user running the app. In many cases, it can
also be helpful to have the screen sharing session so you can see what
they\'re doing in the app as you view the events in Monitor.

The collaboration features of Monitor allow you to work with others to
troubleshoot problems in apps even when you aren't located in the same
place.
