---
layout: default
title: 'rvm gemset clear' - Clear any currently selected gemset.
permalink: /gemsets/clear/
---

# Clear any currently selected gemset

Assume that you are already using the teddy gemset.

```
$ rvm gemset use teddy
Now using gemset 'teddy'
```

And that you now wish to switch back to using the default gems directory for the currently selected ruby.

You can accomplish this using gemset clear:

```
$ rvm gemdir
/Users/rys/.rvm/gems/2.1.1@teddy
$ rvm gemset clear
gemset cleared.
$ rvm gemdir
/Users/rys/.rvm/gems/2.1.1
```
