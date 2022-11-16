# learn-LINUX-Admin

<!--
| Command| Description |Example |
|------|---------------|--------|
|      |               |        |
|      |               |        |
<details><summary>:penguin: </summary>
<p>

</p>
</details>

--->
## Install Ubuntu server 
https://ubuntu.com/tutorials/install-ubuntu-server#1-overview
<details><summary>:penguin: Overview</summary>
<p>
This guide will provide an overview of the installation from either a DVD or a USB flash drive

</p>
</details>

<details><summary>:penguin: Requirements </summary>
<p>
You’ll need to consider the following before starting the installation:

    Ensure you have at least 2GB of free storage space.
    Have access to either a DVD or a USB flash drive containing the version of Ubuntu Server you want to install.
    If you’re going to install Ubuntu Server alongside data you wish to keep, ensure you have a recent backup.

See the server guide pages for more specific details on hardware requirements. We also have several tutorials that explain how to create an Ubuntu DVD or USB flash drive.
</p>
</details>
<details><summary>:penguin: Boot from install media</summary>
<p>


To trigger the installation process, perform the following:

    Put the Ubuntu DVD into your DVD drive (or insert the USB stick or other install media).
    Restart your computer.

After a few moments, you should see messages like those shown below on the screen…

screenshot

Most computers will automatically boot from USB or DVD, though in some cases this is disabled to improve boot times. If you don’t see the boot message and the “Welcome” screen which should appear after it, you will need to set your computer to boot from the install media.
https://ubuntucommunity.s3.dualstack.us-east-2.amazonaws.com/original/2X/1/17ee449b2bd7c530d2f996215407fca5b722dcb2.png
There should be an on-screen message when the computer starts telling you what key to press for settings or a boot menu. Depending on the manufacturer, this could be Escape, F2,F10 or F12. Simply restart your computer and hold down this key until the boot menu appears, then select the drive with the Ubuntu install media.

If you are still having problems, check out the Ubuntu Community documentation on booting from CD/DVD.

</p>
</details>
<details><summary>:penguin: Choose your language</summary>
<p>
After the boot messages appear, a ‘Language’ menu will be displayed.
</p>
</details>
<details><summary>:penguin: Choose the correct keyboard layout</summary>
<p>
Before you need to type anything in, the installer will next display a menu asking you to select your keyboard layout and, if applicable, the variant.
If you don’t know which particular variant you want, just go with the default - when Ubuntu Server has been installed you can test and change your preferences more easily if necessary.
</p>
</details>

<details><summary>:penguin: Choose your install</summary>
<p>
Now we are ready to select what you want to install. There are three options in the menu:
The bottom two options are used for installing specific components of a Metal As A Service (MAAS) install. If you are installing MAAS, you should check out the MAAS documentation for more information on this! The rest of this tutorial assumes you select the first option, Install Ubuntu.
</p>
</details>
<details><summary>:penguin: Networking</summary>
<p>
The installer will automatically detect and try to configure any network connections via DHCP.
This is usually automatic and you will not have to enter anything on this screen, it is for information only.
</p>
</details>
<details><summary>:penguin: Configure storage</summary>
<p>
The next step is to configure storage. The recommended install is to have an entire disk or partition set aside for running Ubuntu. 
If you need to set up a more complicated system, the manual option will allow you to select and reorganise partitions on any connected drives.
</p>
</details>
<details><summary>:penguin: Select a device</summary>
<p>
This menu will allow you to select a disk from the ones detected on the system.
To help identification, the drives will be listed using their system ID. Use the arrow keys and enter to select the disk you wish to use.
</p>
</details>
<details><summary>:penguin: Confirm partitions</summary>
<p>
With the target drive selected, the installer will calculate what partitions to create and present this information…
If this isn’t what you expected to see (e.g., you have selected the wrong drive), you should use the arrow keys and enter to select Back from the options at the bottom of the screen. This will take you back to the previous menu where you can select a different drive.

It is also possible to manually change the partitions here, by selecting Edit Partitions. Obviously you should only select this if you are familiar with how partitions work.
When you are happy with the disk layout displayed, select Done to continue.
</p>
</details>
<details><summary>:penguin: Confirm changes</summary>
<p>
Before the installer makes any destructive changes, it will show this final confirmation step. Double check that everything looks good here and you aren’t about to reformat the wrong device!
</p>
</details>
<details><summary>:penguin: Set up a Profile</summary>
<p>
The software is now being installed on the disk, but there is some more information the installer needs. Ubuntu Server needs to have at least one known user for the system, and a hostname. The user also needs a password.
</p>
</details>
<details><summary>:penguin: Install software</summary>
<p>
Once you have finished entering the required information, the screen will now show the progress of the installer. Ubuntu Server now installs a concise set of useful software required for servers. This cuts down on the install and setup time dramatically. Of course, after the install is finished, you can install any additional software you may need.
</p>
</details>

<details><summary>:penguin: Installation complete</summary>
<p>
When the install is complete, you will see a message like this on the screen.
Remember to remove the install media, and then press enter to reboot and start the server. Welcome to Ubuntu!
</p>
</details>
<details><summary>:penguin: What next?</summary>
<p>


With Ubuntu Server installed, you can now carry on and build that file-server or multi-node cluster we mentioned!

If you are new to Ubuntu Server, we’d recommend reading the Server Guide.

You can also check out the latest on Ubuntu Server, and what others are using it for on the Ubuntu Server pages.
Finding help

The Ubuntu community, for both desktop and server, is one of the friendliest and most well populated you can find. That means if you get stuck, someone has probably already seen and solved the same problem.

