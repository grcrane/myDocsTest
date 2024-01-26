---
layout: default
title: Code Injection
parent: Components 
nav_order: 59
---

## Code Injection

This will document multiple snipits of code that are included as code injection, which could be found in various places.

- In SquareSpace header/footer
- On page Advanced code injection
- On page as "Code" block

### Site Advanced Code Injection
This is main site code injection.  Code placed in the **Header** or **Footer** sections will be included on all pages.  This is generally used to include global javascript and styles. 

*Follow: Home -> Settings -> Advanced -> Code Injection*

#### Header
Code that will be injected intothe "head" tag on every page of the site

```
<script type="text/javascript" src="https://code.jquery.com/jquery-1.9.1.min.js"></script>
<script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
<!-- Custom museum javascript and styles -->
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/AAHOM/UIL@2e04c73/unity.min.js"></script>
<link rel='stylesheet' href="https://cdn.jsdelivr.net/gh/AAHOM/UIL@2108278/styles.min.css" />
<!-- Slick Carousel plugin -->
<link rel="stylesheet" type="text/css" href="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css"/>
<link rel="stylesheet" type="text/css" href="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick-theme.css"/>
<script type="text/javascript" src="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>
```

Included in the header is:

- jQuery scripts and user interface styles
- Custom javascript and styles for AAHOM
- Slick carousel plugin

#### Footer
Code that will be injected into the template-defined footer on every page of the site 

```
<script src="https://assets.squarewebsites.org/lazy-summaries/lazy-summaries.min.js"></script>
<script>
!function(){window.self===window.top||window.top.document.getElementById("lazy-summaries-admin")||function(e,t,s,i,a){if(s.querySelector("#"+t))i&&i(this);else{var n=document.createElement("script");n.src=e+"?cache="+((new Date).getTime()+"").substr(0,8),n.id=t,n.onload=function(){a&&this.remove(),i&&i(this)},s.appendChild(n)}}("https://assets.squarewebsites.org/lazy-summaries/lazy-summaries-admin.js","lazy-summaries-admin",window.top.document.getElementsByTagName("head")[0])}();
</script>
```

Included in the footer is:

- Lazy Summaries plugin (used to extent the SquareSpace blog limit of 30 items)
- Add link to blog pages to easily return to previous page

### Museum Section Break
The following html is included as "**Code**" on multiple pages to create a section break.

```
<h4 class="museumSectionBreak colorAahom">
Explore the Galleries
</h4>
```

In the above example, the class ***museumSectionBreak*** will display a full width colored bar with the text centered.   The color of the bar is identifed by the ***colorAahom*** class.  Allowable classes for colors are: 

- colorAahom
- colorLeslie
- colorYankee
- colorChallenger
- colorExperience



