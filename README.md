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

We will be using the CCCP package manager ( CCCP Crafter of Controlled Packages ) , whiwh will be able to either installer binaries compiled with the --create parameter or sources from a .spm (soviet package manager ) file. To create .spm source packages you can look github.com/pkd667/Soviet

667Repos/Projects
==============

The CCCP
--------

The CCCP is the official soviet linux package manager , it can installe .spm files. See Installers/Package Managers

The OUR
-------

This is the main repo for the CCCP and Soviet Linux. I decided to move the package files out of the CCCP because it was messy. 

Useful Information
==================

Login for live ISO
------------------

Username: root
Password: communism>capitalism

Tip for people using a qwerty keyboard: You have to hold shift to type numbers
fuck dont show this password and forget about it please

Changing layout to qwerty
-------------------------

No need I will fix it very soon 


