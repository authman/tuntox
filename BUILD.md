* Install libsodium http://doc.libsodium.org/installation/README.html
* Install libtoxcore (libtoxav and the DNS client are not required) https://github.com/irungentoo/toxcore/blob/master/INSTALL.md
* git clone https://github.com/gjedeer/tuntox.git
* cd tuntox
* make

The makefile creates a static binary by default. If you're not a fan of static binaries, remove `-static` from `LDFLAGS`. 

One reason to do so may be if you'd like to resolve hostnames on the tuntox server (invoke client with `-L 80:reddit.com:80` instead of `-L 80:198.41.208.138:80`). 

Static linking breaks hostname resolution, but IMHO the pros overweight the cons.

## MacOS build
Basically the same as above but:

* static compiling is removed - you can't do this on MacOS platform (no, just don't)
* because of removed `-static` you can't resolve hostnames (you can always put it into `hosts` file in your system)

If you'd like to build on Mac do: `make -f Makefile.mac`

