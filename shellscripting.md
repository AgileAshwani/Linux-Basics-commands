[<<Chapter1](commands.md)

### Basic Shell Scripting

**Regular Expressions** *Metacharacters*

* Wildcards

So when it comes to wildcards, a `?` means 0 or 1 of the previous element, that is listed with the ?, that's required. `If we've got an expression of car?t, it means that the r is optional. We need either zero or one of the previous characters, and what's to the left or what's previous to the question mark is an r here. So cat and cart would match that regular expression.` Whereas a `*`, means 0 or more of the previous element is required. So the difference is it's not just 0 or 1, it could be 0 or more matching items. `If we've got the asterisk symbols, as we see in the next example, [agg*hh*] it means that it would match variations such as agh, as well as agghh. Essentially any numbers of gs or hs, because the asterisk symbol means zero or any number of the preceeding characters.` A `+` sign means one or more of the previous element is required. `In our next example, our regular express is ag+h+. And that would match the same type of thing as the previous example up above where we've got to have at least one g and h that need to be present, but there could be more.` A `.` will match a single character at that location. `So if we have an expression of c.t, that matches any three letter word that starts with c and ends with t, but has one character in the middle, so like cat or cut`.


In our next regular expression example, in square brackets we've got [chs]at, so we need to match any one of those, and outside of that, we have at. So that would match things like cat, hat, and sat. Finally, our last example is 123|321, and that means we're trying to match either one of those, either we match 123 or 321. Regular expressions can get much more complicated than the examples we're looking at here, but this is a good primer to get started with working with it.

* Anchors

There are also some anchors, for example, the `^` sign will match something at the beginning of a string. `Our next expression has a hat symbol or a caret symbol, C-A-R-E-T, and the word Once. And that means that we're trying to match any lines that begin with the word Once.` Whereas the `$` sign will matches something at the end of a string.

**Filtering and formatting commands**

* Grep - line filtering `ls -l|grep -E 'j.+s'[match items with letter''j, then any number of characters, then letter 's']` && 
  `grep "^[0-9]"* [begins with atleast one numeric digit]` && `grep -v "^[0-9]"* [shows lines that doesn;t begin with number]` && `grep nfs /etc/rc.conf [will return all lines having nfs string]` && `grep ^nfs /etc/rc.conf [will return all lines begins with nfs string]` && `grep ^[nN] /etc/rc.conf [return anything that starts with lower or upper N]` && `grep -v ^[nN] /etc/rc.conf [-v means inverse]` && `grep -i NFS /etc/rc.conf [ignore case]` &&
  
* awk - Programmatic filtering and string manipulation `ls -l|awk '{print $1}'[shows only the first coloumn e.g.permission coloumn from listing]` && `ls -l|awk '{print $9,"->",$3}'[shows filename which is coloumn 9 and owner name which is column 3, since coloumn 9 is the last colmn $NF could have been used instead]` && `awk '$1 >2000' invoices.txt > /bigSpenders.txt [return only entries in colmn 1 greater than 2000]` && `ls -l | awk '{print $1}[prints 1st colmn]` && `ls -l | awk '{print $1,$9}[prints 1st colmn & 9th]` && `ls -l | awk '{print $1,$NF}[prints same as previous $NF-highest numer colmn of output]` && 

**Background Process**

* find / > /allfiles.txt & - will dump all files in root to allfiles.txt...and process will run in background due to use of '&' @end. 'jobs' command will show all background running processed. 'jobs -r 1' will remove mentioned num job.

**CHMOD 777 meaning??? :confused:**

* There are two parts to the file control mechanism, namely Classes and Permissions. Classes determines who can access the file while the Permissions determines the kind of action the user can do to the file. `There are three Classes – Owner, Group, Others.` In short, `777-everyone has full permissions / 755 - owner has full permission and rest can only read/execute but can't modify'
```
0 – no permission
1 – execute
2 – write
3 – write and execute
4 – read
5 – read and execute
6 – read and write
7 – read, write, and execute
```

**Conditions**

```
if [-f /var/log/msg]
  then
    echo "/var/log/msg exists"
fi
```
```
if["$(whoami)" != 'root']; then
    echo "not root"
else
    echo "root"
fi
```

**Looping**

* For/While/Until
```
for file in $(ls);
do
  echo Filename: $file
done
```
```
while true
do
clear
echo
echo "MENU"
echo "1 - Continue"
echo "2 - Quit"
echo
echo "Enter Choice:"
read selection
echo
case $selection in
      2)clear;exit;;
esac
done
```