Try asking for help in one of the following places:

    Ask Ubuntu
    Ubuntu Forums
    IRC-based support

Alternatively, if you need commercial support for your server deployments, take a look at Ubuntu Advantage.

</p>
</details>


## User management

| Command| Description |Example |
|------|---------------|--------|
|     useradd|     The useradd command creates a new user account using the values specified on the command line plus the default values from the system. User names and user id are stored in /etc/passwd file.  User's passwords are stored in /etc/shadow file in an encrypted form.   |    # useradd -G admin,dba USERNAME    |  
|     usermod|     The usermod command modifies the system account files to reflect the changes that are specified on the command line          |  # usermod -G admin tri      |  
|     userdel|       The userdel command modifies the system account files, deleting all entries that refer to the user name USERNAME. The named user must exist        |    # userdel USERNAME    |
|     passwd|       The passwd utility is used to update user's authentication token(s).You can lock, unlock, assign passwords using passwd utility for any system user        |    # passwd USERNAME    |  
|  groupadd   |       The groupadd command creates a new group account using the values specified on the command line plus the default values from the system. The new group will be entered into the system files as needed        |    # groupadd GROUPNAME    |
| groupdel    |       The groupdel command modifies the system account files, deleting all entries that refer to GROUPNAME. The named group must exist.        |     # groupdel GROUPNAME   |  
|  groupmod   |      The groupmod command modifies the definition of the specified GROUP by modifying the appropriate entry in the group database.         |    # groupmod -n administrator admin    |
| sudo    |       sudo allows a permitted user to execute a command as the superuser or another user, as specified by the security policy. Observe the $ sign in the beginning of the shell, it donates a normal user shell. A root user's shell will have hash (#) So in this example a normal user is performing network restart using sudo privilege.   /etc/sudoers is the configuration file for sudoers to configure the normal user as privileged user.    |   $ sudo systemctl network restart    |


##  File Management
| Command| Description |Example |
|------|---------------|--------|
|  ls    |  list directory contents.See the manual for the switch             |   # ls -altri     |
|  cat    |      Concatenate FILE(s) to standard output.         |    # cat FILENAME    |
|  less    |     The less command is used to display text files on the screen one page at a time. For example, to show the first page in the text file var/log/dmesg that contains the text ‘cpu_-capacity’ we could use the command as follows;         |   less +/"cpu_capacity" /var/log/dmesg     |
|  more    |     The more command is a used to display text files one page at a time and as such it can be considered a member of the family of ‘pagers’.  For example, if we set the number of lines for the screen to 3 using the -num option as follows;        |   more -3 /var/log/dmesg     |
|   tail   |      The tail command is designed to print the last part of a file to the screen. By default it will print out the last 10 lines. It is a very handy program for quickly checking out the end of a file. For example if we wanted to print out the last 50 characters of the file /var/log/dmesg we would use the following;        |    tail -c50 /var/log/dmesg    |
|  sort    |   Displays a File in OrderThe sort utility displays the contents of a file in order by lines            |  # sort FILENAME      |
|   uniq   |      The uniq (unique) utility displays a file, skipping adjacent duplicate lines; it does not change the original file.         |   # uniq FILENAME     |
|  cp    |     The cp (copy) utility makes a copy of a file          |   # cp SOURCE-FILE DESTINATION-FILE     |
|  grep    |       The grep utility searches through one or more files to see whether any contain a specified string of characters.   In this example we search for all the lines containing "ssh" in /etc/services file     |    # grep STRING FILENAME ,# grep ssh /etc/services   |
|  mkdir    |    Create directories           |    # mkdir DIR    |
|   touch   |       Create empty file        |    # touch FILE    |
|  pwd    |        present working directory       |     # pwd   |
|  cut    |     The cut command is used to ‘cut out’ sections of each line of a file or files          |    cut -f 3 cutme.txt    |

## Absolute and Relative Path Name Addressing

| Description |Example |
|---------------|--------|
|      Pathnames            |       /home/pi/foo.txt |
|          Absolute Path Name Addressing         |  /home/pi/foo.txt      |
|      Relative Path Name Addressing         |     ls ../raspberry/foo.txt   |
|              |      ls foo.txt  |
|        The ‘home’ short-cut      |    ls ~/foo.txt    |
|    Everything is a file in Linux          |        |

## Linux files and inodes

### Inode

Each file has an associated inode (index node). The inode is analogous to a database entry that describes a range of attributes of the file. These attributes include;
  • The unique inode number
  • Access Control List (ACL)
  • Extended attributes such as append only or immutability • Disk block location
  • Number of blocks
  • File access, change and modification time
  • File deletion time
  • File generation number
  • File size
  • File type
  • Group
  • Number of links
  • Owner
  • Permissions
  • Status flags

 ## Soft Links (aka symbolic links, aka symlinks)
A soft link can also be referred to as a symbolic link, but is probably more frequently called a ‘symlink’. A symlink has a file name and inode number that points to it’s own inode, but in the inode there is a path that redirects to another inode that in turn points to a data block.
## Hard Links
A hard link is one where more than one file name links to an inode.
## Links Compared
### Hard links

  • Will only link to a file (no directories)
  • Will not link to a file on a different hard drive / partition • Will link to a file even when it is moved
  • Links to an inode and a physical location on the disk

### Soft links (or symbolic links or symlinks)

  • Will link to directories or files
  • Will link to a file or directory on a different hard drive / partition
  • Links will remain if the original file is deleted
  • Links will not connect to the file if it is moved
  • Links connect via abstract (hence symbolic) conventions, not physical locations on the
disk. They have their own inode

