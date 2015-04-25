---
layout: default
title: Quicktime
permalink: /integration/quicktime/
---

# QT Ruby

## Ubuntu

```
sudo aptitude install libqt4-core libqt4-dev
```

Download qtruby from http://rubyforge.org/projects/korundum/

```
version=2.1.0
wget http://rubyforge.org/frs/download.php/71843/qt4-qtruby-${version}.tar.gz

Extract qtruby,

```
tar -xvzf qt4-qtruby-${version}.tar.gz
```

```
cd qt4-qtruby-${version}
```

qtruby installer uses the location of the Ruby binary it is started with,

```
rvm use 1.8.7
cmake .
make
``

Now install,

```
sudo make install
```

ubuntu doesn't look here by default, but the qtruby install puts its libraries here

```
sudo ldconfig /usr/local/lib
```

We had to run make install with root because it writes to /usr/local/lib, but
it also writes to $MY_RUBY_HOME.

we don't want root-owned files floating around in there

```
sudo chown -R $USER:$USER $MY_RUBY_HOME
```

NOTE: These are raw notes thanks to mcantor, please feel free to enhance this
page and send a pull request!
