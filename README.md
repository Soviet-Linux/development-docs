Development Docs
================

These docs were made to help make sure that everybody is on the same page with development and to help other people understand the architecture of this project.

Topics
======

The Packages/Repo
-----------------

This system will use the Soviet-Linux/OUR repo to get the list of packages. 

Right now, we are using a system where we get the packages from the source that they come from. This is similar to how another distributibution, called [Source Mage](https://sourcemage.org), works. 

There are many different stratagies that have been preposed, including:

1. Using torrents to distribute program files (and github repo for torrent files and checksums)
2. Some central server to distribute program files 
3. (Hybrid) Have people opt into opening a port and serving the package files they have installed to other people (checksums and lists of all programs on a github repo)
4. (Our current system) Distribute build instructions and package lists on github and have people get them from the makers

Installers/Package Managers
---------------------------

I don't know what is going on with this. There is the CCCP thing that is being developed. In the Soviet channel, people were talking about having an installer and a package manager. I don't know what should be done for that. 

If anybody has insight, please edit this section. You have write access to this repo.

Repos/Projects
==============

The CCCP
--------

People working on the CCCP right now, please explain how it works and the functions in it right here.

The OUR
-------

This is the main repo for the CCCP and Soviet Linux. I decided to move the package files out of the CCCP because it was messy. 

Useful Information
==================

Login for live ISO
------------------

Username: root
Password: 200489

Tip for people using a qwerty keyboard: You have to hold shift to type numbers

Changing layout to qwerty
-------------------------

Use the command:

`loadkeys /usr/share/keymaps/i386/qwerty/us.map.gz`

Translated to the keys pressed on a qwerty keyboard, that is:

`loqdkeys >usr>shqre>key;qps>i#*&>azerty>us<;qp<gw`

