The list of packages will be obtained from the Soviet-Linux/OUR repo using this method.

We are now using a technique in which we obtain packages directly from the source. This is comparable to how another distribution, Source Mage, operates.

There have been numerous various strategies proposed, including:

1. Using Torrents to distribute software (and github repo for torrent files and checksums)
1. Some sort of central server for distributing program files
1. (Hybrid) Allow individuals to choose whether or not to open a port and serve the package files they have installed to others (checksums and lists of all programs on a github repo)
1. (This is our current system.) Distribute build instructions and package lists on github and direct users to the creators.

# Package Creation :

[Spm-helper](https://github.com/Soviet-Linux/spm-helper) can be used to create a package. A simple tool for creating packages (Warning: the code is garbage; if you know [rust](https://www.rust-lang.org/), you can help improve it). \
you can download the tool from [HERE](https://github.com/Soviet-Linux/spm-helper) \
 or you can follow this example to create a package:
```
{
    "name" : "<package name>",
    "type" : "src",
    "version" : "<version>",
    "dependencies" : ["<a dependencie>","<other dependencie>"],
    "info" : 
    {
        "prepare" : "<prepare command>"
        "build" : "<build command>",
        "test" : "<test command>,
        "special" : "<special command>"
    },
    "locations" : ["<location>","<other location>"]
}
```
if its a source package leave the location empty

1. Name = The name of the package

1. Types :
    1. "src" is for source .

    1. "bin" is for binary packages created using --create option.



1. Version = The package version. 

1. Dependencies = Package dependencies, such as software required to build or download the package.

1. prepare = The command used to prepare the BUILD_DIR ($BUILD_ROOT)

1. Build = The command used to build the package. The target directory must be $BUILD_ROOT.
   
   (example: `make `)
1. test = the command used to test the build of the package ( You can leave it blank)

1. install = The command used to install the package into the BUILD_DIR ($BUILD_ROOT)
   (example: `make prefix=$BUILD_ROOT install`)

1. Special = If you need to run a command after the installation is complete. (This is not yet implemented.)

1. Locations =
When you install or build a package, CCCP automatically generates the location list. Leave it blank.
