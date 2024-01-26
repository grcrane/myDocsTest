---
layout: default
title: Gallery Slideshow
parent: Components
nav_order: 61
---

### Gallery Slideshow

Used to provide an image slideshow as the page header image.  If gallery captions are set on then captions and links are displayed in a black bar at bottom of image.  

This function highly depends on specific SquareSpace selector names and could possible fail later with future SquareSpace changes. 

***How it works***
- Finds the first section on the page that has "div.section-background"
- Finds the first section on the page that has "figure.gallery-grid-item"
- If no gallery found then abort.
- Disables the section-background image by changing css display to none. 
- if not editing the page, disable the gallery section by changing css display to none. 
- Create a set of div's (mySlides) where each is a separate slide and image to replace the header.  
- Call a function "galleryCarousel" to rotate through the set of slides with, currently, 8 second wait time. 
- When it gets to the last slide it will start over at the first. 


***Cook book to create a page header slideshow***
This cookbook assumes you are starting a new page.  If not then
adapt the instructions accordingly. 

- Create a new page
- Click Edit
- Create top section with image block
- Create a gallery section directly after top image block section
- Create another section after gallery to hold your page content
- Save the changes
- Add call to function in Advanced code injection for page
 - Click the wheel for the page
 - Select Advanced
 - Paste the following code block

**Code block for page header slideshow**
```
<script>
$( document ).ready(function() {
    doGalleryShow();
})
</script>
``` 

**Usage:**

*doGalleryShow()*

**Parameters:**

No parameters

**Return Value:**

None