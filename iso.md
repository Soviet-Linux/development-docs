# ISO Creation Instructions

This short guide will guide through the steps of creating a bootable ISO for
Soviet Linux.

> **NOTE:** The process may be subject to changes since Soviet Linux is still
> in early development stage

## 1. Pre-requisites

Before following this guide you should have a copy of Soviet Linux installed
on your system and it should be running. I also advise you install Soviet Linux
alongside another GNU/Linux distribution because not all tools used in this
guide are ported to Soviet Linux. The other system should also have a few common
tools that usually come pre-installed in many distributions such as git, tar
and curl/wget.

## 2. Getting necessary tools

If you installed Soviet Linux using the latest official ISO you should have all
tools installed already on your system. Otherwise you will need to get the
source files and compile these programs.

You will need the following:

- squashfs-tools, available [here](https://github.com/plougher/squashfs-tools)
- mkisofs, which is part of cdreccord available [here](https://sourceforge.net/projects/cdrtools/)

Move the sources for these tools into a folder in your Soviet Linux root directory
and name this folder `livekit`.

In addition to these programs, also download the source of the Linux kernel since
you will need to recompile it to add support for squashfs and overlayfs. The
kernel source can be found [here](https://www.kernel.org/). Grab the latest
stable release. Move the installed tarball into the `livekit` folder.
