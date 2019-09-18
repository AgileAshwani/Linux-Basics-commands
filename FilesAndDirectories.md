### Files and Directories

* Mount Points versus Drives in windows `mount /dev/da0p1 / [Drive zero partition 1, last '/' is used to mound to root]`. 
* Common File Sys commands
  * mkdir,mv[move[,cp[copy],du[disk usage],df[disk free],
  ```
  /bin Binaries
  /dev Devices
  /etc Configuration files
  /lib Shared library files
  /boot Boot files
  /home User home directories
  /mnt Temporary file system mounting
  /usr admin commands - unix sys resorces
  /var logs
  /sbin Admin commands
  /media Removable storage
  ```
* Find command
```
find . -name "filename.txt"
find / -user xyz
find / -cmin -5
find / -ctime -1
```

**LOGGING**
```
/var/log/messages: Contains general log messages
/var/log/boot: Contains system boot log messages
/var/log/debug: Contains debugging log messages
/var/log/auth.log: Contains user login and authentication logs messages
/var/log/daemon.log: Contains running services messages
/var/log/dmesg: Contains Linux kernel ring buffer log messages
/var/log/dpkg.log: Contains binary package log including package installation messages
/var/log/faillog: Contains failed login log messages
/var/log/kern.log: Contains kernel messages
/var/log/lpr.log: Contains printer messages
/var/log/mail.*: Contains mail server messages
/var/log/mysql.*: Contains MySQL server messages
/var/log/user.log: Contains userlevel logs messages
/var/log/xorg.0.log: Contains X.org messages
/var/log/apache2/*: Contains Apache Webserver messages
/var/log/lighttpd/*: Contains Lighttpd Webserver messages
/var/log/fsck/*: Contains fsck messages
/var/log/apport.log: Contains application crash report messages
```
