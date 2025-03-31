I've encountered following error while building a debian package, could happen in other places too.
Culprit - Windows style line endings `CRLF` instead of Linux syle `LF`

As far as I can tell only happens with make shabang `#!/usr/bin/make -f`

```
: No such file or directory
cc      -o .o
cc: fatal error: no input files
compilation terminated.
make: *** [<builtin>: .o] Error 1
dpkg-buildpackage: error: fakeroot debian/rules clean subprocess returned exit status 2
```
