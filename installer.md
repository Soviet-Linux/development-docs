# revolution-installer
The installer of the Soviet-Linux operating system.

## Usage Introduction

This document outlines the technical specifications and implementation
of the program revolution-installer developed for Soviet Linux by the
Soviet Linux development team and its front-end, Revolution. If you have
inquires on this document or you wish to suggest changes please do so in
our official Discord server.

Running Revolution-installer
============================

Revolution-installer comes pre-packaged in the Soviet Linux official ISO
image and can be executed as root user in bash by running the
`revolution` command. This will execute the Revolution front-end program
which will guide the user trough the installation process using TUI
prompts. In addition it will also provide a \"one command\" installation
process, which consists in executing the `revolution` command with a set
of arguments to configure the system.

The Revolution-installer API
============================

The Revolution-installer provides an API to install the system. This API
is specific for the Soviet Linux system, however it could be ported to
another operating system. The API makes use of the CCCP package manager
and its library to install the system and additional packages.

Locale
------

### setlocale

The `setlocale` API call will set the specified locale

### showlocale

The `showlocale` API call will display all available locale

Keyboard format
---------------

### setkb

The `setkb` API call will set the keyboard according to the argument
passed by the user. It follows the standard naming scheme for keyboards

### listkb

This API call will return a list of keyboard layouts that can be chosen
by the user.

Hostname
--------

To set a user defined hostname use the `sethost` API call. It will set
the hostname for the system to be installed.

Time Zone
---------

### listzones

Returns a list of available zones. This API call will work differently
depending on the argument passed. If the argument is an empty string or
a NULL pointer the return will be a list of string representing the
continent of the time zone. Otherwise if the argument is a continent
then it will return a list of time zones available.

### setzone

Set the time zone. It accepts two strings as arguments: one for the
continent one for the time zone.

Root user and User creation
---------------------------

### setrootpasswd

This API call sets the root password. It accepts one string argument.

### createuser

This API call creates a new user. By default revolution-installer will
set the default user settings as defined in `man useradd`, however it is
possible to add additional arguments to this API call to change its
behaviour. Here is a list of acceptable arguments:

This function returns an integer, defined as user id. Store this value
as it will be necessary to complete the user setup.

### setuserpasswd

This API call sets the user password using the argument passed. It
require a user id to be passed as argument.

User Goups
----------

After a user is created use the following calls to set its groups. It is
necessary for a user to be already created for these calls to work
properly.

### listgroups

Given a user id, returned by `createuser`, it will return a list of
groups structures. These structures contain the group name as well as a
value indicating if the user is part of these groups: 1 if it is, 0 if
it is not.

### setgroups

Sets the groups for the user. Specify the groups in a list of groups
structures and provide a user id.

Network
-------

Soviet Linux only officially supports only wired connections at the time of
writing, so revolution-installer will support only those as well. This will be
changed in future versions of the software.

Installation Medium Selection
-----------------------------

Revolution-installer supports multiple ways to install the system. It is
possible to install Soviet Linux from the local ISO, from the official
rootfs tarball or trough the CCCP. The CCCP option require the system to
be recompiled from scratc hbut it will provide the most up to date
packages, while the tarball and the ISO will be faster to install but
might be out of date.

### setinstmethod

This call sets the installation method. It accepts one of the following
arguments:

LOCAL

:   uses the local ISO image to install the system

TARBALL

:   uses the rootfs tarball to install the system

SOURCE

:   uses CCCP to install the system

Disk partition
--------------

Disk partition will occur trough the use of libparted, which is part of the
parted package.

File system
-----------

### setfs

Accepts a disk id and a fs type. It will format the disk with that file
system.

System Installation
===================

After the setup is complete to install the system make the `install` API
call. This call will begin the installation process following these
steps:

-   Partition the disk

-   Install the fs

-   Fetch the base system, if TARBALL is selected. It will fetch and
    compile the preliminary tools if SOURCE is selected.

-   Unpack the downloaded tarball

System configuration and Deployment
===================================

In addition to standard installation and configuration,
revolution-installer also offers the ability to create and export
configuration files containing a list of packages to be installed at
system installation. These config files should be standard and portable
and should work on any Soviet Linux system. The config file used at
system installation is conserved for future use in
/etc/revolution.d/config.rev file.

revolution export
-----------------

To help with the creation of config files, revolution-installer offers a
simple program that will create a config file based on the current
system. The file will be then saved in the path specified by the passed
argument.

config.rev specification and syntax
-----------------------------------

The config files used by revolution-installer should use the .rev
extension and they should follow a specified standard and syntax.

To install in the system move the executable into `/bin` or `/usr/bin` if `/bin`
is a symlink.
