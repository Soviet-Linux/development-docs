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
All the work,of the PM is done in a directory defined by the constant MAIN_DIR in the main.cpp file.\
This MAIN_DIR is usually "/var/cccp".\
Note : You can use the cccp to install packages to another system by changing the ROOT string to the path of the "/" dir of you other system. \
Inside the MAIN_DIR there are :
  - PKG_DIR (ususally "/var/cccp/pkg/") where .spm source package file are stored.
  - DATA_DIR (usually "/var/cccp/data") where the .spm file of instaled packages are stored ( more info about these file after) 
  - SRC_DIR (usually "/var/cccp/src") where source files for local packages are stored.
  - BIN_DIR (usually "/var/cccp/bin") where the .tar.gz archive containing  compiled binaries are stored.
  - WORK_DIR (usually "/var/cccp/bin") where all the work will be done (ex : the source are downloaded and compiled in MAKE_DIR (WORK_DIR + "sources/") , the binaries are stored and tested in BUILD_DIR (WORK_DIR + "build/").
## Options
  ### Special options 
  ```-d``` option is used if the first place (ex : ``` cccp -d --someting``` not ``` cccp --something -d ```)\
  ### Regular options
  ```--install``` option is used to install source package from PKG_DIR.\
  ```--create``` option is used to create a binry package from a source package. the package will be stored in BIN_DIR\
  ```--binary``` option is used to install a binary package ( tar.gz format) from BIN_DIR.\
  ```--remove``` optio  is used to remove an installed package. ( It has some bugs)\


See the [documentation](https://docs.sovietlinux.ml/repo) for information on how to create a package.
