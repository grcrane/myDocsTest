---
layout: default
title: Calendars <span class="new">(05/07/23)</span>
parent: Components
nav_order: 2.2
---

### Calendar of Events

The Calendar of Events custom function grabs CSV data from "reference-data/calendars" blog entry for the list of calendars, Google calendar id and links.   It also gets reference data from "refeerence-data/museum-list", which identifies the museums that are currently being included/hidden.   Calendars are organized and displayed in a tabbed list.  In addition to each museum calendar, the combination of all included calendars is displayed as the first tabbed item called "All Locations".  test

The Calendar of Events block is emplimented by adding a code block to the page with the following:

**Code block for Calendar of Events**
```
<script>
$(document).ready(function() {
  collectionControl(
    '#calendarsOut',
    '',
    'calendars',
    {activetab: 1,
     single: false,
     openFirst: false,
     collapsable: false,
     collapsed: false,
     title: "View Calendars",
     showPrint: false,
     showTabs: false,
     showTitle: false,
     showName: false,
     showNav: true,
     showDate: true,
     showTz: true,
     mode: "MONTH",
     showCalendars: false}
  );
})
</script>
<div id="calendarsOut"></div>