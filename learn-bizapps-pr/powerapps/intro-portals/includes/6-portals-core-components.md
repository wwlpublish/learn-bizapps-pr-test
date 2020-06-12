# Power Apps portals core components

Power Apps portals store all information in the Common Data Service. The portal entities define the site structure, layout, content, and functionality.

Two most common questions asked about any portal are:

* How do I manage the portal content?
* How do I surface and interact with the business data in the portal?

Power Apps portals have a number of core components that enable these scenarios. 

## Web pages

Most of the content of a portal is represented by the web pages. A web page represents a particular URL in a portals website, and is one of the core entities of the portals content management system. Through parent and child relationships to other web pages, this entity forms the hierarchy of a website, i.e. its site map.

Web pages also form the basis for including other, specialized entity types in the portal site map: web files, shortcuts, forums, ideas, and blogs. Each of these records have a relationship with a parent page. That defines the URL and where the entries are located on the portal site map. 

![Site page hierarchy](../media/3-page-hierarchy.png)

Pages can be added and edited using the Portal studio, the portal front-side editor, or directly in the Common Data Service using the Portal Management app.

| Portal Studio                               | Portal management app                                        |
| :------------------------------------------ | :----------------------------------------------------------- |
| 1. Select the portal app and press **Edit** | 1. Open Portal management app                                |
| 2. Press **New Page** on the Command bar    | 2. Go to **Portal > Web Pages**                              |
| 3. Choose a layout                          | 3. Select **New**                                            |
| 4. Enter details on the properties pane     | 4. Enter the page details                                    |
| 5. Page will be automatically saved.        | 5. Select **Save**                                           |
|                                             | **Security:** user must be a **licensed Power Apps user** with the appropriate Common Data Service security privileges. |

> [!VIDEO "../media/create-web-page.mp4"]

<video src="../media/create-web-page.mp4"></video>

Each web page is composed of at least two portal metadata records.  A *root* web page record which contains the main attributes of the web page record and a *content* web page record that holds the language specific content of the web page.  There is one *content* web page for each provision portal language.

## Page templates

Web page record itself does not define how the page looks when rendered on the portal. Instead, it's linked to the **Page template** record that defines the layout and the behavior.

There are two types of the templates that can be used in Power Apps portals.

* **Rewrite**. These templates use specialized server-side processing to specific behavior required by some of the components such as polls, forums, etc. They are also used to handle special pages such as an error page, sitemap, search, and others.  You cannot create new or edit existing Rewrite templates.
* **Web Template**. The linked layout template defines how the content of the page is rendered for output. These templates can be edited as required.

### Web template 

Web templates use the liquid templating language to define how the content is processed and rendered. Templates are very flexible. A template can re-use other templates for parts of the content. A template can also be based on another template, extending the base functionality. 

Web templates can be used to define an entire web page, a part of a page, or common elements such as the site header and footer. This approach creates consistent look and feel throughout the portal and makes it easy to modify the appearance.

Existing Web templates can be edited in the portals studio.

## Web files

Web files provide access to inline or downloadable content. They are very similar to the web pages and have very similar properties except that web files do not use templates. Instead, when the file is requested, the attached content is delivered.

The content can be stored as a **Note** with attachment or in Azure Blob Storage. Using Azure storage requires additional configuration but is more cost efficient if organization deals with a large number of documents.

Web files are used to deliver content like documents, for example, an annual report. They are also used to store essential site content like CSS (Cascading Style Sheet) and JavaScript files.

Images displayed on portal web pages can also be stored as web files.

## Content snippets

Content snippets are reusable fragments of editable content that can be placed within a web template. Using snippets creates consistent look and feel for the site, makes it easy to translate the multi-lingual context, and allows targeted edited of the parts of a page without affecting the overall content.

Content snippets can include plain text, HTML layout, or even template processing instructions, enabling dynamic content. 

![Content snippets on a page](../media/1-6-content-snippet.png)

![Content snippets metadata in portal management app](../media/1-6.contentsnippetmetadata.png)

## Entity lists and entity forms

The strength of Power Apps portals is the ability to to interact information and data stored in the Common Data Service.

![Entity List](../media/1-6.EntityListStudio.png)

**Entity lists** and **entity forms** use model-driven Power Apps views and forms definitions to create dynamic and interactive portal pages working with the Common Data Service. 

Web page record can be linked to an entity list or an entity form. The linked list or form will be used by the template to render the page layout using data from the Common Data Service based on system or custom entities. The template may use list and form definitions to include interactivity, e.g. read-write access to Common Data Service records.

### Entity lists

Entity lists define how the list of Common Data Service records is displayed on the portal pages. They are defined by one or more model-driven Power Apps views and include functionality like filtering and sorting.

Entity lists can also have actions associated with them to enable Create/Edit/Read abilities and to trigger workflows. Display formats include traditional grid lists, calendar or map and spreadsheet download.

### Entity forms

Entity forms add ability for the portal pages to interact with the records in a specific entity using a model-driven Power Apps form definition as a layout template.

Form mode can be read-only, insert, or edit. This defines if the form is used to generate a layout, capture the data, or provide full editing capabilities using the Common Data Service entity record. Some of the examples include:

* Informational pages about employees, products, or any other Common Data Service entity.
* Data capture from either anonymous or authenticated users, for example using "contact us" page to record leads in Dynamics 365 Sales, or survey page to collect product feedback from the customers. 
* Support pages providing read-write access to the customer's cases. 
* Profile self-management for the customers.
* Alternative user interface for the employees that provides required functionality but without the need to deploy canvas based Power Apps.
* Any other scenario where data from the Common Data Service needs to accessed, displayed, captured and processed using the portal.