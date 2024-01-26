---
layout: default
title: Grids <span class="new">(06/02/22)</span>
parent: Components
nav_order: 3
---

## Grids

This will display a SquareSpace collection (blog or events) as a grid with optional
filtering based on defined groups (see reference-data).  Number of blog items
displayed depends on page width.  If width > 1200px then display 5 across, width < 1200 display 4 across, width < 900 display 3 across, width < 600 (mobile) display 1.

### Quick try

Paste the following into a SquareSpace code block to see how it works:

```
<script>
$(document).ready(function() {
  collectionControl(
    '#exampleDiv',
    'outreach-1',
    'grid'
  );
})
</script>
<div id="exampleDiv"></div>
```

**Used On Pages**

*Home*
*Learn -> Outreach*

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
      <td>This is the slug key for a defined collection blog or event.</td>
    </tr>
    <tr>
      <td><em>Display Type</em></td>
      <td>Required.<br>Identifies the display type requested.  For grids must be "grid".  These are case sensitive parameters. </td>
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
      <td>Groups</td>
      <td>This parameter only has meaning if the filter parameter is
        true.  It is a comma delimited string value of filter group names
     </td>
     <td>Null</td>
    </tr>
    <tr>
      <td>FindCats</td>
      <td>A comma delimted string value of defined
      categories to include.  If not defined then this is ignored.</td>
      <td>Null</td>
    </tr>
    <tr>
      <td>Filter</td>
      <td>Set to true if filtering is to be enabled.</td>
      <td>False</td>
    </tr>
    <tr>
      <td>ShowCats</td>
      <td>Set to true if category names are to be
        displayed along with the blog entry.</td>
      <td>False</td>
    </tr>
    <tr>
      <td>Dots</td>
      <td>Display series of dots under the carousel to show
        the current slide and positon.
      </td>
      <td>False</td>
    </tr>
    <tr>
      <td>ShowCount</td>
      <td>Display a count of blog entrieds in the carousel.</td>
      <td>False</td>
    </tr>
    <tr>
      <td>Featuredimage</td>
      <td>Display the blog entry image, true or false</td>
      <td>false</td>
    </tr>
  </tbody>
</table>

**Example code block for control**

This example displays the *outreach* blog collection as a grid.  The
grid will be displayed as 5 across (default).  Filtering will be
enabled for defined groupings of **grades** and **outreach**.  Categories
for each blog entry will be dislayed.   A count of blog entries will be displayed
as two parts ("items found" of "total items").

```<script>
$(document).ready(function() {
  collectionControl(
    '#filterOutreach',
    'outreach-1',
    'grid',
    {filter: true,
     groups: 'grades,outreach',
     showcats: true,
     showcount: true,
     dots: false}
  );
})
</script>
<div id="filterOutreach"></div>
```

**Reference Data**

- [/reference-data/categories](../reference/refcategories.html).
- [/reference-data/category-groups](../reference/refcatgroups.html).

**Return Value:**

None


**Additional Carousel Dependancies**

- Slick plugin

**Example Screenshot**

![Alt Carousel](../../assets/images/pickgrid.jpg "Carousel"){: .theImage}