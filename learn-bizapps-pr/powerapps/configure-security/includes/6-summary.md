Power App portals provide web page access security by creating a **web page access control rule** record for a specific web page.  To provide security to Common Data Service entities, an **entity permission** record is created for a specific CDS entity.  Both the **web page access control rule** and the **entity permission** records can be associated to a **web role** record which can be associated to a CDS contact record.  When a CDS contact is an authenticated portal user, the permissions and access will determine what pages and data they can view and interact with. 

Let's have a quick look at what we have covered in this module:

* We reviewed the relationship between the Common Data Service **contact** entity and a portal user
* We learned about the **web role** record and how it is used in portal security
* We learned how to restrict access to web pages using **web page access control rules**
* We learned how to restrict or provide access to the Common Data Service on portal web pages using **entity permissions**
* We reviewed how to configure a security model in a Power Apps portal
