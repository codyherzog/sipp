<a href="https://travis-ci.org/SIPp/sipp">
  <img alt="Travis Build Status"
       src="https://api.travis-ci.org/SIPp/sipp.svg"/>
</a>
<a href="https://scan.coverity.com/projects/5988">
  <img alt="Coverity Scan Build Status"
       src="https://scan.coverity.com/projects/5988/badge.svg"/>
</a>

SIPp - a SIP protocol test tool
Copyright (C) 2003-2019 - The Authors

This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation, either version 3 of the License, or (at your
option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
General Public License for more details.

You should have received a copy of the GNU General Public License along
with this program.  If not, see
[http://www.gnu.org/licenses/](http://www.gnu.org/licenses/).

# Documentation

See the `docs/` directory. Hopefully it is also available in html format at:
https://sipp.readthedocs.io/en/latest/

# Building

This is the SIPp package. Please refer to the
[webpage](http://sipp.sourceforge.net/) for details and documentation.

Normally, you should be able to build SIPp by using CMake:

```
cmake .
make
```

There are several optional flags:

```
cmake . -DBUILD_STATIC=1 -DUSE_SSL=1 -DUSE_SCTP=1 -DUSE_PCAP=1 -DUSE_GSL=1 -DUSE_EPOLL=1
```

# Support

I try and be responsive to issues raised on Github, and there's [a
reasonably active mailing
list](https://lists.sourceforge.net/lists/listinfo/sipp-users).

# Making a release

* Update CHANGES.md. Tag release.
* Download zip, `autoreconf -vif`, copy sipp.1, copy include/version.h.
* Create tgz. Upload to github as "binary".
* Run `sudo docker build -t sipp-build docker && sudo docker run -it -v $PWD:/src sipp-build` to create a static binary. Upload this to Github as well.

# Contributing

SIPp is free software, under the terms of the GPL licence (see the
LICENCE.txt file for details). You can contribute to the development of
SIPp and use the standard Github fork/pull request method to integrate
your changes integrate your changes. If you make changes in SIPp,
*PLEASE* follow a few coding rules:

  - Please stay conformant with the current indentation style (4 spaces
    indent, standard Emacs-like indentation). Examples:

```
if (condition) {        /* "{" even if only one instruction */
    f();                /* 4 space indents */
} else {
    char* p = ptr;      /* C++-style pointer declaration placement */
    g(p);
}
```

  - If possible, check your changes can be compiled on:
      - Linux,
      - Cygwin,
      - Mac OS X,
      - FreeBSD.

Thanks,

  Rob Day <rkd@rkd.me.uk>
