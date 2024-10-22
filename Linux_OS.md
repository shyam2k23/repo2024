# OS
https://www.javatpoint.com/what-is-linux
Operating systems, the software that powers your computer(Hardware), rely on crucial elements known as 
	Kernal 
	The file system.
	
# File System
## Linux File System
It helps to arrange the file on the disk storage. It manages the file name, file size, creation date, and much more information about a file.	

Linux file system has a hierarchal file structure as it contains a root directory and its subdirectories. All other directories can be accessed from the root directory. 

### Directory Structure

1. / (root filesystem): It is the top-level filesystem directory. It must include every file needed to boot the Linux system before another filesystem is mounted. Every other filesystem is mounted on a well-defined and standard mount point because of the root filesystem directories after the system is started.
2. /boot: It includes the static kernel and bootloader configuration and executable files needed to start a Linux computer.
3. /bin: This directory includes user executable files.
4. /dev: It includes the device file for all hardware devices connected to the system. These aren't device drivers; instead, they are files that indicate all devices on the system and provide access to these devices.
5. /etc: It includes the local system configuration files for the host system.
6. /lib: It includes shared library files that are needed to start the system.
7. /home: The home directory storage is available for user files. All users have a subdirectory inside /home.
8. /mnt: It is a temporary mount point for basic filesystems that can be used at the time when the administrator is working or repairing a filesystem.
9. /media: A place for mounting external removable media devices like USB thumb drives that might be linked to the host.
10. /opt: It contains optional files like vendor supplied application programs that must be placed here.
11. /root: It's the home directory for a root user. Keep in mind that it's not the '/' (root) file system.
12. /tmp: It is a temporary directory used by the OS and several programs for storing temporary files. Also, users may temporarily store files here. Remember that files may be removed without prior notice at any time in this directory.
13. /sbin: These are system binary files. They are executables utilized for system administration.
14. /usr: They are read-only and shareable files, including executable libraries and binaries, man files, and several documentation types.
15. /var: Here, variable data files are saved. It can contain things such as MySQL, log files, other database files, email inboxes, web server data files, and much more.

- The default file system for Red Hat Enterprise Linux (RHEL) is XFS
- The Red Hat cluster file system is called the Global File System 2 (GFS2)

https://www.geeksforgeeks.org/linux-file-system/
https://www.javatpoint.com/linux-file-system
