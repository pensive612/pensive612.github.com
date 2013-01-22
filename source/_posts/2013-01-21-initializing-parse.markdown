---
layout: post
title: "Initializing Parse"
date: 2013-01-21 16:30
comments: true
categories: [parse, codeacademy]
---

{% img right http://puu.sh/1QRgk %}

Okay, picking up off the last section where I talked about my experience with starting
the Parse Lesson on CodeAcademy.

I now have my Parse account and have been instructed to create an app and use my credentials in the app.

Easy enough.  I just clicked on the dropdown, created my app and pressed the copy buttons
to get my strings.  Now time to initialize Parse with my credentials.

<!-- more -->

The next part is super easy.  Just calling the initialize method on the Parse object.
Pass 2 parameters.  Both your *application_id* and *javscript_key*.


``` javascript
// Initializing
Parse.initialize("application_id", "javascript_key");

```

Here's a cool trick, If you have a wide screen, and you maximize it, the result window
will go next to the script window.  Makes it easier to Run the code.

{% img http://puu.sh/1QRvh %}