We'll be utilizing the [CCCP](https://github.com/Soviet-Linux/CCCP) package manager (CCCP Crafter of Controlled Packages).
This package manager can use .spm file to build source packages or a tar.gz archive with precompiled binaries.
## File organization
The CCCP does all of its work in a directory defined by the constant MAIN_DIR in the main.cpp file.\
MAIN_DIR is usually "/var/cccp".

Note: You may use the cccp to install packages on another system by changing the ROOT string to the path to the other system's "/" directory.

Inside the MAIN_DIR there are :
  1.  PKG_DIR (usually ```/var/cccp/pkg/```) The source package files (```.spm```) are stored here. 
  2.  DATA_DIR (usually ```/var/cccp/data```) where the ```.spm``` file of installed packages are kept ( more info about these file after) 
  3. SRC_DIR (usually ```/var/cccp/src```) where local package source files are kept
  4. BIN_DIR (usually ```/var/cccp/bin```) where the.tar.gz archive containing built binaries is kept
  5. WORK_DIR (usually ```/var/cccp/bin```) where all of the work will be done (for example, the source code will be downloaded and built in it) MAKE_DIR (```WORK_DIR + "sources/"```) BUILD DIR (```WORK DIR + "build/"```) is where Binaries are kept and tested at this location. .
## Options
  ### Special options 
  ```-d``` or ```--debug ``` - enable debug mode \
  ### Regular options
  1. ```-i``` or ```--install``` - Install a package from the repos!  \
  1. ```-p``` or ```--package``` - Install a package file!  \
  1. ```-r``` or ```--remove``` -  Uninstall a package!  \
  1. ```-l``` or ```--list```   -  List all packages!  \
  1. ```-c``` or ```--check``` -   Check if a package is installed!  \
  1. ```-h``` or ```--help```  -   Print this help message!  \
  1. ```-s``` or ```--sync```  -   Synchronize package file!  \
  1. ```-b``` or ```--binary``` - install a binary package (.bin.spm.tar.gz format) \


To learn how to make a package see the [docs](https://docs.sovietlinux.ml/repo)
