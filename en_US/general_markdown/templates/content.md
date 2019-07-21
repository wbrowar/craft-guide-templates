## Entries

<img src='[GUIDE_VOLUME_PATH]/content-section-types.png' alt='Guide content section types'>

Craft stores your website&rsquo;s content in the <a href="/admin/entries">Entries</a> section of Craft’s Control Panel. There are three types of sections that your entries can be stored as:

|  |  |
| --- | --- |
| Singles | One-off pages that have a specific purpose, require a specific URL, and often are displayed in their own unique page template. Singles can only be created by an Admin or a developer, but they can be edited by content editors. |
| Channels | Channels are used to create multiple entries that are grouped together by content type. |
| Structures | Structures can be used to create multiple entries that can be manually organized within a hierarchy. |

---

## Creating New Entries

<grid grid-type="text-sidebar">
  <div>
    <p>Channel and Structure entries can be created from the Entries page by clicking on the "+&nbsp;New Entry" button in the top-right. If you&rsquo;re already within a Channel or Structure section, a new entry of that section type will be created. Alternatively, you may use the downward caret to the right of the "+&nbsp;New Entry" button to select the type of entry you will be creating.</p>
    <p>By selecting the new entry&rsquo;s section, you&rsquo;ll be taken to the Create Entry page.</p>
  </div>
  <div>
    <img data-lazy-load data-src='[GUIDE_VOLUME_PATH]/content-new.png' alt='Guide content new'>
  </div>
</grid>


### Populating Fields

<grid grid-type="2-column">
  <div>
    <p>There are several different field types within Craft. Some fields are used for content entry, whereas others may be used to determine the layout of the page.</p>
    <p>If a field is required for a particular entry type, you must enter something into the field before you may publish the entry. If a required field is not filled out during publishing, it will be highlighted in red and an error message will indicate what is missing.</p>
  </div>
  <div>
    <img data-lazy-load data-src='[GUIDE_VOLUME_PATH]/content-fields.png' alt='Guide content fields'>
  </div>
</grid>


### Live Preview

To get an idea as to how a page is starting to look as you begin to enter content into it, you may use the Live Preview feature in Craft. Live Preview updates as you type, helping you make layout and design decisions as your content is being created.

Some entry types may appear in multiple places within your website. For example, a News article may live on its own page, on a news collection page, and in a "Related Article" secton on other pages. To view how an entry is displayed on multiple pages, use the dropdown found above the preview area to switch Live Preview’s preview URL to the other locations.

To exit Live Preview, use the "Close Live Preview" button in the top-left.

---

## Content Blocks

Some entry types allow for your content to be built in a modular fashion. Content blocks allow for multiple blocks of similar components&mdash;that can be mixed and matched&mdash;so you can create unique layouts for the type of content you are presenting to your audience.


### Matrix Fields

<grid grid-type="text-sidebar">
  <div>
    <img data-lazy-load data-src='[GUIDE_VOLUME_PATH]/content-matrix.png' alt='Guide content matrix'>
  </div>
  <div>
    <p>To create content within a matrix field, start by selecting the type of content block you would like to create. A new content block will appear and you will be presented with a set of fields that are specific to that block type. In this block there may be fields that are required for the block to be displayed properly.</p>
    <p>If you need to re-order a series of matrix blocks use the move icon (✜) in the top-right of the block to drag your content blocks up and down.</p>
  </div>
</grid>


Clicking on the gear in the top-right will allow you to perform bulk actions:

|  |  |
| --- | --- |
| Collapse | Get large content blocks out of the way by collapsing them down. The content in these blocks will still appear on the page, and collapsing them only affect the how your content blocks look on the edit page. _NOTE: you can quickly collapse a content block by double-clicking the header of the matrix block._ |
| Disable | Disabling a matrix block is useful in that if you don&rsquo;t want to delete a block of content but you would like to remove it from the page, disabling a block prevents the content from appearing on the page&mdash;while making it easy to bring back later. |
| Delete | Removed the content block and all of the content within it. |

Bulk actions can be applied to multiple content blocks at once by checking the box in the top-left corner of each content block before selecting the desired action.

---

## Drafts and Revisions

Drafts are versions of your content that are unpublished and can be shared with others while the current version of your content exists on your site. To start a new draft, click on the "Save as a Draft" button.

Craft will automatically save new drafts as you make changes to the fields on a piece of content. You’ll see the revisions drop down change and a green check mark will appear next to it letting you know that a new draft has been saved.

When you are satisfied with the current draft, clicking "Update entry" will publish the new draft and save it as the "Current" version.

Content can be rolled backwards between old drafts and revisions by selecting a previous revision from the revisions drop down and clicking the "Revert entry to this revision" button.

---

## Publishing

An entry is published when the "Enabled" switch in the edit page sidebar is turned on. Depending on the section type, this sidebar can contain more publishing options.

In Channel entries, you will find the following options:

|  |  |
| --- | --- |
| Slug | The slug helps determine the URL of the entry. Each slug is unique and will be generated from the entry Title field, however you may manually change the slug if needed. |
| Author | The entry author affects the permissions for who may edit and publish the entry. The author is pulled from users within Craft. |
| Post Date | The Post Date of the entry helps when listing content in chronological order. Content can be scheduled for publishing by selecting a future date and time for the Post Date. |
| Expiry Date | You can schedule content to become unpublished by setting an Expiry Date. |
| Notes about your changes | All content types allow you to write a note about what had been changed in an update. This is useful for communicating to multiple team members who may work together to create and edit content. |