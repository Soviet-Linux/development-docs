The list of packages will be obtained from the Soviet-Linux/OUR repo using this method.

We are now using a technique in which we obtain packages directly from the source. This is comparable to how another distribution, Source Mage, operates.

There have been numerous various strategies proposed, including:

1. Using Torrents to distribute software (and github repo for torrent files and checksums)
1. Some sort of central server for distributing program files
1. (Hybrid) Allow individuals to choose whether or not to open a port and serve the package files they have installed to others (checksums and lists of all programs on a github repo)
1. (This is our current system.) Distribute build instructions and package lists on github and direct users to the creators.

Follow this example to create a package:
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
        "archive" : "<archive location>"
    }, 
    "install" : 
    [
        {
            "file" : "<a file in the build dir>" ,
            "destination" : "<where the file should be installed>" 
        },
        {
            "file" : "<antoher file in the build dir>" ,
            "destination" : "<where the file should be installed>"
        }
    ]
```
