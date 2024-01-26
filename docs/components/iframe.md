---
layout: default
title: Embedded Iframe
parent: Components
nav_order: 59
---

### Embedded Iframe

You can embed a page from the UIL website into the page of a separate website.  When this is done, headers and footers are hidden with "display:none" CSS attribute. Otherwise this is a basic iFrame embed and initial height/width will be honored.

To work best, create a separate minimal page with just the components you want to display
in the remote website.  Do not include header images or extra text that should be
included on the remote site.

**Cook Book**

As an example, to create a field trips iframe page.

- Open the Field Trips page
- In Settings, **Duplicate** page
- Name the duplicate page **Field Trips Iframe**
- Move the new page to the **Embedded Iframes** folder
- Edit to remove un-necessary blocks.
- Save modified page
- On the remote site, include the iframe tag, using the slug from the field trips iframe page.

```
<iframe id="iFrame1" src="http://www.unityinlearning.org/field-trips-iframe" frameborder="0" scrolling="yes" style="height:1500px;width: 100%;overflow-y:scroll;"/>
     </iframe>
```
**Embedded Iframe Screenshot**

![Alt Embedded Iframe](../../assets/images/embediframe.jpg "Embedded Iframe"){: .theImage}