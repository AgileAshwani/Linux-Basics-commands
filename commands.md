### Simple Unix Command-line Walkthrough :runner:

`echo $SHELL` or `echo $0` To know which shell is installed

`yum` Yellowdog updater modified

`yum install/list/update/remove/info httpd` -

`yum deplist httpd` - dependency list

`yum install mc` - mc utility to browse RPM without extracting them

`top` - `top -d 5`[ -d delay in sec] The top command is similar to the ps command, but it provides a more detailed view of the process. The view is constantly updated. `top -bi -n 5` - You can run the top command in batch mode using the -b parameter. With the help of -n parameter, you can specify the number of processes that will run in batch mode. Furthermore, you can ignore the idle processes using the -i parameter.

`uptime` - To check the uptime of the system, number of logged in users, etc.,

`jobs` - You can also find active jobs by running the jobs command.

` nohup find -size -100K > files.txt ` [This command uses the find command to find files that are less than 100 KB in size and then log the results to files.txt.]- The nohup utility continues to run a program even after the user logs out. 

`ps -aux`- You can also view the processes that are owned by others and are in the user mode. You will need to use three parameters: -a, -u, and -x.

`ps -U root -u root -N` - To list every process except those running as root.

`ps -l` - To display detailed information, including priority of a process. `ps -l -u root` - You can also display the priority specified for a user. 

`nice -n +5 bash` `renice +2 -p 6293` ` ps -l -u root`
```
You can run a program with higher or lower priority. For example, for a program with a default priority 0, you can change the priority to either of the following:
Up to -1 to -19 where -19 is the highest priority
From 1 to +20 where +20 is the lowest priority
```


`kill 1 8641` - In your system, the process id for bash may be different. Replace 8641 with the relevant process id.
```
Note the use of “1” in the command above. It is one of the operators that you can use to terminate a process. Various ways of terminating a process include:
1 or SIGHUP hangup or disconnect the process
2 or SIGINT same as Ctrl+C interrupt
3 or SIGQUIT to quit the process
9 or SIGKILL kill the process through a kernel call
15 or SIGTERM terminate a process 'nicely'. This is the DEFAULT signal.
```
`pstree` - To view the process hierarchy. Child Process.

`free -m` - You can also view the current memory usage in megabytes.

`uname` - has several switches....can view arch, kernel etc

`yum list yum-utils` - check if package is installed

`repoquery --list httpd` - to query content of package. yum-utils should be installed

`rpm -q httpd` - q[details]-

`echo c{a,b,d}` Run and see the magic :innocent:

`pwd` present working directory

`service name stop/start/status` - Service status

`echo $(date)` Shows system date

`ls` list current directory contents

`ls -la` list current directory contents in long format and show hidden files

`ls | grep a` will list all directories having character 'a' grep 'general regular expression' :yum:

`ls [!Aa]*` -  let us list all files that don't start with an 'a' or an 'A', enter the following command.

`ls D[eo]*` - Notice that the output lists all the files that have names starting with “De” or “Do”.

`find / -user root -name “gnome*”` - you will find files starting with gnome for a user named admin. 

`find / -user root -type f` - To find a specific type of file for a user.

`find /var/spool -mtime +60` - To find files that were modified a number of days ago.

`find -mmin -60 -exec ls -l {} \;` - To find files that were modified in the last one hour and then get the detailed listing

`find -size 1M -exec ls -l {} \;` - To list all the files with size more than 1MB.

`man <some unix command>` Bring up the manual pages for a command. Type `q` to exit

`man ls` will show you what ls does and the possible flags you can pass

`cd` change directory

`cd somedir` will take you into the directory called "somedir" if it's a subdirectory of your `pwd`

`open .` Open the current directory in Finder

`rm filename` deletes filename

`mate` Special textmate command

`mate .` Open everything in the current directory with textmate

`mate somefile.txt` creates a new file called somefile.txt if it does not already exist, opens the file if it does already exist.

`whoami` show the active user's name

**Use the tar, cpio, and dd Commands**

`tar -cvjf test.tar.bz *.txt`
```
The switches used with the tar command:
c - to create the archive
v - to display the verbose output during archive creation
j - to compress the archive with bzip compression. You can use the ‘z’ switch to use gzip compression
f - to name the file that is being created
```


# Git Basics

#### Cloning a repo

`git clone http://github.com/username/reponame.git`

Will clone the directory into your `pwd`

`cd reponame` change directory into the repo you just cloned

`rails s` start the rails server

go to your browser and type http://localhost:3000 and you can view the app.

`mate .` to open all the app files and start editing

Assuming the repo you cloned already has initialized git you can start adding files that you want to commit.

#### Updating your local repo

`git pull` will pull in latest changes from the master branch

It's possible you get some error telling you that you have a conflict, meaning you edited the same file as someone else and they are not the same.

`git stash` will git rid of your local changes so you can pull from master

If you don't want to lose them, you'll have to work the conflict out.


### Committing Changes

When you have made some changes and you are ready to add them..

`git remote -v` show current git remotes

You should have a remote of the repo name that you cloned (if you are a collaborator)
If you don't you need to add that origin.

`git remote add origin git@github.com:username/reponame.git`

You may want to add a heroku origin if the team is using one

`git remote add production git@heroku.com:appname.git`

And if there is a staging app on heroku

`git remote add staging git@heroku.com:appname-staging.git`

It's important that not everyone is pushing to master. If we are all on our own branch our commits won't be conflicting with each other. We can merge any certain branch to master when necessary

`git branch nameofyourbranch` The name of your branch should describe what kind of changes you are making. In some scenarios you may just want to use your name. This command makes a new branch but you still have to switch to it.

`git checkout branchname` switch to a certain branch

`git add .` adds all the files that have been edited to git tracking, git now knows what you will be committing

you should run a quick `git status` to make sure everything has been added. If you delete files manually (without use `git rm filename`), git won't know it's gone. If this is the case you can just run

If there are certain files you changed but don't want committed you can run
`git reset filename`

`git commit -am "message describing your commit goes here"`

The -a means, commit all changes. It's not necessary if you used `git add .` but will fix the issue of you deleting files manually and not using `git rm filename`.

The "m" in the -am means you are passing a message, describing your commit, this is very important for seeing what was changed when and tracking down bugs later.

after you have ran `git commit -am "some message"` you need to run

`git push origin nameofyourbranch` this will push your changes up to git on the branch you specified

