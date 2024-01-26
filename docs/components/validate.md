---
layout: default
title: Validate  <span class="new">(05/03/22)</span>
parent: Components
nav_order: 50
---

### Validate

Given a list of collections, this routine will examine each blog
entry in the list of collections and report any categories 
that do not have a match in the official list of categories. 

**Used On Pages**

*About Us -> Invalid Categories*

**Usage**

*collectionControl(Selector, Collection Slug, Display Type, Attributes)*

**Parameters:**

<table class="ws-table-all notranslate">
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Parameter</td>
     <td>Description</td>
    </tr>
    <tr>
      <td><em>Selector</em></td>
      <td>Required.<br>jQuery selector identification where the resulting html code will be generated.  Note that the selector must be unique on the page.</td>
    </tr>
    <tr>
      <td><em>Collection Slug</em></td>
      <td>Not used</td>
    </tr>
    <tr>
      <td><em>Display Type</em></td>
      <td>Required.<br>Identifies the display type requested.  For collection validation must be "validate".  These are case sensitive parameters. </td>
    </tr>
    <tr>
      <td><em>Attributes</em></td>
      <td>Optional.<br>Identifies parameters to override default values.  The parameters are passed in a object array of key/value pairs.  Each display type has different default values as described below. </td>
    </tr>
  </tbody>
</table>

**Attributes:**

All attributes are optional, the defaults are defined.

<table class="ws-table-all notranslate">
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Attribute</td>
     <td>Description</td>
     <td>Default</td>
    </tr>
    <tr>
      <td>collections</td>
      <td><strong>Required.</strong> This parameter is a javascript array of the collections to be included in the validation.
     </td>
     <td>Null</td>
    </tr>
  </tbody>
</table>

**Example code block for control**

This example displays invalid categories found in the blog entries for all of the listed collections.

**NOTE:**, The list of collections must be a valid javascript
array of collections slug names.

```
<script>
$(document).ready(function() {
  collectionControl(
    "#validateCategories",
    "",
    "validate",
    {collections: [
        "announcements",
        "distance-learning-1",
        "outreach-1",
        "field-trip-options",
        "site-features",
        "public-education",
        "promotions",
        "jobs-list",
        "team-members",
        "flex-boxes",
        "giving-opportunities",
        "reference-data"
        ]
    }
  );
})
</script>
<div id="validateCategories"></div>
```

**Reference Data**

*reference-data blog: categories*

**Return Value:**

None

