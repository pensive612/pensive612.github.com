---
layout: post
title: "Basic Objects in Parse"
date: 2013-01-21 17:03
comments: true
categories: [parse, codeacademy]
---

Creating an object in [Parse](https://parse.com/) is the foundation of the API.

Without it.  You really don't have anything.  Not even this blog post.



Here's the important steps as I've seen them so far:

``` javascript
// Extend the Parse.Object
var Character = Parse.Object.extend("Character");
```

<!-- more -->

*Keep in mind that Classes get CapitalCase.
And instances will get snakeCase*.  It helps to be able to decipher variable types at a quick glance.

``` javascript
// Create a new instance of the object
var character = new Character();
```

Now its time to set/get some keys on the object

``` javascript
// Setting a key/value on the instance
character.set('name', 'nelson');
```

And I'm sure you know it doesn't mean a thing til you save that thing.
``` javascript
// Save it to the database
character.save();
```

Still frustrating that I'm dealing with bugs in the CodeAcademy/Parse tutorial app.
As well as inconsistencies in the text.

I've now created my object.  I'm fairly certain its correct.  But can't get the code
to run.  And have no idea if its my code or the checker.

This is what I have:

``` javascript
// extend the subClass
var Post = Parse.Object.extend("Post");

// create instances of the subClass
var post = new Post();
var post2 = new Post();

// set and save the objects
post.set('text', 'got some text in here');
post.save();

post2.set('text', 'look at me, saving text');
post2.save();
```

Argh.  Might have to skip over the Parse tutorial for now and come back to it.

Oh wait!  After waiting long enough to type this entry out.  I'm now allowed to
test my code.  That i know is correct.

{% img http://puu.sh/1QSsH %}

Oops try again.
Wait, 'like' key?  That's not even in this step.

Bah.

Hint repeating the exact same text above it?

{% img http://puu.sh/1QSx6 %}

Bah.

Looks like I picked the wrong week to quit sniffing glue.

Another time then...

#### Wait!

Hoozah!  The coderunner has finally decided it will give my exact same code another
chance.  And guess what!  It works!

Woot woot.

Hmm.  maybe this is some new alternative learning method.  Make you read your code a hundred
times.  Make you read the docs a hundred times.  Get frustrated.  yell, research.

And just when its realy sunk in.  BAM!  That very same original code is now acceptable.

Very alternative... Kudos Parse and CodeAcademy.  Kudos.
