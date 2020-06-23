Understanding portal metadata and where its used is important for a maker to effectively configure a Power Apps portal. While some of the portal configuration and metadata can be created and edited directly on the Portal studio or other tools, there are many portal metadata records that can only be added or modified using the Portal Management app.

The following is an overview and purpose of the portal metadata records. 

## Website

The website portal metadata section defines properties that control the behavior of the portals provisioned on the particular Common Data Service environment.

> [!div class="mx-imgBorder"]
> [![Website Metadata](../media/2-website-metadata-ssm.png)](../media/2-website-metadata-ssm.png#lightbox)

| Metadata | Purpose |
| --- | --- |
| Websites | Each provision portal will have one website record that is the main parent entity for all the websites portal metadata.  The website record will define the default header and footer templates as well as the languages.  It is not recommended to create a website and related records manually. Instead, let the system create the metadata through the provisioning or import process. |
| Page Templates | A page template is a record that will be used by a web page record to point to either a legacy aspx page on the portal host application or to a web template record. Once a page template record is created it will appear as an option on the Portal Studio when creating new web pages. |
| Redirects | A redirect record is meant to be either a temporary or a permanent detour for specific pages or sections undergoing maintenance without the need to completely shut down the portal. If a particular URL is intercepted as specified in the redirect record, it can be redirected to external URL, a web page or a site marker. |
| Site Markers | A site marker is a pointer to a specific web page record.  The site marker can be referenced in a liquid tag on a content snippet, web template or in web page content.  This allows makers to avoid having to hard code specific URLs on portal pages or content. |
| Site Settings | Site settings define specific behavior of portal functionality and features.  Site setting are value-pairs that can enable or disable particular items such as authentication settings, searching and caching. |
| Website Bindings | Website bindings are what links the particular website to the portal Azure web application.  Typically an admin would not modify this value directly in the portal management app but configure in the Portal Admin center actions. |
| Settings | Similar to settings, the settings entity contains value-pairs that are specific to all portals provisioned for the particular environment as opposed to a specific portal. |

## Content

The content section contains the entities that define what and how static and dynamic information is displayed on a Power Apps portal. While some of the content can be added using the Portal studio, certain aspects can only be added or fine-tuned by updating the data directly using the Portal Management app.

> [!div class="mx-imgBorder"]
> [![Content Metadata](../media/2-content-metadata-ssm.png)](../media/2-content-metadata-ssm.png#lightbox)

| Metadata | Purpose |
| --- | --- |
| Content Snippets | Content snippets are typically short reusable content items that can be surfaced on various parts of a portal.  An example of a content snippet would the the footer content that would be displayed on most portal web pages.  A content snippet can contain text, Liquid code, HTML and CSS.  Typically a content snippet record would be replicated for each provisioned portal language. |
| Entity Forms | Entity forms use model-driven form definitions to display forms in the portal and enable access to Common Data Service records for portal visitors. An entity form can be configured to display a read-only, edit, or create forms. |
| Entity Lists | Entity lists use model-driven view definitions to display lists of Common Data Service records. An entity list can be configured to allow a navigation to a selected record or to run workflows. A maker can also enable advanced search and filter capabilities. |
| Shortcuts | A shortcut record allows a portal maker to make a direct link on a web page to another web page, web file or even an external URL, regardless of the hierarchy or site map of the portal. Be default, the shortcut link will appear as a link on the parent web page along with the list of other child pages. |
| Web Files | A web file record provides a metadata record where a file can be attached as a note record.  The web file record will define the name and partial URL.  Web files are used for the images, CSS, JavaScript files as well as to store downloadable content. |
| Web Forms | Web forms are a component that are similar to entity forms but instead of a single record/form, web forms create a sequence of steps that can be used to build a portal based business process flow. Web forms can currently only be configured using the Portal Management app. |
| Web Link Sets | A web link set defines the web site menu that can appear in the header of a web page or as a sub-menu within a web page.  The Web Link Set record contains a collection of Web Link records that can point to a portal page or even external URLs. |
| Portal Languages | List of all languages supported by the portals out-of-the-box. Portal makers can also expand the list and add language variants like French - Canadian, to cater for international audiences. Any of these records can be associated with the web site record to enable selected language for portal visitors. |
| Web Pages | The web page record is the core of the web site.  It defines the actual displayed content, both static and via other components like entity lists and entity forms. A web page can be created and edited using the Portal studio and the Portal Management app. |
| Web Templates | The Web Template record contains the Liquid, HTML, CSS or JavaScript code that make up the layout and foundation of how a web page is rendered. When a portal is provisioned, there are a set of predefined web templates which would allow a maker to create a basic portal without needing to understand the code.  A maker can create their own web templates or modify existing web templates to satisfy specific requirements and implement custom features of their portal apps. |

## Security

The security capabilities of Power Apps portals are similar to the Common Data Service role-based security. The main concept is that a portal user is represented by a contact record and can authenticate and sign in into a portal. The portal user can be assigned to one or more web roles which can be used to control access to static portal content and Common Data Service records. This currently can only be managed  within the Portal Management app.

> [!div class="mx-imgBorder"]
> [![Security Metadata](../media/2-security-metadata-ssm.png)](../media/2-security-metadata-ssm.png#lightbox)

| Metadata | Purpose |
| --- | --- |
| Contacts | The contact entity is the actual Common Data Service or Dynamics 365 contact entity.  All authenticated portal visitors, including internal staff members, must have a corresponding contact record regardless of the authentication method. |
| Entity Permissions | Entity permissions define the scope and the privileges for specific Common Data Service records. Each entity permission record can be associated with a web role granting configured data access to portal visitors. |
| Invitations | An invitation for an existing CDS contact to join the portal can be created and sent to the contact using Power Automate flow. Once accepted, the invitation will determine their access and permissions for the portal. |
| Publishing State Transition Rules | External users can be given the ability to create and update portal content, however there may be further rules in place to allow for an approval process before the content is viewable by everyone. The publishing state transition rule records define who can either publish or unpublish content on the portal.|
| Web Page Access Control Rules | Web page access control rules link a specific web page to a web role which is linked to portal users. This controls what web pages a portal user can access. |
| Web Roles | One or many web role records can be assigned to a portal user (contact). The web role can be linked to both entity permissions and web page access control rules to control access to content and Common Data Service records.|
| Website Access Permissions | Website access permissions define what high level editing permissions specific web roles have on the portal. |

Some of the specific starter portal templates may install additional portal metadata settings for specific features of the the portal app, for example Knowledge Articles for the Customer self-service portal.

