Images, graphics, and videos are important elements that enhance your marketing emails and marketing pages. In order to use these elements in your designs, you must first upload them to Dynamics 365, which also hosts the images and delivers them when contacts open an email or marketing page.

### Upload images

When you add an image element to a marketing page or email, you can choose to add an image that already exists in your Dynamics 365 database or upload a new one. After you've uploaded a file, the file will be available for use in other designs. You can also upload images directly to the file library to be used in future marketing activities.

For security purposes, you are only allowed to upload image files. The following formats are supported: GIF, BMP, JPEG, and PNG.

Go to **Marketing** \> **Marketing content** \> **Files**.
 
Select **+ New** to upload a new file.

You can apply keywords each time that you upload a file. After the file is uploaded, a lookup field will appear under the name of the file. Use the search feature or the magnifying glass to find keywords that have already been set up in the site. You can also create new keywords by clicking the + New icon.

![Upload images](../media/gsm-managemarketingcontent-1.png)

### Manage keywords

Keywords make it easier to find your images later when you want to use them in content. Each time that you upload a new image, you're offered a chance to apply a keyword to it. You can also add or remove keywords
from existing images by going to **Marketing** \> **Marketing content** \> **Files**.

To help manage your keywords, Dynamics 365 requires you to establish a list of specific keywords that users can apply to their files. Users must therefore select keywords from a list rather than enter free text. This helps prevent users from applying competing ontologies and helps prevent typos.

To view and edit the keywords available to your organization, go to **Marketing** \> **Marketing content** \> **Keywords**. All existing keywords are listed here. Select any listed keyword to edit it or select **New** to create a new one. You can also delete keywords.

> [!IMPORTANT] 
> Be careful when editing or deleting keywords. If you edit an existing keyword, all existing files that use it will instead show the new
value from now on. If you delete a keyword, it is simply removed from all files that use it.

### Create reusable content blocks

Content blocks let you establish common content that you can reuse in multiple emails, forms, and/or pages such as headers, footers, and other blocks of content to standardize your communications.

Content blocks work like templates. Once added, the content is copied into your design and doesn\'t maintain any connection to the original block content, which means that if you edit a content block in a design, other designs that use that block won\'t be affected.

You can lock the content of a content block to prevent it from being changed in any design where it is used. This will help improve control over common content and/or design choices.

> [!IMPORTANT] 
> Even if you choose to lock a content block, users who have access to the designer's **HTML** tab will still be able to edit it by
> modifying the code directly. To prevent this, administrators can use designer feature protection to limit access to the **HTML** tab by some or all
> users. For more information, review the next section on how to control access to designer features.

### Control access to designer features

Designer feature protection lets you control which users have access to which features of the content designers (email, marketing page, marketing form, and content-block designers). You can use these settings to block access by any user or group to one or both of the following
designer features:

- **Designer HTML tab** - Users with access to the **HTML** tab can work with all aspects of the HTML code that goes into your designs. By blocking access to this tab, you'll make sure that design elements that you mark as locked in the HTML code (and all content outside of design elements) won't be editable by certain (or most) users. Content-block elements provide an easy setting that enables you to lock or unlock them, but you can also lock any design element by adding the data-protected=\"true\" HTML attribute to its opening \<div\> tag.

- **Litmus inbox previews**: The email designer's inbox preview feature provides pixel-perfect previews that show exactly what your design will look like when rendered in nearly any specific client/browser/platform combination. This feature is provided by a company called Litmus and requires that users purchase an extra license if your organization uses more than a certain number of previews each month (see your Dynamics 365 license agreement for details). You may choose to limit access to this feature to help manage costs and/or to have better control over who gets to use your organization's free monthly previews.

To control access to designer features:

1. Go to **Settings** \> **Designer feature access.** This opens a list of currently defined protection rules, each of which shows which user or group is being denied access to which features. Each row sets a rule for exactly one user or one group.

2. Choose an existing configuration to edit or delete, or choose **+ New** from the command bar to create a new one.

3. If you choose to edit or create, a form opens where you can edit the following settings:
    - **Team** - To apply protection to all members of a team, choose a team name from this lookup field. Each rule can apply only to one team or one user.
    - **User** - To apply protection to a specific user, choose a user name from this lookup field. Each rule can apply only to one team or one user.
    - **Blocked features** - Choose which features you want to hide from the specified user or team: HTML, Litmus, or both.

4.  When finished, click **Save & Close**.

![manage marketing content](../media/gsm-managemarketingcontent-2.png)

### Preview: Create a video library to add videos to your designs

Use Dynamics 365 for Marketing to store information about each of the videos that you use in your marketing initiatives and then include those videos in your emails and pages by adding a video design element that references a video from your video library. The library won't contain the video itself, just references to it, so you'll need to host your video somewhere else, such as on one of the major video platforms such as YouTube or Vimeo.

When you add a video to one of your designs, the designer will automatically use the settings it needs for the type of design that you are creating. For pages, the designer will embed the video, so visitors can play it without leaving the page. Most email clients don't support embedded videos, so for emails the designer will embed the thumbnail image and link it to the video URL so contacts can select the thumbnail to open the video in a new browser tab.

This is currently a **preview feature**. Please read the following note about preview features.

> [!IMPORTANT] 
> A preview feature is a feature that is not complete but is made available before it's officially in a release, so customers can get
early access and provide feedback. Preview features aren't meant for production use and may have limited or restricted functionality.

Microsoft doesn't provide support for this preview feature. Microsoft Dynamics 365 Technical Support won't be able to help you with issues or questions. Preview features aren't meant for production use and are
subject to a separate supplemental term of use.

To add a video to your library in Dynamics 365 for Marketing:

1. Go to **Marketing** \> **Marketing content** \> **Videos**
2. Choose an existing configuration to edit or delete, or choose **+ New** from the command bar to create a new one
3. If you choose to edit or create, a form opens where you can edit the following settings:
     - **Name** - Assign a name to the video that will make it easy for you and other users to recognize.
     - **Owner** - This is the user who owns this video record, which can sometimes affect who can view and/or edit it. It defaults to the user who creates the record.
     - **Video URL** - Specify the URL that will open the video in a browser. This link will be used to link to the video from its thumbnail image when you use it in an email message.
     - **Video thumbnail URL** - Specify the URL of a still image that represents the video. This image will be embedded and linked to the video URL when you place the video in an email design. Most video hosting platforms make this URL available publicly. You could also create your own thumbnails and host them in your Dynamics 365 files library or elsewhere if you prefer.
     - **Video embed URL** - Specify the code required to embed the image on a web page. This code will be used when you place the video on a marketing page, so visitors can watch without leaving the page. Most video hosting platforms will provide this code for you.
4. When finished, click **Save & Close**.

![Video marketing content](../media/gsm-managemarketingcontent-3.png)
