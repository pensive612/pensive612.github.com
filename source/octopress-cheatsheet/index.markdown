---
layout: page
title: "My Octopress Cheatsheet"
date: 2013-01-21 5:59
comments: true
sharing: true
footer: true
---

So it would seem lots of people are creating Octopress Cheatsheets on their blog.
And I quickly see why.

Here's the first heads up.  Every time I run any task, I get:

```
rake aborted!
You have already activated rake 10.0.3, but your Gemfile requires rake 0.9.2.2.
Using bundle exec may solve this.
```

After researching a bit, its obviously a conflict with my gemlock file and 2 different
versions of rake.

However, rather than modify anything.  People say you should be using ```bundle exec``` first anyway.

So for now, imagine I'm prefixing any rake command with ```bundle exec```  Yes.  It is as fun as it sounds.

#### Site Generating

```
rake generate # Use this to generate the newly create posts and pages
rake watch    # Watch for changes while you're editing source files
rake preview  # Watch and Create server at localhost:4000
rake deploy   # Commits and deploys your site to the remote branch

```

#### Content Generators
*Although as of now, the generators appear a bit broken for me, maybe it just needs new documentation.  not sure.*

```
rake new_post["Zombie Ninjas Attack"]
# Should work, but doesn't for me.  Instead I have to use
rake new_post
# It asks me the title, and I give it.  Not bad...
```

The header generates the following:

```
---
layout: post
title: "Zombie Ninjas Attack"
date: 2011-07-03 5:59
comments: true
external-url:
categories:
---

# You could also add
published: false

# Remember, categories is an array []
```

and for pages
```
rake new_page[super-awesome]
# should work, but doesn't at all for me.
```
So I manually create the file in source/

ie.  source/cheatsheet/index.markdown

And manually need to copy the headers:

```
---
layout: page
title: "Page Title Here"
date: 2011-07-03 5:59
comments: true
sharing: true
footer: true
---
```


*On a sidenote. Its almost mandatory to use some sort of LiveReload with rake preview these days.
I can't imagine editing pages without it anymore. Funny how quickly things change.

But I noticed you need to set a delay on LiveReload otherwise, it works faster than preview server.

I've set mine to 1 second, and it works great.

{% img http://puu.sh/1QHnk %}