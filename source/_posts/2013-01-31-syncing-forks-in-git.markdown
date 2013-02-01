---
layout: post
title: "How to Sync Forks in Git"
date: 2013-01-31 23:48
comments: true
categories: [git]
---

I needed a workflow for a project I was working on where all my code would
be strictly reviewed before it was merged into a repo.

This would be a continuous process for a while.  I came across a great github
page, and merged it with some other advice out there.

This is how we settled on doing it:

<!-- more -->

*******

* The first thing I did was fork the repo.  This allowed me to work on my own codebase
and the PM to have full control over what was brought into their codebase.
{% img http://puu.sh/1VJlp %}

*******

* Next I cloned the repo onto my local machine:
```
git clone git@github.com:pensive612/Adamin-Clone.git
```

*******

* Then I create my development branch on my local machine.
```
git checkout -b full-screen
```

*******

Made my edits.  But wait.  They finished a page that I might want to use to for
extra testing.  Good time to set up my fork syncing process.

*******

It can get confusing with all the variations of the word 'master' out there,
and in one conversation we were already trying to find a new way to refer to
the all out master sync repo.  Without using that confusing word, 'master'

Well, the brains at GitHub thought of a perfect one, if you ask me.

'Upstream'.  That is the name of our sync only repo.

So I add 'upstream' branch to my git remotes.  (I don't need to worry about anything
but read access.  So http is fine.

```
git remote add upstream https://github.com/bigrepo/repo.git
git remote -v
# origin    git@github.com:pensive612/Adamin-Clone.git (fetch)
# origin    git@github.com:pensive612/Adamin-Clone.git (push)
# upstream  https://github.com/bigrepo/repo.git (fetch)
# upstream  https://github.com/bigrepo/repo.git (push)
```

*******

And now for the sync part.

Rather than pulling from my ```remote origin``` like I normally do.  I'm gonna
[fetch](http://git-scm.com/docs/git-fetch) from the ```remote: upstream```.
Which is really just pulling down extra head info into my repo.

So now, just doing
```
git fetch upstream
```

Gives me all this cool branch data from 'Upstream'.

And since we don't sync from 'master' on 'Upstream', we sync from a QA branch.

I now merge that specific branch into my current.

```
git merge upstream/qa-branch
```

And awesome.  I get a recursive commit with all the synced fork data in there.
Ready for me to review my changes.  And get ready to push to my origin.

```
git push origin
```

Once that's done, I log into GitHub and create my pull request.

And we're done.  The circle of life.

Hope that helps somebody out there.

If it doesn't, please don't hesitate to ask me any questions, or show me how I
completely missed the correct way of doing it.


Take care.


