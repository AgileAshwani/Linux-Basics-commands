### Process text streams

`cut -d: -f1 /etc/passwd` - to display only the first column of the passwd file, enter the following command:

`expand --tab=20 newfile.txt` - Now, you can use the expand command to alter the tab spaces.

`fmt -u newfile1.txt` - The fmt command is used to define uniform spacing between words and sentences. When used with the -u parameter, it formats the text with one space between words and two spaces between sentences.

`head -n5 /etc/yum.conf` - Let's use the -n parameter and display only the first five lines.

`head -n5 /etc/yum.conf /etc/passwd` - The display from multiple files marks the output from each file with a header naming the file.

`join -j2 rates.txt fruits.txt` - You will use the join command on both the files to display the joined output.
![image](https://user-images.githubusercontent.com/36263233/65147761-6e019080-da3c-11e9-88da-52d5835d8372.png)
