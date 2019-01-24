On the **Business Management settings** menu, you can:

- Import data
- Export data
- Manage duplicate detection

### Import data

You can quickly bring your customer and sales data into your app by importing it. You can import data into most record types. Data can be imported from most list views. To do this, go to **Settings** \> **Advanced settings** \> **Business management** \> **Import data**.

To learn more, see [Import data](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/import-data).

### Export data

You can share information with people who don\'t have access to Dynamics 365 by exporting the data to an Excel workbook. You can export just the data from a list or you can export a template. Data can be exported from most list views. To do this, go to **Settings** \> **Advanced settings** \> **Business management** \> **Export data**.

To learn more, see [Export data](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/export-data-word-excel).

### Duplicate detection

Dynamics 365 includes duplicate detection rules for accounts and contacts. The rules are automatically published when duplicate detection is enabled.

- Accounts with the same account name are found.
- Contacts with the same first name and last name are found.
- Contacts with the same email address are found.

If any of these rules are deleted, duplicate detection won\'t work as expected.

### Enable duplicate detection

To enable duplicate detection:
1.  Go to **Settings** \> **Advanced Settings** \> **Business Management** \> **Duplicate Detection**.
2.  Select **Enable**.

If duplicate detection is enabled, duplicates are detected when:
- **A record is created or updated** - The system checks for duplicates when a user enters or updates records.
- **During data import** - When you use the Import Data wizard to bring in contacts or accounts, the wizard detects any duplicate records.

### Disable duplicate detection

Checking for duplicates can affect performance if your system contains a large number of records so you may want to disable duplicate detection if that is the case.

To disable duplicate detection:
1.  Go to **Settings** \> **Advanced Settings** \> **Business Management** \> **Duplicate Detection**.
2.  Select **Disable**.

All the duplicate detection rules will be unpublished on the back end.
