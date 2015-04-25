---
layout: default
title: RVM and Ruby-based services started with init.d or upstart
permalink: /integration/init-d/
---

# Using RVM and Ruby-based services that start via init.d or upstart

To use any Ruby application that needs to be started with `init.d` or `upstart`
(e.g., god, unicorn, thin) with RVM, you need to generate a wrapper script.
Namely, you need to set it up so that there is an alternative executable that
loads the correct ruby and gems environment (run this in your shell):

    rvm alias create my_app ruby-2.0.0-p247@my_app
    # rvm wrapper my_app --no-links unicorn_rails # only for RVM 1.24 and older

This will generate a wrapper that can be referenced in the `init.d` script or
in `upstart` configuration:

    /usr/local/rvm/wrappers/my_app/unicorn_rails

Where:

- `/usr/local/rvm` - is `echo $rvm_path`
- `wrappers`       - is static always the same
- `my_app`         - is the alias name
- `unicorn_rails`  - is the command that is being wrapped

Example scripts:

- [`init.d unicorn`](https://github.com/rvm/rvm/blob/master/contrib/unicorn_init.sh)
- [`init.d smfbot`](https://github.com/rvm/rvm-site-setup/blob/master/conf/smfbot.rc)
