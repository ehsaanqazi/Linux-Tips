# Linux Commands

| S. No | Name  | URL          | Usage                                                                                               |
| ----- | ----- | ------------ | --------------------------------------------------------------------------------------------------- |
| 1     | grep  | [🔗](#grep)  | search for expressions                                                                              |
| 2     | cat   | [🔗](#cat)   | reading data                                                                                        |
| 3     | cut   | [🔗](#cut)   | cutting out the selections                                                                          |
| 4     | sed   | [🔗](#sed)   | find, filtering and replacing text                                                                  |
| 5     | tee   | [🔗](#tee)   | reads from standard input and writes to both standard output and one or more files at the same time |
| 6     | head  | [🔗](#head)  | printing top part of files                                                                          |
| 7     | tail  | [🔗](#tail)  | printing last part of files                                                                         |
| 8     | find  | [🔗](#find)  | finding and replacing files                                                                         |
| 9     | curl  | [🔗](#curl)  | transfer data files                                                                                 |
| 10    | chmod | [🔗](#chmod) | used to change permission of files files                                                            |
| 11    | wc    | [🔗](#wc)    | used for counting lines and characters                                                              |
| 12    | wget  | [🔗](#wget)  | retrieve content files                                                                              |
| 13    | gzip  | [🔗](#gzip)  | used to compress files                                                                              |
| 14    | sudo  | [🔗](#sudo)  | grant permissions to user                                                                           |

1. #### **grep**

   - print any line containig the text

     `grep "hack" terminal.txt`

   * print any line containig the text in multiple files

     `grep "hack" terminal.txt terminal2.txt treminal3.txt`

   * print any line containing the text in the whole directory

     `grep "hack" *`

   * print whole words only

     `grep -w "hack" *`

   * ignoring case in grep searches

     `grep -i "admin" *`

   * search in subdirectories

     `grep -r "admin" *`

   * inverse search exlcluding lines

     `grep -v "admin" *`

   * showing the lines that match a string

     `grep -x "admin" *`

   * print the name of files that contain the words

     `grep -l "admin" *`

   * print total count of the matches

     `grep -c "admin" *`

   * printing 3 lines after the match

     `grep -A 3 "admin" *`

   * printing 3 lines before the match

     `grep -B 3 "admin" *`

   * printing 3 lines before and after the match

     `grep -C 3 "admin" *`

   * display lines number with the matches

     `grep -n -C 2 "admin" *`

   * set output to a fixed number of lines

     `grep -m2 "admin" *`

   * run grep with regular expression

     `grep -E "[0-9] terminal.txt"`

   * only show the matching part of the string

     `grep -o "admin" *`

     [Back to Top](#linux-commands)

2. #### **cat**

   - view single file

     `cat file.txt`

   - view multiple files

     `cat file1.txt file2.txt`

   * view file with line numbers

     `cat -n file.txt`

     `cat -b file.txt`

   * copy contents of one file into another

     `cat [file1.txt] > [file2.txt]`

   * supress empty lines in output

     `cat -s file.txt`

   - append contents of one file into another

     `cat file.txt >> file2.txt`

   * reverse order using tac

     `tac file.txt`

   - highlight the end of line

     `cat -E file.txt`

   - using -v, -E, -T together

     `cat -A file.txt`

   * open dashed file

     `cat -- _file.txt`

   * more text

     `cat file.txt | more`

   - merge the content of multiple files

     `cat file.txt file2.txt file3.txt > masterFile.txt`

   * display content of all files in folder

     `cat *.txt`

   - append existing file

     `cat >> file.txt`

   * create a file

     `cat >file`

   * insert new line while concatening

     `cat - file.txt file2.txt > newfile.txt`

   * creating new file by displaying end marked at the end

     `cat > file.txt <<EOF`

   - displaying tab characters

     `cat -eT file.txt`

     [Back to Top](#linux-commands)

3. #### **cut**

   - by using hyphen as a delimiter

     `cut -d- -f2 file.txt`

   - by using space as a delimiter

     `cut -d " " -f2 file.txt`

   - cut by byte

     `cut -b 1 file.txt`

     `cut -b 1-3 file.txt`

   - cut by character

     `cut -c 1,3 file.txt`

     `cut -c 1-3 file.txt`

   - cut by complement

     `cut --complement -c 1,2 file.txt`

     `cut --complement -c 1-3 file.txt`

   * select range of fields

     `cut -f 2- file.txt`

     [Back to Top](#linux-commands)

4. #### **sed**

   - replace the first text with the second patter

     `echo Ehsaan | sed 's/Ehsaan/Hacker'`

   - replace all the matched pattern

     `echo My name is Ehsaan and I am Ehsaan | sed 's/Ehsaan/Hacker/'g`

   * delete the lines that match the pattern

     `cat test.txt | sed '/cd/d'`

   * multiple sed commands

     `sed -e '/cd/d; /burp/d' file.txt`

   * run sed commands from a file

     `sed -f sed.txt file.txt`

   * apply the command on the specific line

     `sed '3s/Ehsaan/Hacker/'`

   - specify the command on the range of lines

     `sed '1,3/Red/Purple/'`

   - inserting text before the match

     `echo "Line 1" | sed 'i\Line 2'`

   - inserting text after the match

     `echo "Line 2" | sed 'a\Line 1'`

   - modify lines

     `sed '3c/This is new line' file.txt`

   - modify line by regex

     `sed /Apple is /c Line Updated' file.txt`

   - transformaiton of characters

     `sed 'y/abc/def/' file.txt`

   - printing the line numbers

     `sed '=' file.txt`

   - displaying line numbers by match

     `sed -n '/mango/=' file.txt`

   - replace the nth occurance

     `` sed 's/color/colour/1` file.txt ``

   - replace from nth occurance to all occurance

     `sed 's/color/colour/3/g' file.txt`

   - print only the replaced string

     `sed -n 's/apple/mango/p' file.txt`

   - print the replaced string twice

     `sed 's/Apple/mango/p' file.txt`

   - to delte particular line

     `sed '5d' file.txt`

   * to delte last line

     `sed '$d' file.txt`

   - delete from range

     `sed '3,6d' file.txt`

   - delete from nth line to last line

     `sed '12,$d' file.txt`

   - view entire file except give range

     `sed '20,35d' file.txt`

   - display lines in more than 1 range

     `sed -n -e '5,7p' -e '1,2p' file.txt`

   - replace characters by ignoring case senstive

     `sed 's/word/character/gi' file.txt`

   - remove multiple blank spaces with single space

     `sed 's/ */ /g' file.txt`

   * insert one blank after each line

     `sed G file.txt`

   - insert two blank lines

     `sed 'G;G' file.txt`

   - insert black line above every match

     `sed '/Apple/{x;p;x;};' file.txt`

   - insert blank line below evrey line

     `sed '/love/G' a.txt`

   * insert five spaces on the left of every line

     `sed '/^/ /' a.txt`

   * number each line of a file

     `sed = a.txt | sed 'N; s/^/ /; s/ *\(.\{4,\}\)\n/\1 /'`

   * number each file if it's not blank

     `sed '/./=' a.txt | sed '/./N; s/\n/ /'`

   * delete empty lines or those begin with #

     `sed -i '/^#/d;/^$/d' file.txt`

     [Back to Top](#linux-commands)

5. #### **tee**

   - write output of the file to the next file

     `cat file.txt | tee file2.txt`

   * append data to a file

     `echo "Hello" | tee -a file.txt`

   * the snap of working directory is store in file

     `ls ~/| tee pipe1.txt | grep ^b | tee pipe2.txt | sort -r`

   * write data to multiple files

     `echo "New Line" | tee file.txt file2.txt`

   * Hide the output

     `echo "new" | tee file.txt >/dev/null`

   * Ignoring interupts

     `command | tee -i file.txt`

     [Back to Top](#linux-commands)

6. #### **head**

   - displays top 10 lines of the file

     `head file.txt`

   * prints the number of lines

     `head -n 3 file.txt`

   * prints the num bytes

     `head -c 3 file.txt`

   * multiple fies
     `head -q file.txt file1.txt`

   * prints along with file name

     `head -v file.txt`

   * get three recently used files

     `ls -t | head -n 3`

   * get three recently used files by alphaetical order

     `ls -t | head -n 3 | sort`

     [Back to Top](#linux-commands)

7. #### **tail**

   - prints the last 10 lines

     `tail file.txt`

   - prints the number of lines

     `tail -n 3 file.txt`

   * prints the num bytes

     `tail -c 3 file.txt`

   * multiple fies
     `tail -q file.txt file1.txt`

   * prints along with file name

     `tail -v file.txt`

   * get three recently used files

     `ls -t | tail -n 3`

   * get three recently used files by alphaetical order

     `ls -t | tail -n 3 | sort`

   * will print form the nth line number to the end

     `tail +10 file.txt`

   * print from the last of file

     `tail -c -20 file.txt`

   * prints all data after skipping number

     `tail -c 50 file.txt`

     [Back to Top](#linux-commands)

8. #### **find**

   - prints the last 10 lines

     `tail file.txt`

   - Find all files whose name ends with ".xml"

     `find / -type f -name *.xml`

   - Find all files in the /home directory (recursive) whose name is "user.txt" (case insensitive)

     `find /home -type f -name user.txt`

   - Find all directories whose name contains the word "exploits"

     `find / -type d -name "exploits*"`

   - Find all files owned by the user "kittycat"

     `find / -type f -user kittycat`

   - Find all files that are exactly 150 bytes in size

     `find / -type f -size 150`

   - Find all files in the /home directory (recursive) with size less than 2 KiB’s and extension ".txt"

     `find /home -type f -size -2k -name *.txt`

   - Find all files that are exactly readable and writeable by the owner, and readable by everyone else (use octal format)

     `find / -type f -perm 644`

   - Find all files that are only readable by anyone (use octal format)

     `find / -type f -perm /44`

   - Find all files with write permission for the group "others", regardless of any other permissions, with extension ".sh" (use symbolic format)

     `find / -type f -perm -o=w -name "*.sh"`

   - Find all files in the /usr/bin directory (recursive) that are owned by root and have at least the SUID permission (use symbolic format)

     `find /usr/bin -type f -user root -perm -u=s`

   - Find all files that were not accessed in the last 10 days with extension ".png"

     `find / -type f -atime +10 -name "*.png"`

   - Find all files in the /usr/bin directory (recursive) that have been modified within the last 2 hours

     `find /usr/bin -type f -mmin -120`

   - Find files without displaying the error

     `find / -name flag.txt 2>/dev/null`

     [Back to Top](#linux-commands)

9. ### **curl**

   - basic usuage

     `curl ehsaanqazi.com`

   * urls having sequence

     `curl ehsaanqazi.com/[1-10].txt`

   * show http headers

     `curl -I --http2 https://ehsaanqazi.com`

   * check if a website supports http

     `curl -I --http2 -s https://linuxize.com/ | grep HTTP`

   - to show progress bar

     `curl -# -o index.html ehsaanqazi.com`

   - to hide the progress meter

     `curl --silent ehsaanqazi.com`

   * save file on the machine with a custom name

     `curl -o index.html ehsaanqazi.com`

   - save file on the machine with original name

     `curl -O ehsaanqazi.com`

   * follow a redirect

     `curl -L ehsaanqazi.com`

   - resume downloads

     `curl -C - -O ehsaanqazi.com`

   - limit rate

     `curl --limit-rate 1K -O ehsaanqazi.com`

   * send cookies

     `curl -b "language=en" ehsaanqazi.com`

   - download files from FTP server

     `curl -u admin:password -O https://ftp.ehsaanqazi.com`

   - upload a file to FTP server and if exists append it

     `curl -u admin:password -T -a hos.txt https://ftp.ehsaanqazi.com`

   - send url through proxy

     `curl --proxy http://127.0.0.1:8080 ehsaanqazi.com`

[Back to Top](#linux-commands)

10. ### chmod

    **u: User, meaning the owner of the file.**
    **g: Group, meaning members of the group the file belongs to.**
    **o: Others, meaning people not governed by the u and g permissions.**
    **a: All, meaning all of the above.**
    **- sign removes the permission**
    **+ sign adds the permission**
    **= sign set a permission and remove others**
    **r: read permission**
    **w: write permission**
    **x: execute permission**

- change the permission to read

  `chmod u+r file.txt`

  `chmod g+r file.txt`

  `chmod o+r file.txt`

  `chmod a+r file.txt`

- remove the permission to read

  `chmod u-r file.txt`

* change the permission to write

  `chmod u+w file.txt`

* remove the permission to write

  `chmod u-w file.txt`

* change the permission to execute

  `chmod u+x file.txt`

* remove the permission to execute

  `chmod u-x file.txt`

* add read permission to all txt files

  `chmod u+r *.txt`

[Back to Top](#linux-commands)

11. ### wc

- count new lines in a file

  `cat file.txt | wc -l`

* count words

  `cat file.txt | wc -w`

* count characters

  `cat file.txt | wc -c`

* count length of longest line

  `cat file.txt | wc -L`

* print counts at once

  `wc file.txt`

* pass multiple files

  `wc file.txt file2.txt`

[Back to Top](#linux-commands)

12. ### wget

- download a file

  `wget https://ehsaanqazi.com/file.txt`

* download files from a list of urls

  `wget -i https://ehsaanqazi.com/file.txt`

* download file in custom location

  `wget -P Desktop https://ehsaanqazi.com/file.txt`

* download file with limited speed

  `wget --limit-rate=50kb https://ehsaanqazi.com/file.txt`

* set custom number of retry attempts

  `wget -tries=10 https://ehsaanqazi.com/file.txt`

* download file with custom name

  `wget -O https://ehsaanqazi.com/file.txt script.txt`

* run wget in background

  `wget -b https://ehsaanqazi.com/file.txt`

* changing the user-agent header

  `wget --user-agent="Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/50.0" http://ehsaanqazi.com`

* download files from server having invalid certificate

  `wget --no-check-certificate https://ehsaanqazi.com`

* download files via ftp

  `wget --ftp-user=admin --ftp-password=admin ftp://ehsaanqazi.com/file.txt`

* continue interrupted downloads

  `wget -c https://ehsaanqazi.com/file.txt`

* download files in sequence

  `wget http://ehsaanqazi.com/file{1..20}.txt`

[Back to Top](#linux-commands)

13. ### gzip

- compress a file

  `gzip file.txt`

* compress multiple files

  `gzip file.txt app.txt script.py`

* compress a file and keep original one

  `gzip -k file.txt`

* display the license of a compressed file

  `gzip -L file.txt.gz`

* recursively compress every file in a folder

  `gzip -r videos`

* set the custom compression level

  `gzip -9 file.txt`

* display the reduction in percentage

  `gzip -v file.txt`

* de-compress the file

  `gzip -d file.txt.gz`

* keep the original while after decompression

  `gzip -dk file.txt.gz`

* decompress all files in a directory

  `gzip -r videos`

[Back to Top](#linux-commands)

14. ### sudo

- basic usuage

  `sudo ls`

* print the list of commmands granted and forbidden for the current user

  `sudo -l`

* display the version

  `sudo -V`

* increase the timestamp by 5 minutes

  `sudo -v`

* kill the temestamp

  `sudo -k`

* run command as different user

  `sudo -u ehsaan ls`

* execute previous command with sudo

  `sudo !!`

* execute command by history number as sudo

  `sudo !3`

[Back to Top](#linux-commands)
