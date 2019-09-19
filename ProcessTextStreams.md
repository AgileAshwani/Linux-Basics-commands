### Process text streams

`cut -d: -f1 /etc/passwd` - to display only the first column of the passwd file, enter the following command:

`expand --tab=20 newfile.txt` - Now, you can use the expand command to alter the tab spaces.

`fmt -u newfile1.txt` - The fmt command is used to define uniform spacing between words and sentences. When used with the -u parameter, it formats the text with one space between words and two spaces between sentences.

`head -n5 /etc/yum.conf` - Let's use the -n parameter and display only the first five lines.

`head -n5 /etc/yum.conf /etc/passwd` - The display from multiple files marks the output from each file with a header naming the file.

`join -j2 rates.txt fruits.txt` - You will use the join command on both the files to display the joined output.
![image](https://user-images.githubusercontent.com/36263233/65147761-6e019080-da3c-11e9-88da-52d5835d8372.png)

 `nl a /etc/yum.conf` - You can number the lines of a file using the nl command. Using the a parameter, you can number all lines in a file.
 `od -t c fruits.txt` - Using the od command, you can view the file in different number formats, namely octal, hexadecimal, or any other. The -t parameter is used to specify the type of output. The c parameter displays the ASCII characters.
 
 `paste rates.txt fruits.txt` - Using the paste command, you can paste the output from multiple files into a vertical format. The -s parameter in the paste command enables you to re-orient the output of the command into a horizontal format rather than a vertical one.
 
 `pr -d /etc/yum.conf` - Using the pr command, you can convert a text file into a more appropriately formatted file with the headers, pagination, and column fills. With the -d parameter, you can add double space between lines.
 
 `cat yum.conf | tr a-z A-Z` - Note that, as specified in the command, all the lower case a to z characters are translated to upper case.
 
 `wc yum.conf` - The wc command helps you to count the lines, words, and characters of a file.

**Search Text Files using Regular Expressions**
`grep -n “old” /etc/yum.conf` - To find the word old in the /etc/yum.conf file. Notice the number 17 at the beginning of the display.
`grep -c “yum” /etc/yum.conf` - Instead of displaying the lines with the searched text, you can simply count the number of lines in which the searched text appears.
`grep -c “y*” /etc/yum.conf` - Let’s try to find the number of words that start with y in the yum.conf file.
`grep -v “yum” /etc/yum.conf` - Let’s try to find the word “yum” in the yum.conf file that does not contain the yum word
`grep -n “^$” /etc/yum.conf` - To list all the blank lines with their line numbers.
`ls | egrep "yum” /etc/yum.conf` - In this command, the pipe | acts as OR command. This means that egrep will simply search a specific file, in this case, yum.conf, and list the occurrences that have yum in the name.
`egrep 'Fedora|yum' /etc/yum.conf` - To find two words simultaneously in a file.
`fgrep -c ‘yum' /etc/yum.conf` - Egrep and fgrep are equivalent to grep with -E and -F. Fgrep is similar to grep, but it does not process any regular expression meta-characters as being special characters.
`sed '/^#/ d ' yumtest.conf` [to delete all the commented lines in the yumtest.conf file, enter the following command] - Stream Editor. The sed tool is used for performing automatic non-interactive editing of files. You can use most of the regular expressions with this tool to locate the required text.
`sed '/^  / d' yumtest.conf` - To delete all the blank lines at the end of the file, enter the following command.
`sed -e '/^$/ d’  -e ‘s/Fedora/Linux/g'  yumtest.conf` - You can also combine more than one sed commands. To combine more than one sed command, you use the -e switch. Enter the following command to delete all the blank lines and replace Fedora with Linux.







