---
layout: default
title: Icon Bars <span class="new">(06/04/22)</span>
parent: Components
nav_order: 4
---

## Icon Bars

Icon Bars appear either attached to the top header image and/or the bottom footer on
all pages.  The icons displayed are saved in /reference-data/iconbar

### Quick try

Paste the following into a SquareSpace code block to see how it works:

```
<script>
$( document ).ready(function() {
  addIconBar('header');
})
</script>
```

**Note 1:** This code will attempt to attach the header bar to the bottom of the first section that it finds.  If the first section is not a header image then the results may not be what is expected.

**Note 2:** Since the footer appears on all pages, the above code is pasted into a Footer code block.  as:

```
<script>
$( document ).ready(function() {
  addIconBar('footer');
})
</script>
```

**Usage**

*addIconBar(Where)*

**Parameters:**

<table class="ws-table-all notranslate">
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Parameter</td>
     <td>Description</td>
    </tr>
    <tr>
      <td><em>Where</em></td>
      <td>Required.<br>Identifies the location of the icon bar.  Must be either "footer" or "header"</td>
    </tr>
  </tbody>
</table>


**Reference Data**

- [/reference-data/icon-bar](../reference/reficonbar.html).

**Return Value:**

None


**Example Screenshot**

![Alt Icon Barl](../../assets/images/pickiconbar.jpg "Icon Bar"){: .theImage}