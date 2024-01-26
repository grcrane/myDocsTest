---
layout: default
title: Carousel  <span class="new">(06/02/22)</span>
parent: Components
nav_order: 2
---

## Carousel

The Carousel is an infinint loop of entries in a collection with previous and next
buttons on the left and right.  The number of items displayed can be defined as an
attribute when calling the carousel function.  Filtering (to limit items) based on SquareSpace categories is also available via attributes.

### Quick try

Paste the following into a SquareSpace code block to see how it works:

```
<script>
$(document).ready(function() {
  collectionControl(
    '#exampleDiv',
    'announcements',
    'carousel'
   );
})
</script>
<div id="exampleDiv"></div>
```

**Used On Pages**

*Home*
*Visit -> Ann Arbor Hands-On Museum*

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
      <td>Required.<br>Identifies the display type requested.  For carousels must be "carousel".  These are case sensitive parameters. </td>
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
      <td>ShowSlides</td>
      <td>Number of slides to show in the carousel</td>
      <td>3</td>
    </tr>
  </tbody>
</table>

**Example code block for control**

This example displays the *announcements* blog collection as a carousel.  The
carousel will be displayed as two items.

```
<script>
$(document).ready(function() {
  collectionControl(
    '#announce',
    'announcements',
    'carousel',
    {groups: "",
     findcats: "",
     filter: false,
     showcats: false,
     dots: false,
     showslides: 2
    }
   );
})
</script>
<div id="announce"></div>
```

**Reference Data**

None

**Return Value:**

None


**Additional Carousel Dependancies**

- Slick plugin

**Example Screenshot**

![Alt Carousel](../../assets/images/pickcarousel.jpg "Carousel"){: .theImage}
