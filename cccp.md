We'll be utilizing the [CCCP](https://github.com/Soviet-Linux/CCCP) package manager (CCCP Crafter of Controlled Packages).
This package manager can use .spm file to build source packages or a tar.gz archive with precompiled binaries.\
the spm files are in json format and are organised like this :\
```
{
    "name" : "<package name>",
    "type" : "<src,bin,local>",
    "version" : "<version>",
    "dependencies" : ["<a dependencie>","<other dependencie>"],
    "info" : 
    {
        "download" : "<download command>",
        "build" : "<build command>",
        "special" : "<special command>"
    },
    "locations" : ["<location>","<other location>"]
}
```
## File organization
The CCCP does all of its work in a directory defined by the constant MAIN_DIR in the main.cpp file.\
MAIN_DIR is usually "/var/cccp".\

Note: You may use the cccp to install packages on another system by changing the ROOT string to the path to the other system's "/" directory.\

Inside the MAIN_DIR there are :
  1.  PKG_DIR (ususally "/var/cccp/pkg/") The source package files (.spm) are stored here. 
  2.  DATA_DIR (usually "/var/cccp/data") where the .spm file of installed packages are kept ( more info about these file after) 
  3. SRC_DIR (usually "/var/cccp/src") where local package source files are kept
  4. BIN_DIR (usually "/var/cccp/bin") where the.tar.gz archive containing built binaries is kept
  5. WORK_DIR (usually "/var/cccp/bin") where all of the work will be done (for example, the source code will be downloaded and built in it) MAKE_DIR (WORK_DIR + "sources/") BUILD DIR (WORK DIR + "build/") is where Binaries are kept and tested at this location. .
## Options
  ### Special options 
  ```-d``` option is used if the first place (ex : ``` cccp -d --someting``` not ``` cccp --something -d ```)\
  ### Regular options
  1. ```--install``` The option is used to install a source package from the PKG_DIR directory.\
  1. ```--create``` This option is used to generate a binary package from a source package. The package will be saved in the BIN_DIR directory.\
  1. ```--binary``` The option is used to install a binary package (tar.gz format) from the BIN_DIR directory..\
  1. ```--remove``` optio  is used to remove an installed package. ( It has some bugs)\


See the [documentation](https://docs.sovietlinux.ml/repo) for information on how to create a package.
