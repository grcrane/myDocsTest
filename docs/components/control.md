---
layout: default
title: Control 
parent: Components 
nav_order: 62
---

### Control

Controls the display of any blog or event collections as one of:

- Slick carousel
- Grid
- Team Members
- Flex Boxes 

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
      <td>Required.<br>This is the internal slug (key) assigned to the collection.  You can find this by looking going to the page settings -> General, under URL SLUG.</td>
    </tr>
    <tr>
      <td><em>Display Type</em></td>
      <td>Required.<br>Identifies the display type requested.  Must be one of "grid", "carousel", "team" or "flexboxes".  These are case sensitive parameters. </td>
    </tr>
    <tr>
      <td><em>Attributes</em></td>
      <td>Optional.<br>Identifies parameters to override default values.  The parameters are passed in a object array of key/value pairs.  Each display type has different default values as described below. </td>
    </tr>
  </tbody>
</table>

**Attributes:**

<table class="ws-table-all notranslate"> 
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Attribute</td>
     <td>Description</td>
    </tr>
    <tr>
      <td>filter</td>
      <td>Defines if filtering checkboxes (or radio buttons) are to be displayed.  Valid values are "true" or "false".  </td>
    </tr>
    <tr>
      <td>groups</td>
      <td>Overrides the default groups used for filtering.  This is a comma delimeted
      list of group names found in the categories spreadsheet.</td>
    </tr>
    <tr>
      <td>showcats</td>
      <td>Defines if categories are shown for each blog entry. Valid values
      are "true" or "false".</td>
    </tr>
    <tr>
      <td>showcount</td>
      <td>Defines if a count of filtered and total number of blog items is shown. Valid values are "true" or "false"</td>
    </tr>
    <tr>
      <td>findcats</td>
      <td>Defines a comma delimted list of categories which will be included
      in the blog entries.</td>
    </tr>
    <tr>
      <td>dots</td>
      <td>Defines if navigation dots are shown below a carousel. Valid values are "true" or "false".   This is only valid for "carousel" display type, otherwise it is ignored.</td>
    </tr>
  </tbody>
</table>


**Example code block for control**

```
<script>
$(document).ready(function() {
  collectionControl(
    '#demo2',
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
<div id="demo2"></div>
``` 

**Example Team Members code block**

**Pages**: 

- About Us -> People

This code block can be found on the *About Us -> People page*.   It will display team members from the **Team Members** blog with the slug name "**team-members**", using the display type "**team**".  All additional attributes are turned off so categories and filter checkboxes are not shown, as an example. 

```
<script>
$(document).ready(function() {
  collectionControl(
    '#teamContainer',
    'team-members',
    'team', 
    {filter: false, 
     showcount: false,
     groups: '',
     showcats: false,
     findcats: '',
     dots: true}
  );
})
</script>
<div id="teamContainer"></div>
```

**Example Flex Boxes code block**

**Pages**: 

- Home

This code block can be found on the *Home* page.  It will display the flex boxes from the **Flex Boxes** blog with slug name "**flex-boxes**", using the display type of "**flexboxes**".  Attitional attributes are currently ignored for flex boxes and not needed.  

```
<script>
$(document).ready(function() {
  collectionControl(
    '#flexBoxes',
    'flex-boxes',
    'flexboxes'
  );
})
</script>
<div id="flexBoxes"></div>
```

**Example Carousel code block for Announcements**

**Pages**: 

- Home, Ann Arbor Hands-on Museum
- Visit -> Leslie Science & Nature Center
- Visit -> Challenger Learning Center (filter unity)

This code block can be found on the *Home* page, for Announcements.  It will display the an infinite carousel from the **Announcements** blog with slug name "**announcements**", using the display type of "**carousel**".  

```
<script>
$(document).ready(function() {
  collectionControl(
    '#announce',
    'announcements',
    'carousel',
    {filter: false, 
     showcount: false,
     groups: '',
     showcats: false,
     findcats: '',
     dots: false} 
   );
})
</script>
<div id="announce"></div>
```

**Example Carousel code block for Promotions**

**Pages**: 

- Home

This code block can be found on the *Home* page, for Promotions.  It will display an infinite carousel loop from the **Promotions** blog with slug name "**promotions**", using the display type of "**carousel**".  No categories, total count or filtering will be shown. 

