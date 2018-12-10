---
description: Importing Chat and Comment data into Livefyre.
seo-description: Importing Chat and Comment data into Livefyre.
seo-title: Importing Content
solution: Experience Manager
title: Importing Content
uuid: dced31da-cc25-4e99-9ed3-4dddcaa6f566
index: y
internal: n
snippet: y
---

# Importing Content{#importing-content}

Importing Chat and Comment data into Livefyre.

On this page:

* [](#c_importing_content/section_vhm_vtt_b1b) 
* [](#c_importing_content/section_p4c_qtt_b1b) 
* [](#c_importing_content/section_ufj_jkn_b1b)

Import legacy content after your user profile data import is complete to allow Livefyre to link content to its author appropriately.

## Content Data Formatting {#section_vhm_vtt_b1b}

To begin the import process, you must prepare your import data. Livefyre’s import system expects a specific file format of line-delimited JSON Blobs, with each file representing a site on your network, and each line within the file representing an individual Collection on that site.

The Content [JSON schema](http://json-schema.org/) is described in this Livefyre [GitHub gist](https://github.com/Livefyre/import-tools/blob/master/lfvalidator/jsonschema/conv_schema.json). Validators can be found in the language of your choice from the json-schema.org > [Implementations](http://json-schema.org/implementations.html) page.

**File Format Standards**

A successful import must adhere to the following standards:

* Individual files may not contain multiple sites. Please create one file per site.
* Each line must be valid JSON, but the files do not need to be valid JSON. Do not include commas after each line.
* All Comments in a given Collection must appear in full on a single line. Do not include any literal endlines other than a single one at the end of each (Collection) Blob.
* Files must be UTF-8 formatted.
* Timestamps must be [ISO-8601 compliant](https://en.wikipedia.org/wiki/ISO_8601).
* URLs must be fully qualified. They must include http:// or https:// and domains must include the trailing /. For example:

    * https://web.livefyre.com/ or http://web.livefyre.com/index.html

* The top level id field must be unique to the content. (This id is often the CMS’s unique ID, but may also be the content’s URL, post number, or other identifying string. If using the content URL as the unique identifier, it is a best practice to MD5 or otherwise hash the identifier to meet field length restrictions.)
* To streamline the import process, do not import Collections that do not yet include comments. After implementation, Livefyre will automatically create a Collection with 0 comments the first time your App is loaded on the page.
* If not importing User Profiles, omit the author_id field from the Blob (unless you are preparing files for Livefyre’s archive import).

**HTML Standards**

* **Allowed HTML tags and attributes in comment bodies:**

    * Tags: a, span, label, p, br, strong, em, u, blockquote, ul, li, ol, pre, body, b, i
    * Attributes: href, target

  **Line breaks:** Line breaks in comments must be represented as <p></p> and <br> tags. n will not be accepted. Wrapping the entire comment in surrounding <p></p> tags is not required.

* **Do not use HTML entities in Collection Titles:** HTML entities like <b>, <i>, <strong>, and <em> must be removed from the Collection title. If included, they will be represented literally in the displayed Collection title in Studio.
* **Do not encode angle brackets in HTML tags: **The left and right angle bracket characters ( < > ) of HTML tags in body_html should not be encoded. If encoded, these tags will have no meaning and will be displayed literally in Studio.
* **Escape quotations in tags: **Quotation marks in HTML tags must be backslash escaped.

  For example: <a href=”http://www.baseart.fr/doc/sacguccifrance.php”>gucci jeans<a>

* **Do not add extra attributes from anchor tags: **Additional attributes like rel=”nofollow” and rel=”bookmark” are not permitted. The additional invalid attributes will be stripped out during the import, and the anchor tag will be imported without them.

**Threaded Content**

To maintain threading in your imported content, adhere to the following rules:

* **Comment ordering: **To preserve comment threading, parent content must be imported before child/reply content. Specifically, the top level ID of a comment must exist before a child comment references it as parent. An easy way to accomplish this is to list comments from oldest to newest date of creation.

  **Note: **Livefyre doesn’t keep a record of parent IDs after running a sample import. Parent IDs must be included in the delta file.

* **Threading with moderated comments: **To maintain threading in your reply structures, set the parent_id for every reply comment.
* **Deleted or Moderated comments: **There are two options for comments that have been deleted or moderated and have child replies:

    * **Import all comments: **Import all comments and replace the text of deleted or moderated comments with a standardized message.

      For example, if your original content structure follows this format:

      - A

      — B (deleted/moderated)

      — C

      —- DStructure the import file to replace the deleted content with a message:

      - A

      — B (replace body_html text. For example: “This comment has been deleted or moderated.”)

      — C

      —- D
    
    * **Import approved comments only: **Include only approved (non-moderated) comments and comments from users that have not been banned in the import. To preserve threading, replies to removed comments must specify the parent of the removed comment’s ID as the parent_id.

      For example, if content follows this format:

      - A

      — B (deleted/moderated)

      — C

      —- D Structure your import file to set the top level comment as the parent to the removed content’s child:

      - A

      — C (set parent_id to ID of A)

      — D

**Special Characters**

* **Encode non-ASCII special characters: **All non-ASCII special characters must be encoded, preferably with Python style encoding. For example, replace smartquotes (also known as typographer’s quotes ’ ) with u2019. (Do not escape the backslash; Livefyre requires the single backslash.)

## Available Content Parameters {#section_p4c_qtt_b1b}

The following parameters are used in the Content import process.

**Required**

* ** source: ** **(required) string **The site on which the comment originated.

* ** title: ** **(required) string **The title for the Collection to which the comment was posted.

* ** created: ** **(required) timestamp **The ISO-8601 compliant timestamp for the moment the Collection in which the comment was posted was created. For example: “2010-07-05T23:01:15Z”

* ** id (source): ** **(required) string **The article ID you chose to uniquely identify a Collection within your Site, encoded using Base64. This parameter is limited to 150 characters.

* ** id (comments): ** **(required) string **Your system’s internal content identifier, used by the importer to relate children using their `parent_id`.

* ** imported_display_name: ** **(required) string **The name to display next to content. (Unicode characters may be used.)

* ** author_id: ** **(required) string **The unique ID of the content’s author. (Unicode characters cannot be used for this parameter.)

* ** body_html: ** **(required) string **The text string for the Comment. Only <p> and <a> tags, and the href attribute are allowed.

* ** created: ** **(required) timestamp **The ISO-8601 compliant timestamp for the Comment’s creation. For example: “2010-07-05T23:01:15Z”

**Optional fields**

* ** imported_email: ** **(optional) string **Used for gravatars, and not displayed publicly.

* ** imported_url: ** **(optional) string **A user provided website.

* ** parent_id: ** **(optional) string **Provide the parent ID for the comment to which this comment is a reply. Parent comments must appear before their children.

* ** likes: ** **(optional) array **An array of user IDs of users who have ‘liked’ the comment.

* ** tags: ** **(optional) array **Use tags to assign users to user groups. Tags may include 1-63 alphanumeric and underscore characters.

* ** allow_comments: ** **(optional) Boolean **Set to `false` if you do not wish to allow new comments on the conversation. May be `true` or `false`.

## Example Comment Format {#section_ufj_jkn_b1b}

>[!NOTE]
>
>`parent_id` and `id` must be strings in your import file.

```
{ 
   "source": "http://www.somepartner.com/homepage/check-out-this-sneezing-panda.html", 
   "title": "Check out this sneezing panda!", 
   "created": "2010-07-05T23:07:15Z", 
   "id": "3042469", 
  
   "comments": [ 
      { 
         "id": "99770519", 
         "imported_display_name": "chris", 
         "author_id": "99999", 
         "body_html": "<p>OMG I love how cute the video is!</p>", 
         "created": "2010-07-05T23:01:15Z" 
      }, 
      { 
         "id": "99770520", 
         "body_html": "<p>OMG I love how cute the video is!</p>", 
         "created": "2010-07-05T23:01:15Z", 
         "author_id": "999999", 
         "imported_display_name": "chris", 
         "imported_email": "chris@livefyre.com", 
         "imported_url": "http://livefyre.com", 
         "parent_id": "99770519", 
         "likes": ["999998", "999990"] 
      } 
   ], 
  
   "tags": ["blog_post","news","sports"], 
   "allow_comments": true 
}
```
