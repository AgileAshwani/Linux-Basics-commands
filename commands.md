### Simple Unix Command-line Walkthrough :runner:

`echo $SHELL` or `echo $0` To know which shell is installed

`echo c{a,b,d}` Run and see the magic :innocent:

`pwd` present working directory

`service name stop/start/status` - Service status

`echo $(date)` Shows system date

`ls` list current directory contents

`ls -la` list current directory contents in long format and show hidden files

`ls | grep a` will list all directories having character 'a' grep 'general regular expression' :yum:

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

