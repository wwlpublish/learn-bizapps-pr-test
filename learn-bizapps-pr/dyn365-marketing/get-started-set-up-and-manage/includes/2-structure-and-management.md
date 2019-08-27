Dynamics 365 for Marketing can only be used on instances running Dynamics 365 Customer Engagement apps version 9.0 or higher. If you have a paid Dynamics 365 instance, you can integrate Marketing by adding the Marketing app to your tenant. Dynamics 365 for Marketing is licensed per instance, with each instance priced according to the number of marketing contacts that you market to. To learn more, see 

- [How Marketing is licensed](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-marketing#how--is-licensed)
- [Adding a Marketing app to your Office 365 tenant](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-marketing#add-a--app-to-your--tenant)
- [Setting up an unconfigured Marketing app](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-marketing#set-up-an-unconfigured--app)

### Prerequisites and setup

Dynamics 365 for Marketing uses several other Dynamics 365 components, Microsoft services, and apps as mentioned earlier. There are several [prerequisites and requirements](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-setup#prerequisites-and-requirements)
along with multiple steps you must follow to ensure a valid setup of your Marketing app such as [choosing an organization](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-setup#step-1-choose-an-organization-and-name-your-portal),
[acceptances of consents to license agreements and privacy statements](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-setup#step-2-give-consent-and-enter-your-postal-address)
and [allowing marketing services to process your data from Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-setup#privacy-notice).

The setup wizard will help you review all the relevant privacy policies and set up and integrate these various elements. To learn more about using the setup wizard, see  [Purchase a production version of Dynamics 365 for Marketing](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-marketing).

You should familiarize yourself with the [Microsoft Dynamics 365 Licensing Guide terms and limits](https://go.microsoft.com/fwlink/p/?linkid=874224) of the product before you begin to use it. Your system has certain limits and quotas that apply to the number of contacts that you can market to, monthly email messages that you can send, and monthly Litmus previews that you can view.

### Manage marketing instances

Dynamics 365 for Marketing adds significant complexity to Dynamics 365. It is composed of several components that you should be aware of in order to understand how the instance-management operations work when Marketing is installed. Dynamics 365 for Marketing and Customer Insights services are external to the Dynamics 365 platform server, and thus follow their own lifecycle. These services aren't directly accessible to users, so when backup and restore operations are used on the organization database, you must consider their impact on these connected services.

General instructions for how to manage Dynamics 365 instances are available in [Manage instances](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-online-instances) and its subtopics.

Each time that you set up a new Marketing instance, including restoring a backup to a new instance and copying a production instance to a sandbox instance, you must re-run the Marketing [setup wizard](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/purchase-setup) on the new instance. This is because the new instance needs to be set up with a new collection of external services. Automatic daily backups don't pause any of your live entities. This helps to ensure that your customer journeys and other live features aren't interrupted by these backups, which are primarily made for purposes of disaster recovery.

### Keep marketing up to date

Microsoft is continuously developing and improving online services. Although updates are rolled out as soon as they're ready, they are not automatically applied to customers' systems because most customers prefer to manage this process themselves. In many cases, customers want to apply and test updates on a sandbox instance before applying them to their production system.

Marketing also includes two solutions, Dynamics 365 Portals – Base Portal and Voice of the Customer for Dynamics 365, that must be updated separately using the **Instances** tab as described in [Find and apply updates for shared Marketing solutions](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/apply-updates#update-shared). Be sure that you do not update any of the core Marketing solutions while you are updating these shared solutions, even if they show an update is available. Always run the Marketing update wizard first, before you run shared-solution updates.  
