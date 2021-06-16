Power Apps portals provides webpage access security by creating a **Web Page Access Control Rule** record for a specific webpage. To provide security to Microsoft Dataverse tables, an **Table Permission** record is created for a specific Dataverse table. Both the **Web Page Access Control Rule** record and the **Table Permission** record can be associated to a **Web Role** record, which can be associated to a Dataverse contact record. When a Dataverse contact is an authenticated portal user, the permissions and access will determine which pages and data they can view and interact with. 

This module explained the following concepts:

- The relationship between a Dataverse contact table and a portal user.
- The **Web Role** record and how it is used in portal security.
- Restricting access to webpages by using webpage access control rules.
- Restricting or providing access to Dataverse on portal webpages by using table permissions.
- Configuring a security model in a Power Apps portal.
