Development Docs
================

These docs were made to help make sure that everybody is on the same page with development and to help other people understand the architecture of this project.

The Packages/Repo
------------

This system will use the Soviet-Linux/OUR repo to get the list of packages. 

Right now, we are using a system where we get the packages from the source that they come from. This is similar to how another distributibution, called [Source Mage](https://sourcemage.org), works. 

There are many different stratagies that have been preposed, including:

1. Using torrents to distribute program files (and github repo for torrent files and checksums)
2. Some central server to distribute program files 
3. (Hybrid) Have people opt into opening a port and serving the package files they have installed to other people (checksums and lists of all programs on a github repo)
4. (Our current system) Distribute build instructions and package lists on github and have people get them from the makers

