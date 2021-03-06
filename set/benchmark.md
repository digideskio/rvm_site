---
layout: default
title: Benchmarking with RVM
permalink: /set/benchmark/
---

# Benchmarking with RVM

If you have a bit of code that you would like to benchmark across several
versions of ruby all at once you can now do this easily with RVM. Given:

```
$ cat increment.rb
require 'benchmark'

puts RUBY_DESCRIPTION
puts Benchmark.measure do
  y=0
  1000.times do |x|
    y = x + 1
  end
end
```

We can benchmark this code against multiple ruby versions very easily:

```
$ rvm 1.8.6,1.8.7,1.9.1,ree do ruby increment.rb

ruby-1.8.6-p383: ruby 1.8.6 (2009-08-04 patchlevel 383) [i686-darwin10.0.0]

Rehearsal ---------------------------------------------------------------
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.000261)
\------------------------------------------------------ total: 0.000000sec

user     system      total        real
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.000263)

ruby-1.8.7-p174: ruby 1.8.7 (2009-06-12 patchlevel 174) [i686-darwin10.0.0]

Rehearsal ---------------------------------------------------------------
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.001448)
\------------------------------------------------------ total: 0.000000sec

user     system      total        real
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.001364)

ruby-1.9.1-p243: ruby 1.9.1p243 (2009-07-16 revision 24175) [i386-darwin10.0.0]

Rehearsal ---------------------------------------------------------------
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.000096)
\------------------------------------------------------ total: 0.000000sec

user     system      total        real
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.000090)

ruby-enterprise-1.8.6-20090610: ruby 1.8.6 (2008-08-11 patchlevel 287) [i686-darwin10.0.0]
Ruby Enterprise Edition 20090610

Rehearsal ---------------------------------------------------------------
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.000281)
\------------------------------------------------------ total: 0.000000sec

user     system      total        real
benchmarking 'increment.rb'   0.000000   0.000000   0.000000 (  0.000272)
```
