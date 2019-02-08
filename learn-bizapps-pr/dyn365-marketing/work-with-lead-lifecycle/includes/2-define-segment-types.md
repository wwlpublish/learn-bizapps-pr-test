### Types of segments in Dynamics 365 for Marketing

A market segment is the collection of contacts that you target in a marketing
campaign. You can simply create a segment to include all contacts or you
can specify a target segment based on demographic, firmographic, or
other data. For example, if you are hosting a product launch event in
Chicago, you can create a segment for those who live near the Chicago
area and invite them specifically.

In Dynamics 365 for Marketing, segments are used to target customer
journeys and you will most likely place the segment tile at the start of
the journey. Inbound journeys will be handled slightly different.

There are three types of segments:

- **Dynamic segment** - Set up by using logical expressions. Membership in dynamic segments changes constantly to reflect new or removed contacts and updated contact information.
- **Static segment** - A static list of contacts who are selected on a per-contact basis rather than created logically based on field values. Marketers and salespeople might create and populate a static list based on private knowledge or offline interactions.
- **Compound segment** - Combination of existing segments using logical operators.

Segments can also be based either on profiles or interactions:
- **Profile segments** - Query the profile records stored in the customer-interaction database. Profiles records are synced between your Dynamics 365 database and the customer-interaction database which includes the entities that you typically work with such as contacts, accounts, leads, and any other entities that you want to sync.
- **Interaction segments** - Query the interaction records stored in the customer-interaction database. Each of these records are generated automatically and related to a specific contact record. Interaction records are accessed to generate various insights displays in the Dynamics 365 Unified Interface, but they aren\'t synced to the Dynamics 365 database. They are generated in response to contact interactions such as opening an email, clicking an email link, submitting a form, or registering for an event.
