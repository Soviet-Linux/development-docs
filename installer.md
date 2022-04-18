# revolution-installer
The installer of the Soviet-Linux operating system.

## Usage
you need to have [Git](https://git-scm.com/)
then clone the repo with this command:
```
git clone https://github.com/Soviet-Linux/revolution-installer
```
cd into it:
```
cd revolution-installer
```
Compile the program using make in the program's root directory
```
make 
```
then use the following command to execute it
```
./bin/revolution
```

To install in the system move the executable into `/bin` or `/usr/bin` if `/bin`
is a symlink.

## Functionality
To install the system, the installer will go through the following steps.:

1. Display the various keyboard layouts and prompt the user to select a valid keyboard layout.
2. Prompt the user for a hostname.
3. Display the available locales and prompt the user to select one.
4. Display available time zones and prompt the user for a valid one
5. Prompt the user for a root password
6. Prompt the user for a username and password. Allow also the user to set
user groups
7. Display available devices and prompt the user for a device where to install
GRUB
8. Prompt the user for a choice of cfdisk or fdisk, if user chooses cfdisk
display the devices available and prompt the user for one
9. Display and prompt the user for a device and a file system
10. Review the installation settings
11. Install the system:
12. Format and install filesystem
13. Mount the drives
14. Copy the system
15. Set the hostname
16. Set the locale
17. Set the timezone
18. Set the timezone
19. Set root password
20. Create the username and set groups
21. Create /etc/fstab
22. Install GRUB
23. Reboot

## TODO
- Add user creation
- Set root password
- Set keyboard layout
- Set hostname
- Set locale and timezone
- Install GRUB
- Recompile kernel
