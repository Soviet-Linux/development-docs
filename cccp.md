We'll be utilizing the [CCCP](https://github.com/Soviet-Linux/CCCP) package manager (CCCP Crafter of Controlled Packages).
This package manager can use .spm file to build source packages or a tar.gz archive with precompiled binaries.

## Executable organisation 
 The soviet packages manager is conposed of two parts : \
### libspm
  The libspm , a shared libray ( ```libspm.so ```) which contains all code necessary to manage package on a soviet system.  
  It contains the soviet namespace which itself contains  the package class , used to create package object , and to install them , and the soviet utilities , like  ```soviet::format ``` ,  ```soviet::exec ```.\
  It also includes an interface function , the  ```cccp() ``` function which accept an int parameter whcich will be converted to an enum to do stuff like installing and uninstalling packages . \
  If you xant more details bout this , go the  ```inlude/libspm.hpp ``` in the CCCP repo.
  

### the frontend

To transform a cli argument to a call to the  ```cccp() ``` function from the libspm we need a frontend. I wrote a simlpe c++ executable that does that in the CCCP repo , but it could be better , especially in languages like RUST.


## Options
  ### Special options 
  ```-d``` or ```--debug ``` - enable debug mode \
   ```-t ```or ```--test ``` - enable package testing
  ### Regular options
  1. ```-i``` or ```--install``` - Install a package from the repos!  \
  1. ```-p``` or ```--package``` - Install a package file!  \
  1. ```-r``` or ```--remove``` -  Uninstall a package!  \
  1. ```-l``` or ```--list```   -  List all packages!  \
  1. ```-c``` or ```--check``` -   Check if a package is installed!  \
  1. ```-h``` or ```--help```  -   Print an help message!  \
  1. ```-s``` or ```--sync```  -   Synchronize package file!  \
  1. ```-b``` or ```--binary``` - creates a binary package (.bin.spm.tar.gz format) \

## File organization
The CCCP does all of its work in a directory defined by the constant MAIN_DIR in the main.cpp file.\
MAIN_DIR is usually "/var/cccp".

Note: You may use the cccp to install packages on another system by changing the ROOT string to the path to the other system's "/" directory.

Inside the MAIN_DIR there are :\
    1.  DATA_DIR (usually ```/var/cccp/data```) where all the data used by the cccp is stored like the  ```all.json ``` or the  ```installed.json ``` ( more about thoses files later ).\
    2. SRC_DIR (usually ```/var/cccp/src```) where local package source files are kept\
    3. BIN_DIR (usually ```/var/cccp/bin```) where the.tar.gz archive containing built binaries is kept\
    4. WORK_DIR (usually ```/var/cccp/bin```) where all of the work will be done (for example, the source code will be downloaded and built in it) MAKE_DIR (```WORK_DIR + "sources/"```) BUILD DIR (```WORK DIR + "build/"```) is where Binaries are kept and tested at this location. .\
    5. SPM_DIR (usually  ```/var/cccp/spm ``` ) where  ```.spm ``` files of installed packages are kept.\
    
## Configuration

You can configure the cccp with the  config file , usually stored at  ```/etc/cccp.conf ``` .
In this file you can chnage the file path of the cccp :\
ex :  ```ROOT=/mnt/arch ``` to change the cccp root to  ```/mnt/arch ``` .
You can also specify package repos : 
ex :  ``` REPOS=http://localhost:8080 https://our.sovietlinux.ml ``` 

## ⚠️WARNING⚠️ This file is a work in progress ⚠️WARNING⚠️


To learn how to make a package see the [docs](https://docs.sovietlinux.ml/repo)
