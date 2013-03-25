# Lua-rados - RADOS bindings for Lua

Source for Lua bindings for RADOS, which is a reliable, autonomic, distributed 
object store comprised of self-healing, self-managing, intelligent storage nodes. RADOS is part 
of the Ceph project. http://ceph.com/ 

[![Build Status](https://travis-ci.org/noahdesu/lua-rados.png)](https://travis-ci.org/noahdesu/lua-rados)


## Information
 
 * LuaDoc documentation http://noahdesu.github.com/lua-rados/
 * Source code [available on GitHub] https://github.com/noahdesu/lua-rados


## Getting Help
 
 * Please report bugs on the [issue tracker] https://github.com/noahdesu/lua-rados/issues

## Dependencies

* autoconf 
* automake 
* libtool
* lua5.1
* luarocks
* ceph

## Ceph Installation 

* Instructions From:
http://ceph.com/docs/master/install/debian/

* Install Release Key
```
$ wget -q -O- 'https://ceph.com/git/?p=ceph.git;a=blob_plain;f=keys/release.asc' | sudo apt-key add -
```
* Add Release Packages
```
$ echo deb http://ceph.com/debian-bobtail/ $(lsb\_release -sc) main | sudo tee /etc/apt/sources.list.d/ceph.list
```
* Install packages
```
$ sudo apt-get update
$ sudo apt-get install ceph
$ sudo apt-get install librados-dev
```
## Lua-rados Installation 

* Build Lua-rados
```
$ git clone git://github.com/noahdesu/lua-rados.git
$ cd lua-rados
$ autoreconf -I m4 -ivf
$ ./configure && make
```
* Install Busted
```
$ sudo luarocks install busted
```
## Setting up and Starting Ceph

* Follow these instuctions 

http://ceph.com/docs/master/start/quick-start/

## Testing Lua-rados

* After you set up and start ceph
$ eval `luarocks path``
$ export LUA_CPATH="$PWD/.libs/?.so;$LUA_CPATH\"
$ busted test.lua
