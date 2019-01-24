A marketing form is an input form added to a marketing page. Marketing forms enable visitors to register for an event, manage their mailing-list subscriptions, forward a marketing message, or submit information to interact with marketing initiatives. All the information submitted through a marketing page is automatically captured by Dynamics 365 and immediately applied to your customer database.

Dynamics 365 for Marketing comes with a collection of sample form templates. You can also create your own templates. Each marketing form is made from a collection of form fields, buttons, graphical elements, and a few configuration settings. Each field included in your form must be set up in Dynamics 365 as a marketing form field, which establishes options for how the field is presented in forms, where it appears, and which lead or contact field it maps to. Field types include elements such as single line of text, option sets, radio buttons, whole number, date and time.

There are 3 types of marketing forms:

-  **Landing Page form** Primary focus is collecting contact information on a specific marketing page which does not include subscription centers nor forwarding forms. Landing page forms must match the marketing page type.
-  **Subscription form** Provides details of stored data for contacts to view and update their personal information. A subscription form only modifies existing contacts and never creates new ones.
-  **Forward to a Friend** Provides fields, each accepting an email address entered by an existing contact.

### Form requirements and limitations

Design element availability and requirements vary by form type, as outlined in the following table. Be sure to include all the required elements for the type of form you are designing.

  |**Design element type**           | **Landing page**  | **Subscription center**  | **Forward to a friend**  |
  |----------------------------------| ------------------| -------------------------| -------------------------|
  |Text, Image, Divider, and Button  | Yes               | Yes                      | Yes                      |
  |Field                             | Yes               | Yes                      | No                       |
  |Subscription List                 | Yes               | Yes                      | No                       |
  |Forward to a friend               | No                | No                       | **Required**             |
  |Do not bulk email                 | Yes               | **Required**             | No                       |
  |Remember me                       | Yes               | Yes                      | No                       |
  |Submit button                     | **Required**      | **Required**             | **Required**             |
  |Reset button                      | Yes               | No                       | Yes                      |
  |Captcha                           | Yes               | No                       | No                       |
