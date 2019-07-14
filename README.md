# Craft Guide Templates
Open source CMS guide templates for use in the Guide plugin for Craft CMS.

Guide is made up of two parts:
- [The commercial plugin for Craft 3](https://plugins.craftcms.com/guide)
- [The open source user guide template](https://github.com/wbrowar/craft-guide-templates)

> If you are looking for templates for Guide 1, [see the `guide-1` branch of this repo](https://github.com/wbrowar/craft-guide-templates/tree/guide-1).

## Overview

The [Guide](https://plugins.craftcms.com/guide) plugin for Craft 3 is built so you can drop in a CMS Guide template and tailor it to your client’s website. Craft Guide Templates is meant to give you a starting point and to offer inspiration and examples for your company’s boilerplate Guide template.

While these template files and assets are created to support the commercial Guide plugin, they are open and free to use however you’d like. They are like the penny jar for CMS guides: if you need an idea, take one, and if you have an idea, please consider [contributing](#contributing).

## Adding Templates to Guide

These Guide templates can be added to a Craft website in one of two ways:

### Guide Importer
The simplest way is to import templates from within Guide’s General Settings page. Clicking on the "Download Templates" button will download this repository to your site’s `storage` directory, unzip it, and present you with a list of importable templates.

Clicking on which parts of a Guide template you’d like to import, then clicking on the "Import" button will move template files and assets into the right directories.

Once assets are imported, you may have to run Craft’s "Update asset indexes" command to make sure assets are added to your Guide Asset Volume.

Clicking on the "Import Guides into Organizer" option will not move any files, but it will add guides into the database. Imported guides will appear in the "Unused Guides" column of the Guide Organizer.

### Adding Templates to the Guide Template Path Directory

Adding a path into Guide’s Template Path setting will let Guide know where to look for Guide templates within your site’s `templates` directory.

To manually add templates from this repo into your site, follow these steps:

1. Download this repo and unzip it onto your server.
1. Move the template files of your choice from the unzipped directory into your Guide Template Path (`./templates/_guide` by default).
1. In Craft’s CP, visit the Guide Organizer and click the "+ New Guide" button to create a new guide.
1. Set a title and any other guide options you’d like. Select `Page Template` from the Content Source field.
1. Select a guide template for the Template field and click "Save".

## Contributing

If you have something you'd like to add to a guide template, if you find a typo you’d like to fix, or if you're a plugin developer who can help write an official how-to, please do so in the form of a [Pull Request](https://github.com/wbrowar/craft-guide-templates/pulls).

### New Guide Templates

If you would like to create a new Guide template and add it to this repo, please follow these steps:
 
1. Create a new folder in the appropriate language folder (create a new language folder if needed).
1. In that folder, create an `info.json` file and fill it out using the options in the [Info File](#info-file) section, below.
1. In `./GUIDES.json` add the path to your guide to the list of paths.
1. If your guide template requires assets, create an `assets` folder, add your assets there, and add the path to the folder into your `info.json` file. _NOTE: The path should be relative to the root of this repo._
1. Create a `templates` folder, create your `.md`, `.twig`, or `.html` files in this new folder, and add the path to the folder into your `info.json` file. _NOTE: This path should also be relative to the root of this repo._
1. In your `info.json` file, add a `guides` array and add information required for each of the templates in your guide.
1. Submit your new Guide template via pull request.

### Info File

The `info.json` file provides Guide with information necessary for importing your template files and assets.

| Property | Description | Notes |
| --- | --- | --- |
| `title` | The title as it will appear when importing the guide template into Guide. |  |
| `description` | A description of the guide template, for the guide import section. |  |
| `assetsPath` | **(optional)** The path to images and other assets used in the guide. This path is relative to the root of this repo. | _If no assets are used in your Guide template, remove `assetsPath` from your `info.json` file._ |
| `templatesPath` | The path to `.md`, `.twig`, or `.html` files used in your Guide template. This path is relative to the root of this repo. |  |
| `guides` | **(optional)** An array of guide objects that can be imported into the Guide Organizer. | See below for more information about the properties that can be used in each object. |
| `contributors` | An array of the GitHub user names of each person who has contributed to the Guide template. | |

The objects in the `guides` array can use the following properties:

| Property | Default | Description |
| --- | --- | --- |
| `access` | `"all"` | **(optional)** The intended access level for the guide. Accepts: `"all"`, `"admins"`, and `"permissions"`. |
| `contentSource` | `"template"` | **(optional)** The source of the guide which determines how the guide is rendered. Accepts: `"field"`, `"template"`, and `"iframe"`. |
| `contentUrl` | `""` | **(optional)** For guides with the `contentSource` set to `"iframe"`, a `contentUrl` is the URL embedded as an iframe. |
| `format` | `"markdown"` | **(optional)** For guides with the `contentSource` set to `"field"`, the `format` determines the language that the field content is rendered. This is optional for guides with the `contentSource` set to `"template"` since the rendering language is determined by the file extension. |
| `slug` |  | The slug of the guide that creates the URL of the guide in the Guide CP section. The slug may also be used when querying a guide from within another guide. |
| `template` | `""` | **(optional)** The filename of the `.md`, `.twig`, or `.html` file for guides with the `contentSource` set to `"template"`. Please include the file extension and avoid special characters and spaces. |
| `title` |  | The title of the guide as it will appear in the Guide CP section and other places where guides are shown. |

### Craft Plugin Developer Contributions

Twig-based guides are rendered with all of Craft’s Twig functions and filters, so specific information can safely be added to a Twig-based Guide template based on whether or not a plugin is installed onto a reader’s website.

To add information about your plugin to a Guide template, please follow these best practices:

- Use Craft’s `plugin` Twig function to encapsulate information specific to your plugin. For example, `{% if plugin('guide') %}<p>Here’s how you use Guide.</p>{% endif %}`
  - This will check to see if your plugin is installed and enabled. If not, the information will not be displayed.
- Write information in a similar tone and with similar language to the rest of the Guide template.
- Information that is more technical in nature should be included within a check to see if the user is an admin (`currentUser.admin`). This assumes that an admin is the developer of the website or a person familiar with the technical aspects of the website.
- Information can be written for users with specific permissions, by checking `currentUser.can('REPLACE_PERMISSION_KEY')`.
- If you’d like to embed your plugin’s docs as an iframe, add a new object into the Guide template’s `info.json` file’s `guides` array. This object should look something like this:

```json
{
    "contentSource": "iframe",
    "contentUrl": "https://docs.craftcms.com/v3/",
    "slug": "craft-docs",
    "title": "Craft Docs"
}
```

---

> _NOTE: All contributions may be edited or rejected if it falls outside of the scope described in the Guide template’s `info.json`, if its content is inappropriate, or if it is reported as incorrect information._