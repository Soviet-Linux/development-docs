# Live USB Creation instructions

This page will go into detail about creating a Live USB to use or install Soviet Linux. It is recommended that you carefully read this page before attempting to create a Live USB because the process is different from the usual, write the ISO on the USB with `dd`. It also includes a few notes that may be useful in debugging and locating problems in your Live USB.

## What you will need

- USB Drive (4GB recommended)
- The Soviet Linux ISO which can be downloaded from our [website](https://sovietlinux.ml/)
- A working Linux system

> **NOTE:** It is possible to create the Live USB on Windows but it is untested

### Note on the USB drive

The Live USB will not boot on a drive with a gpt label due to the limitations of the tool we've been using. We recommend that you change the label of your drive to dos and that the partition you create is set to be bootable. You can try to create a Live USB on a gpt disk, but you won't get any support.

## Formatting the USB drive

The first step in the process is to format your USB drive and create the appropriate file system. Because the precompiled kernel only includes this file system, ext4 is currently the only option.

> **WARNING:** Backup all important data from your USB drive since the next
> command will erase all content from your drive.

Run this command to format your drive and create the proper file system:

`mkfs.ext4 <*your device*>`

## Mounting the ISO and USB

Unlike other distributions, the `dd` command will not work to create the ISO. You must manually copy the files from the ISO to your hard drive.
To begin, mount the ISO using the following command:

`# mount soviet-linux.x86_64.iso /mnt/iso -o loop`

Then `cd` into the `/mnt/iso` directory.

> **NOTE:** You can choose any directory name under `/mnt` but remember to
> create one if it doesn't exist or else `mount` will return an error

Also mount your USB drive:

`# mount <*your device*> /mnt/usb`

> **NOTE:** You will need superuser permission to execute the `mount` command

## Copying the ISO

The next step is to copy all files from the ISO to the drive. Execute this command from the `/mnt/iso` directory.:

`cp -r * /mnt/usb`

## READ THE README IN THE DRIVE DIRECTORY

This is a **VERY** important step! Failure to read and follow the instructions in the `readme.txt` file will result in an error when attempting to boot from the Live USB, so do so!

## Conclusion

You are finished once you have completed all of the steps in this guide and in the `readme.txt` file. You can now restart your computer and boot into your newly created Live USB.

> **NOTE:** You will get a few errors on boot. Don't be alarmed, they can be
> safely ignored.

If you need assistance with the Live USB, please join our Discord and ask for help there, mentioning ComradeKrasMazov#5277 for good measure.

Enjoy Soviet Linux, comrade! Now you can say "Im a communist, BTW."
