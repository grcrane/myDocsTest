---
layout: default
title: Lazy Summary
parent: Components
nav_order: 57
---

### Lazy Summary

Lazy Summary is a paid plugin which extends the 30 post limit that SquareSpace imposes.  Once a summary block is defined, regardless of the type (carousel, grid, etc), SquareSpace will normally limit the number of entries displayed to 30.  This plugin adds some JavaScript tricks behind the scenes to get around that limit.  

The following code is from the vendor.  It needs to be inserted into the site Advanced, Code Injection Footer section:

```
<script src="https://assets.squarewebsites.org/lazy-summaries/lazy-summaries.min.js"></script>
<script>
!function(){window.self===window.top||window.top.document.getElementById("lazy-summaries-admin")||function(e,t,s,i,a){if(s.querySelector("#"+t))i&&i(this);else{var n=document.createElement("script");n.src=e+"?cache="+((new Date).getTime()+"").substr(0,8),n.id=t,n.onload=function(){a&&this.remove(),i&&i(this)},s.appendChild(n)}}("https://assets.squarewebsites.org/lazy-summaries/lazy-summaries-admin.js","lazy-summaries-admin",window.top.document.getElementsByTagName("head")[0])}();
</script>
```

Support:  

Contact michael@squarespacewebsites.com for support.  The purchase was made using email address georgecrane@mac.com.   It is a one-time purchase and can be used for every on as many sites as we like.   It was purchased in September of 2021. 

Note: When I originally purchased the plugin, I accidently used georgecrane@mac.comx (notice comx instead of com).  The vendor could not change that, so I opened up a new account in georgecrane@mac.com and he made a note about the issue. 

