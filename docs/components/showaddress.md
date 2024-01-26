---
layout: default
title: Address Info Box <span class="new">(Updated)</span>
parent: Components
nav_order: 52
---

### Address Info Box

Museum address and information box.  Gets data from spreadsheet and displays as three blocks of information.  (1) Address; (2) Hours of operations; (3) Admissions information.  Standard museum colors are used. 

***Cook book***
- Edit the page
- Click a "+" sign where you want to insert 
- Select "Code"
- Paste the following code block
- Adust parameters as needed

**Code block for address info block**
```
<script>
$( document ).ready(function() {
  showAddressInfo('#addressContainer', 'leslie'); 
});
</script>
<div id="addressContainer"> 
``` 

**Overrides:**

None

**Usage:**

*showAddressInfo(Selector, Museum)*

**Parameters:**

<table class="ws-table-all notranslate"> 
  <tbody>
    <tr class="tableTop">
     <td style="width:120px">Parameter</td>
     <td>Description</td>
    </tr>
    <tr>
      <td>SelectorID</td>
      <td>Required.<br>jQuery selector identification where the resulting html code will be generated.</td>
    </tr>
    <tr class="w3-white">
      <td>Museum</td>
      <td>Optional.
        <ul>
          <li>aahom=Ann Arbor Hands On (default)</li>
          <li>leslie=Leslie Science</li>
          <li>yankee=Yankee Air Museum</li>
          <li>challenger=Challenger Learning center</li>
          <li>experience=Experience Center</li>
        </ul>
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
      <td>aahom220@gmail.com</td>
    </tr>
    <tr>
      <td>File Name</td>
      <td>Hours Pricing</td>
    </tr>
    <tr>
      <td>Folder</td>
      <td><a href="https://drive.google.com/drive/folders/1YaVLSr9quHsbMDChBrlZUjpI_ZeG0cG-" target="_blank">UIL_Web_Site_Docs</a></td>
    </tr>
    <tr>
      <td>Link</td>
      <td><a href="https://docs.google.com/spreadsheets/d/1eBU2TqbjAT0-PUkKVa0J9obsoyIBJ7ib_KJMQLNym8Y/edit#gid=0" target="_blank">Hours Pricing Spreadsheet</a></td>
    </tr>
    <tr>
      <td>ID</td>
      <td>1eBU2TqbjAT0-PUkKVa0J9obsoyIBJ7ib_KJMQLNym8Y</td>
    </tr>
    <tr>
      <td>Sheet Name</td>
      <td>Hours</td>
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
    <td>Museum</td>
    <td>Optional, selects the museum information to display
        <ul>
          <li>aahom=Ann Arbor Hands On (default)</li>
          <li>leslie=Leslie Science</li>
          <li>yankee=Yankee Air Museum</li>
          <li>challenger=Challenger Learning center</li>
          <li>experience=Experience Center</li>
        </ul>
     </td>
  </tr>
  <tr>
    <td>B</td>
    <td>Address Title</td>
    <td>Title line for address block</td>
  </tr>
  <tr>
    <td>C</td>
    <td>Address Content</td>
    <td>Content for the address block (left block)</td>
  </tr>
  <tr>
    <td>D</td>
    <td>Hours Title</td>
    <td>Title line for hours block</td>
    </tr>
    <tr>
    <td>E</td>
    <td>Hours Content</td>
    <td>Content for the hours block (middle block)</td>
    </tr>
    <tr>
    <td>F</td>
    <td>Admission Title</td>
    <td>Title line for admissions block</td>
  </tr>
    <tr>
    <td>G</td>
    <td>Admission content</td>
    <td>content for the admissions block (right block)</td>
    </tr>
  </tbody>
</table>

**Example Screenshot**

![Alt Address Info Box](../../assets/images/address_info_box.jpg "Address Info Box"){: .theImage}