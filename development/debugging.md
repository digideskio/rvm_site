---
layout: default
title: Debugging RVM
permalink: /development/debugging/
---

# Debugging RVM

The easiest way to get help with rvm is to join the #rvm channel on freenode -
You can use a [web-based client](http://webchat.freenode.net/?channels=rvm) if
you don't already have an IRC application. If you're unable to chat in the
channel, make sure you
[register your nick first](http://www.wikihow.com/Register-a-User-Name-on-Freenode).

If you encounter an issue with rvm, you can make it greatly easier for us by
following the steps below. Each one helps provide additional insight into what
is going wrong.

## Tracking Down Bugs

If you do encounter a bug, the first (and most important) information we need is
related to how rvm is loaded. You should first confirm that rvm is loaded as a
function. Do this by running:

```
$ type rvm | head -1
```

which should output "rvm is a function". If it shows anything else, rvm isn't
loading correctly. For information on why this occurs, and how to solve it,
please see [the bottom of the Installation instructions](/rvm/install/).

Next, we'll need two sets of information. Namely, the output of running
'rvm debug', like so:

```
$ rvm debug
```

And the output of running the broken command *with the trace option*, e.g. if
you're having a use problem:

```
$ rvm use ree
```

you would need to try running it as:

```
$ rvm --trace use ree
```

To share this information with us in IRC, use a site like
[gist](http://gist.github.com/) or [pastie](http://pastie.org/). We prefer gist,
as it lets us easily fork your results and provide edited output; but either
will suffice.

Lastly, please ensure you've read
[How to Report Bugs Effectively](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html)
in order to speed up the whole process.
