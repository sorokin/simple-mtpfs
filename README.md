ABOUT
=====

SIMPLE-MTPFS (Simple Media Transfer Protocol FileSystem) is a file system for
Linux (and other operating systems with a FUSE implementation, such as Mac OS X
or FreeBSD) capable of operating on files on MTP devices attached via USB to
local machine. On the local computer where the SIMPLE-MTPFS is mounted, the
implementation makes use of the FUSE (Filesystem in Userspace) kernel module.
The practical effect of this is that the end user can seamlessly interact with
MTP device files.

LATEST VERSION
==============

Latest sources of the software can be found at: [simple-mtpfs][]

INSTALLATION
============

Simple-mtpfs depends on fuse (version >= **2.7.3**) and libmtp. It also
requires the C++ compiler to support **C++11** standard.

To install the driver, follow these steps:

    $ mkdir build && cd build
    $ cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo ..
    $ make
    $ make install (as root)

MOUNTING
========

To mount MTP-based device to your local filesystem, simply run:

    $ simple-mtpfs mountpoint [options]

If you have more than one MTP device attached to the computer, it is possible
to specify which device, you are willing to mount. Either by entering its **order
number** or special file usually placed in `/dev`:

MOUNTING BY NUMBER
------------------

    $ simple-mtpfs --device <number> mountpoint [options]

Where the `<number>` should contain a numeric order of the device, you are
about to mount. To get a list of all attached devices, execute following:

    $ simple-mtpfs --list-devices
    <number>: <device name>
    <number>: <device name>
    ...

MOUNTING BY SPECIAL FILE
------------------------

Enter special device file as the first argument to simple-mtpfs. The special device
file is usually named as `/dev/libmtp-*`.

    $ simple-mtpfs <device> mountpoint [options]

UNMOUNTING
==========

To unmount MTP device, execute following command:

    $ fusermount -u <mountpoint>

BUG REPORTS
===========

Report bugs to [simple-mtpfs issues][].

[simple-mtpfs]: https://github.com/sorokin/simple-mtpfs "simple-mtpfs repository on github"
[simple-mtpfs issues]: https://github.com/sorokin/simple-mtpfs/issues "Report a bug"
