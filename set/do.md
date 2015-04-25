---
layout: default
title: The do set operation
permalink: /set/do/
---


## Usage

    ∴ rvm [all|all-gemsets|<ruby>,...|<path>] [--verbose|--summary|--yaml|--json] do <command> ...
    ∴ rvm in <path> do <some-command> ...
    ∴ rvm-exec [all|all-gemsets|<ruby>,...|<path>] [--verbose|--summary|--yaml|--json] <command> ...

Executes arbitrary commands against given a set of rvm environments.
Without additional flags it will exec the command directly without printing
out extra rvm information.

## Selectors:

 - `all`         - execute command in the default gemset of all rubies
 - `all-gemsets` - execute command in the all gemset for all rubies
 - `<ruby>,...`  - list of rubies to use, allows short versions or gemsets
 - `<path>`      - use ruby from the given path/project

## Modifiers:

- `in`        - works with path and will additionally `cd` to the given directory
- `--verbose` - display one line details about ruby/gemset
- `--summary` - hide output and display summary of failures/success list only
- `--yaml`    - hide output and display yaml summary of failures/success list only
- `--json`    - hide output and display json summary of failures/success list only

## Caveats

If using the set do operation when scripting, use rvm-exec (usually installed to `~/.rvm/bin/rvm-exec`). Using `~/.rvm/bin/rvm` instead will cause RVM to spawn a bash shell, which is undesireable in the context of process monitoring.

## Examples:

To execute `ruby -v` against all installed rubies and aliases, you would run:

    ∴ rvm all do ruby -v

If you want to execute it against a specific ruby (without extra logging / data
printed by rvm as is done with normal set operations), you can instead do:

    ∴ rvm ree do ruby -v

Since it is a set operation, normal ruby specifiers will work. As an example, to run
`gem list` against **2.0.0** and **2.1.1** and prefix with ruby name, you would run:

    ∴ rvm 2.1.1,2.0.0 --verbose do gem list

Or, to execute `gem env` against all gemsets:

    ∴ rvm all-gemsets do gem env

To execute `which ruby` in the current directory, loading a `.rvmrc`:

    ∴ rvm . do which ruby

To execute `rake test` in the project directory, loading a `.rvmrc`:

    ∴ rvm in /path/to/project do rake test

For more information, refer to the rvm set operations.
