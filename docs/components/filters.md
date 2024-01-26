---
layout: default
title: Filters <span class="new">(Updated)</span>
parent: Components
nav_order: 53
---

### Filter Checkboxes

Filter summary blocks based on assigned categories.  The summary block filter function is one of the mmore complex components available.  It is important to understand how it works.  When envoked, the function looks at two sources of information. 

1. A Google spreadsheet that contains valid categories for each grouping requested.  
2. It will look at the generated summary block blog items and pick out the assigned categories for each blog item.  
3. It will then build a list of check boxes (or radio buttons) based on the categories in blog items which match categories found in the spreadsheet.    

***Cook book to create a summary block***
- Edit the page
- Click the "+" sign where you want the carousel to appear
- Select **Summary Block**
- Under ***content*** 
	- select the appropriate blog to display
	- Primary Metadata: None
	- Secondary Metadata: **Category**
	- Filter Items: If needed
- Under ***Design*** 
	- Select Grid
	- Number of items: 30 (max)
	- Aspect Ratio: 3:2 Standard
	- TEXT Middle, Left adjusted
	- Title: checked
	- Featured Image: checked
	- Excerpt: checked
	- Read More Link: **checked**
	- Set Read more link text: Leave alone
	- Metadata Postion: Below Content
	- Size and Spacing: 
		- Column Width: 270px
		- Gutter Width: 60px
		- Use Columns number instead: No
- Under ***Lazy Settings***
	- Ignore for now, leave off
- Under ***Additional***
	- Ignore for now, leave off

***Cook book to add Slick Carousel***
- Edit the page
- Click a "+" sign just above the summary block, in the same section 
- Select "Code"
- Paste the following code block
- Adust parameters as needed

**Code block for Summary Block Filter**
```
<script>
$(document).ready(function () {
    filterSelections('#filterContainer',
        'grades:checkbox:Grades,' +
        'outreach:checkbox:Outreach',false); 
});
</script>
<div id="filterContainer"></div>
``` 
The above example has 2 groups, comma separated, of category selections.

- grades: will be a group of grades checkboxes, labeled "Grades".  
- outreach: will be a group of outreach checkboxes with the label "Outreach". 

**Overrides:**

None

**Usage:**

*filterSelections(SelectorID, Filters, Lazy)*

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
      <td>Filters</td>
      <td>group<:[radio|checkbox]><:[label]>
      </td>
    </tr>
    <tr>
      <td>Lazy</td>
      <td>True or False selection for Lazy Settings.  If True then Lazy Settings must be enabled.  This extends the SquareSpace 30 record limit for summary blocks.  Default is false.
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
    <td>The label, or long category name</td>
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

- Call ***filterSelections***
  - if lazy then wait for lazy plugin to finish
  - Call ***showFilterSelections***
    - Get data from categories spreadsheet (1 sheet)
      - Sheet *Categories* - lists groups and associated category names
    - Navigate items in generated html 
    - Build new html for flexbox filter checkboxes
    - Biild output for items 
    - Call ***filter_showvals***
    - Call ***filter_values***
      - Set up on-change event to call ***filter_showvals***

  