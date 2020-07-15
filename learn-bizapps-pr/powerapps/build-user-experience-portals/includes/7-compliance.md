More and more organizations uses Power Apps portals to reach out to external audiences. One of the important aspects of the global reach is ability to deliver solutions that are compliant with the relevant standards, regulations, and applicable laws. The compliance is especially important when Power Apps portals are used within the Government or financial organizations.

## Accessibility

The out-of-the-box portals (Community, Partner, Customer self-service, Employee self-service) are accessible. However, customizers must ensure that the portal remains accessible after any customization or changes.

You can retrieve specific Power Apps portals conformance reports by searching for "Dynamics 365 Customer Engagement" at [Microsoft Accessibility Conformance Reports](https://cloudblogs.microsoft.com/industry-blog/industry/government/accessibility-conformance-reports/?azure-portal=true). These reports cover the following standards:

* **EN 301 549** - the European standard that sets out accessibility requirements for information and communication technology procured by the public sector.
* **Section 508**. Under Section 508 of the Rehabilitation Act, US Government agencies must give employees with disabilities and members of the public access to information that is comparable to the access available to others.
* **WCAG**. Web Content Accessibility Guidelines published and maintained by W3C.

## Data Protection 

You can configure your portal to meet data protection standards. There are two important parts of data protection standards covered by portals:

* Identifying minor portal users and obtaining parental consent
* Agreeing to terms and conditions

### Minor portal users

Regulations for identifying minors vary by country/region. Because a minor can only access the portal with parental consent, you can configure the portal to identify minors using these fields in the portal contact record:

* **Is Minor**: Indicates that the contact is considered a minor in their jurisdiction. By default, **No** is selected.
* **Is Minor with Parental Consent**: Indicates that the contact is considered a minor in their jurisdiction and has parental consent. By default, **No** is selected.

By using additional site settings, you can configure the portal to deny minors or minors without parental consent, access to the portal. Related messages that are displayed to the users, are also configurable.

It is up to the organization to define how the information about user being a minor and/or having a parental consent, is collected. For example, registration form can be customized to include birthday and, if required, parental consent flag. You may want to further enhance the functionality by implementing workflow rules that would calculate user age at the sign-in time and set or clear **Is Minor** flag.

Special considerations must be given when using external providers such as Azure AD B2C. Only limited information is available from the providers, and providers may or may not have a mechanism for minor protection. Therefore, when someone registers using an external provider and the portal is configured to block minors or minors without parental consent, the contact record is not created and the user is not authenticated.

For details on site settings required to handle minor portal users, see [Identifying minor portal users and obtaining parental consent](https://docs.microsoft.com/powerapps/maker/portals/configure/implement-gdpr#identifying-minor-portal-users-and-obtaining-parental-consent/?azure-portal=true).

### Terms and conditions

Your organization will have policies regarding rules for using your portal. These rules are typically described in Terms and Conditions and include what portal users can do, what is prohibited and include a disclaimer to limit your liability when they access your portal. In addition, according to the GDPR, portal users must agree to the terms and conditions to allow marketing, profiling, or access to private information.

You can publish terms and conditions to get consent of the portal user before they are authenticated to the site.

Power Apps portals use content snippets to store Terms and Conditions and to support the process of getting consent from a portal user before they are authenticated to the site. Since content snippets are language-aware, it's possible to configure Terms and Conditions to be displayed in the language of the user's choice.

Contact entity includes **Portal Terms Agreement Date** indicating the date and time that the person agreed to the portal terms and conditions.

More information: [Agreeing to terms and conditions](https://docs.microsoft.com/powerapps/maker/portals/configure/implement-gdpr#agreeing-to-terms-and-conditions/?azure-portal=true).
