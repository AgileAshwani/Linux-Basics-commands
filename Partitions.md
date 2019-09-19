**Manage MBR Partition Tables**
```
Each hard disk contains one MBR partition. It is the first sector of the disk and is not large enough to hold more than four partitions. These partitions can be:
Primary
Extended
Logical
```
`parted /dev/sda u s p` - You can display the partition table using the parted command.
`fdisk -l /dev/sda` - You can also list the partitions using the fdisk.

**Maintain the Integrity of Filesystems**

`df` - To monitor the free space and disk size in 1K blocks. `df -h` - To monitor the free space and disk size in MBs.
`df -i` - To display the information on the inodes.
`df .` - To determine the partition for the current working directory.
`du` - To get the size of each directory.
`du -h Downloads` - To get the size of the directory in Kilobytes, Megabytes, or Gigabytes.
`ls -l $(which passwd)` - To view the SUID for the file passwd
`stat /bin/passwd` - The stat command also displays values like when last accessed, modified, or changed.

**Create and Change Hard and Symbolic Links**
```
There are two types of links that you can create to a source file:
Symbolic links: It is a pointer to the source file. The permissions that apply to the source file also apply to the symbolic link. It can point to a source file on the local or remote filesystem.
Hard links: It is another directory entry for the source file and carries the same properties, such as file permissions, of the source file. If you delete one file, the other file remains intact. A hard link must exist in the same local filesystem.
```

`ln -s testfile testlink` - The -s parameter creates a symbolic link rather than a hard link.
`ln testfile testlink` - Let's create a hard link. Enter the following command.

`dddd`