```
<script>
$(document).ready(function() {
  collectionControl(
    '#promodiv',
    'promotions',
    'carousel',
    {filter: false, 
     showcount: false,
     groups: '',
     showcats: false,
     findcats: '',
     dots: false} 
   );
})
</script>
<div id="promodiv"></div>
```

**Example Carousel code block for Site Features**

**Pages**: 

- Visit -> Ann Arbor Hands-on Museum (filter Ann Arbor)
- Visit -> Leslie Science & Nature Center (filter Leslie Center)
- Visit -> Yankee Air Museum (filter Yankee)

This code block can be found on the *Home* page, for Promotions.  It will display an infinite carousel loop from the **Site Features** blog with slug name "**site-features**", using the display type of "**carousel**".  No categories, total count or filtering will be shown.  In this case, we are only showing blog entries that have a category of "Ann Arnor". 

```
<script>
$(document).ready(function() {
  collectionControl(
    '#featuresdiv',
    'site-features',
    'carousel',
    {filter: false, 
     showcount: false,
     groups: '',
     showcats: false,
     findcats: 'Ann Arbor',
     dots: false} 
   );
})
</script>
<div id="featuresdiv"></div>
```

**Example Grid code block for Outreach Blog**

**Pages**: 

- Learn -> Outreach 
- About Us -> Jobs List

This code block can be found on the *Learn -> Outreach* page, for Outreach.  It will display a grid format of the blog entries in slug name **outreach-1**, using the display type of **grid**.  Filtering is specified by the group names, which will display checkboxes for **Grades** and **Outreach**.   

```
<script>
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

**Example Grid code block for Field Trips Blog**

**Pages**: 

- Learn -> Field Trips

This code block can be found on the *Learn -> Outreach* page, for Outreach.  It will display a grid format of the blog entries in slug name **field-trips-1**, using the display type of **grid**.  Filtering is specified by the group names, which will display checkboxes for **Field** group.   

```
<script>
$(document).ready(function() {
  collectionControl(
    '#filterField',
    'field-trips-1',
    'grid',
    {filter: true, 
     groups: 'field',
     showcats: true,
     showcount: true,
     dots: false}
  );
})
</script>
<div id="filterField"></div>
```

**Example Grid code block for Distance Learning Blog**

**Pages**: 

- Learn -> Distance Learning

This code block can be found on the *Learn -> Distance Learning* page, for Distance Learning.  It will display a grid format of the blog entries in slug name **distance-learning-1**, using the display type of **grid**.  Filtering is specified by the group names, which will display checkboxes for **Field** group.   

```
<script>
$(document).ready(function() {
  collectionControl(
    '#filterDistance',
    'distance-learning-1',
    'grid',
    {filter: true, 
     groups: 'grades,distance',
     showcats: true,
     showcount: true,
     dots: false}
  );
})
</script>
<div id="filterDistance"></div>
```

**Example Locations code block for Directions Blog**

**Pages**: 

- About Us -> Directions

This code block can be found on the *About Us -> Directions* page, for Directions.  It will display a maps and directions of the blog entries in slug name **reference-data/location-maps**, using the display type of **locations**.    

```
<script>
$(document).ready(function() {
  collectionControl(
    '#locationOut',
    '',
    'locations',
    {filter: false, 
     groups: '',
     showcats: false,
     showcount: false,
     dots: false}
  );
})
</script>
<div id="locationOut"></div>
```

**Example Address code block for Reference-data address**

**Pages**: 

- Home
- Leslie Science & Nature Center

This code block can be found on the *Home, Leslie* page(s), for Address, hours and admission information.  It will display a address information from the blog entries in slug name **reference-data/address-hours**, using the display type of **address**.    

```
<script>
$(document).ready(function() {
  collectionControl(
    '#addressOut',
    '',
    'address',
    {museum: 'aahom'}
  );
})
</script>
<div id="addressOut"></div>
```

**Example Calendar code block for Reference-data calendars**

**Pages**: 

- Leslie Science & Nature Center
- About Us -> Calendars

This code block can be found on the *Leslie* page(s), for maps and directions.  It will display a map information from the blog entries in slug name **reference-data/calendars**, using the display type of **calendars**.    

```
<script>
$(document).ready(function() {
  collectionControl(
    '#calendarsOut',
    '',
    'calendars',
    {activetab: 2,
     collapsed: true}
  );
})
</script>
<div id="calendarsOut"></div>


```