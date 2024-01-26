---
layout: default
title: Filters New <span class="new">(Updated)</span>
parent: Components
nav_order: 54
---

### Filter Checkboxes

Filter summary blocks based on assigned categories.  The summary block filter function is one of the mmore complex components available.  It is important to understand how it works.  When envoked, the function looks at two sources of information. 

1. A Google spreadsheet that contains valid categories for each grouping requested.  
2. It will look at the generated summary block blog items and pick out the assigned categories for each blog item.  
3. It will then build a list of check boxes (or radio buttons) based on the categories in blog items which match categories found in the spreadsheet.
4. Then it builds html code flex boxes to display a thumbnail, title, excerpt and categories for each item in the blog/event.     

***Cook book to create a summary block***
- Edit the page
- Click the "+" sign where you want the carousel to appear
- Select "Code"
- Copy and paste the below code block
- Change the summary collection slug value (**outreach-1**) to the slug of the blog or event collection you want to reference. 

**Code block for Filter**
```
<squarespace:query collection="outreach-1" limit="100">
  <script>
    createFilteredGallery(
      '#collectionData',
      {@|json},
      'grades,outreach');
  </script>
</squarespace:query>
<div id="collectionData"></div>
``` 
In the above example:

- **outreach-1** is the slug assigned to the outreach blog
- **#collectionData** is the selector for the div where filter and items should be placed. 
- **{@|json}** is SquareSpace notation and must be exactly like this. 
- **'grades,outreach'** parameter is a list of groups, comma separated. Must match a valid list from the categories spreadsheet. 
 - grades: will be a group of grades checkboxes, labeled "Grades".  
 - outreach: will be a group of outreach checkboxes with the label "Outreach". 

**Overrides:**

URL parameter "groups", ie. "?groups=grades,outreach"

**Usage:**

*createFilteredGallery(SelectorID, json, Filters)*

**Parameters:**

<table class="ws-table-all notranslate"> 
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Parameter</td>
     <td>Description</td>
    </tr>
    <tr>
      <td><em>Selector</em></td>
      <td>Required.<br>jQuery selector identification where the resulting html code will be generated.</td>
    </tr>
    <tr>
      <td>json</td>
      <td>The value must be "{@|json}", which is a special SquareSpace replacement parameter.  
      </td>
    </tr>
    <tr>
      <td>Filters</td>
      <td>group<:[radio|checkbox]><:[label]>
      </td>
    </tr>
  </tbody>
</table>

**Return Value:**

None

**Google Spreadsheet:**

<table class="ws-table-all notranslate"> 
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Detail</td>
     <td>Description</td>
    </tr>
    <tr>
      <td>Owner</td>
      <td>grcrane319@gmail.com</td>
    </tr>
    <tr>
      <td>File Name</td>
      <td>Categories</td>
    </tr>
    <tr>
      <td>Folder</td>
      <td><a href="https://drive.google.com/drive/folders/1qUS2VmnnptahqFDF0worIZhms3OS0TNr" target="_blank">aahom</a></td>
    </tr>
    <tr>
      <td>Link</td>
      <td><a href="https://docs.google.com/spreadsheets/d/1qrUPQu2qs8eOOi-yZwvzOuGseDFjkvj5_mSnoz0tJVc/edit#gid=0" target="_blank">Google Categories Spreadsheet</a></td>
    </tr>
    <tr>
      <td>ID</td>
      <td>1qrUPQu2qs8eOOi-yZwvzOuGseDFjkvj5_mSnoz0tJVc</td>
    </tr>
    <tr>
      <td>Sheet Name</td>
      <td>Categories</td>
    </tr>
  </tbody>
</table>

**Spreadsheet Fields**

<table class="ws-table-all notranslate"> 
  <tbody>
    <tr class="tableTop">
    <td style="width:20px">Column</td>
    <td style="width:120px">Label</td>
    <td>Description</td>
    </tr>
    <tr>
    <td>A</td>
    <td>Group</td>
    <td>The group this category is assigned to</td>
  </tr>
  <tr>
    <td>B</td>
    <td>Sequence</td>
    <td>The ordering of this category within the group</td>
  </tr>
  <tr>
    <td>C</td>
    <td>Category</td>
    <td>The category abbreviated name</td>
  </tr>
  <tr>
    <td>D</td>
    <td>Label</td>
    <td>The label, or long/full category name.  This is the name as it should appear in the blog entry category name.</td>
    </tr>
    <tr>
    <td>E</td>
    <td>Hide</td>
    <td>Hide=Yes will ignore this category</td>
    </tr>
  </tbody>
</table>

**Programer Notes**

This is the normal flow of things:

- Call ***createFilteredGallery***
  - Get data from categories spreadsheet (2 sheets)
    - Sheet *Categories* - lists groups and associated category names
    - Sheet *Groups* - lists valid group names, label and default type (checkbox/radio)
  - Call ***formatGalleryItems*** - Generate html for all items from json data
    - Call ***adjustGalleryItemHeight*** - adjust height based on image width
    - Set up window resize event with call to ***adjustGalleryItemHeight***
  - Call ***makeFilterBoxes*** - Generate flexbox html for checkboxes
    -  Call ***getSearchParams*** - for possible groups override
  - Call ***filterGalleryShowvals*** - show hide items based on checkboxes
    - Call ***intersection*** to apply add/or group/checkbox logic
  - Set up "on change" event for checkboxs to call ***filterGalleryShowvals***