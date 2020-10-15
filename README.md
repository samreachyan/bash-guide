<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## Table of Contents
  1. [Basic Operations](#1-basic-operations)  
    1.1. [File Operations](#11-file-operations)  
    1.2. [Text Operations](#12-text-operations)  
    1.3. [Directory Operations](#13-directory-operations)  
    1.4. [SSH, System Info & Network Operations](#14-ssh-system-info--network-operations)  
    1.5. [Process Monitoring Operations](#15-process-monitoring-operations)
  2. [Basic Shell Programming](#2-basic-shell-programming)  
    2.1. [Variables](#21-variables)  
    2.2. [Array](#22-array)  
    2.3. [String Substitution](#23-string-substitution)  
    2.4. [Functions](#24-functions)  
    2.5. [Conditionals](#25-conditionals)  
    2.6. [Loops](#26-loops)  
  3. [Tricks](#3-tricks)  
  4. [Debugging](#4-debugging)  
  

# 1. Basic Operations

### a. `export`
ប្រើសម្រាប់បង្ហាញ់អំពីមជ្ឈដ្ឋាន variable ក្នុងការដំឡើងកម្មវិធីអ្វីមួយឬ Configuration ណាមួយ។ ប្រសិនបើអ្នកចង់មើល variable ដែលបានប្រើនោះគ្រាន់តែប្រើ `echo $VARIABLE_NAME` ។
Displays all environment variables. If you want to get details of a specific variable, use `echo $VARIABLE_NAME`.  
```bash
export
```
ឧទាហរណ៍:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R
```
```bash
$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
whatis shows description for user commands, system calls, library functions, and others in manual pages
whatis សម្រាប់បង្ហាញព័ត៌មានបន្ថែមពី commands, ប្រព័ន្ធប្រតិបត្តិការណ៍, បណ្ណាល័យ មុខងារនិង ទំព័រទាក់ទង។
```bash
whatis something
```
ឧទាហរណ៍:
```bash
$ whatis bash
bash (1)             - GNU Bourne-Again SHell
```
```bash
$ whatis uname
uname (1)            - print system information
uname (2)            - get name and information about current kernel
```

### c. `whereis`
whereis searches for executables, source files, and manual pages using a database built by system automatically.
whereis សម្រាប់អនុវត្តស្វែងរកប្រភពឯកសារ និង ទំព័រ​ទាក់ទងដែលបានប្រើប្រាស់ដំឡើងនៅក្នុងប្រព័ន្ធ។
```bash
whereis name
```
ឧទាហរណ៍:
```bash
$ whereis php
/usr/bin/php
```

### d. `which`
which searches for executables in the directories specified by the environment variable PATH. This command will print the full path of the executable(s).
which សម្រាប់អនុវត្តស្វែងរកទីតាំងតាមមជ្ឈដ្ឋាន variable ស្ថិតនៅ។ វានឹងបង្ហាញគ្រប់ទីតាំងដែលពាក់ព័ន្ធការអនុវត្តខាងលើ។
```bash
which program_name 
```
ឧទាហរណ៍:
```bash
$ which php
/c/xampp/php/php
```

### e. clear
Clears content on window.
វាសម្រាប់សម្អាតអត្ថបទដែលមាននៅលើអេក្រង់បង្ហាញ window ឬ terminal។
## 1.1. File Operations
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
It can be used for the following purposes under UNIX or Linux.  
* Display text files on screen
* Copy text files  
* Combine text files  
* Create new text files  
វាឃើញប្រើច្រើនភាគច្រើននៅក្នុង UNIX ឬ Linux។
* សម្រាប់បង្ហាញ អក្សរ លើអេក្រង់
* សម្រាប់ចម្លងអត្ថបទឯកសារ
* សម្រាប់បញ្ចូលអត្ថបទឯកសារ
* សម្រាប់បង្កើតអត្ថបទឯកសារថ្មី

```bash
cat filename
cat file1 file2 
cat file1 file2 > newcombinedfile
cat < file1 > file2 #copy file1 to file2
```

### b. `chmod`
The chmod command stands for "change mode" and allows you to change the read, write, and execute permissions on your files and folders. For more information on this command check this [link](https://ss64.com/bash/chmod.html).
chmod ដែលមកពីពាក្យ "change mode" ដែលអនុញ្ញាតឱ្យអ្នកអាចប្តូរម៉ូដឯកសារ read write ឬ execute លើឯកសារនិងក្របផ្ទុកឯកសារ។ សម្រាប់ព័ត៌មានលម្អិតលោកអ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://ss64.com/bash/chmod.html) ។ 
```bash
chmod -options filename
```

### c. `chown`
The chown command stands for "change owner", and allows you to change the owner of a given file or folder, which can be a user and a group. Basic usage is simple forward first comes the user (owner), and then the group, delimited by a colon.
chown ដែលមកពីពាក្យ "change owner" ដែលអនុញ្ញាតឱ្យអ្នកអាចប្តូរម្ចាស់កម្មសិទ្ធិលើឯកសារឬក្របឯកសារណាមួយបាន ដែលត្រូវបានកំណត់ជា user ឬ group។ ការប្រើប្រាស់ភាគច្រើនគឺអនុញ្ញាតពី user មួយទៅ group មួយទៀតដើម្បីមានសិទ្ធិចូលមកប្រើប្រាស់ដែរ។ 
```bash
chown -options user:group filename
```

### d. `cp`
Copies a file from one location to other.  
សម្រាប់ចម្លងឯកសារពីកន្លែងមួយទៅកន្លែងណាមួយផ្សេងទៀត។
```bash
cp filename1 filename2
```
Where `filename1` is the source path to the file and `filename2` is the destination path to the file.
`filename1` ត្រូវតែជាទីតាំងរួមឈ្មោះឯកសារ និង `filename2` ជាទីតាំងរួមទាំងឈ្មោះឯកសារដែលលោកអ្នកចង់ចម្លងទៅ។
### e. `diff`
Compares files, and lists their differences. 
សម្រាប់ប្រៀបធៀបឯកសារ និង បង្ហាញបញ្ជីពីភាពខុសគ្នានៃឯកសារ។ 
```bash
diff filename1 filename2
```

### f. `file`
Determine file type.  
សម្រាប់កំណត់ប្រភេទឯកសារ។
```bash
file filename
```
ឧទាហរណ៍:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
Find files in directory.
សម្រាប់ស្វែងរកឯកសារនិងទីតាំងណាមួយ។
```bash
find directory options pattern
```
ឧទាហរណ៍:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gunzip`
Un-compresses files compressed by gzip.  
សម្រាប់ពន្លាឯកសារក្នុងបង្រួមឯកសារ gzip ។
```bash
gunzip filename
```

### i. `gzcat`
Lets you look at gzipped file without actually having to gunzip it.  
អនុញ្ញាតឱ្យអ្នកមើលឯកសារ gzipped ដោយមិនចាំបាច់មាន gunzip ។
```bash
gzcat filename
```

### j. `gzip`
Compresses files.  
សម្រាប់បង្រួមឯកសារ។
```bash
gzip filename
```

### k. `head`
Outputs the first 10 lines of file  
សម្រាប់បង្ហាញអត្ថបទ ១០ បន្ទាត់ដំបូងក្នុងឯកសារ។
```bash
head filename
```

### l. `lpq`
Check out the printer queue.  
ពិនិត្យមើលលទ្ធផលបង្ហាញជាជួរៗ។
```bash
lpq
```
ឧទាហរណ៍:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`
Print the file.  
សម្រាប់បង្ហាញឯកសារ។
```bash
lpr filename
```

### n. `lprm`
Remove something from the printer queue.  
សម្រាប់លុបអ្វីមួយពីលទ្ធផលបង្ហាញជាជួរនោះ។
```bash
lprm jobnumber
```

### o. `ls`
Lists your files. `ls` has many options: `-l` lists files in 'long format', which contains the exact size of the file, who owns the file, who has the right to look at it, and when it was last modified. `-a` lists all files, including hidden files. For more information on this command check this [link](https://ss64.com/bash/ls.html).  
សម្រាប់បង្ហាញឯកសារជាបញ្ជី។ `ls` មានជម្រើសជាច្រើន `-l` បង្ហាញព័ត៌មានឯកសារពី ទំហំ ម្ចាស់កម្មសិទ្ធិ និងថ្ងៃកំណែចុងក្រោយ។ `-a` សម្រាប់បង្ហាញបញ្ជីឯកសារ និងបង្ហាញឯកសារដែលមិនត្រូវបានបង្ហាញ។ សម្រាប់ព័ត៌មានលម្អិតលោកអ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://ss64.com/bash/ls.html) ។ 
```bash
ls option
```
ឧទាហរណ៍:
<pre>
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
</pre>

### p. `more`
Shows the first part of a file (move with space and type q to quit).  
សម្រាប់បង្ហាញផ្នែកដំបូងនៃឯកសារ (លោកអ្នកអាចរំកិលចុះក្រោមដោយប្រើ space ឬចុច q ដើម្បីបញ្ចប់)។
```bash
more filename
```

### q. `mv`
Moves a file from one location to other.  
សម្រាប់ផ្លាស់ប្តូរទីតាំងឯកសារទៅកន្លែងផ្សេងមួយទៀត។

```bash
mv filename1 filename2
```
Where `filename1` is the source path to the file and `filename2` is the destination path to the file.
`filename1` ត្រូវតែជាទីតាំងរួមឈ្មោះឯកសារ និង `filename2` ជាទីតាំងរួមទាំងឈ្មោះឯកសារដែលលោកអ្នកចង់ផ្លាស់ប្តូរទៅ។

Also it can be used for rename a file.
វាក៏អាចប្រើសម្រាប់កែឈ្មោះឯកសារផងដែរ។
```bash
mv old_name new_name
```

### r. `rm`
Removes a file. Using this command on a directory gives you an error.
លុបចេញឯកសារ។ ការប្រើប្រាស់ command នេះនៅលើថតឯកសារផ្តល់ឱ្យអ្នកនូវកំហុស។
`rm: directory: is a directory`
To remove a directory you have to pass `-r` which will remove the content of the directory recursively. Optionally you can use `-f` flag to force the deletion i.e. without any confirmations etc.
ដើម្បីលុបថតឯកសារអ្នកត្រូវប្រើ `-r` ដែលនឹងលុបអត្ថបទវិលជុំ។ ជម្រើសផ្សេងអ្នកអាចប្រើ `-f` សម្រាប់បង្ខំឱ្យលុបដោយគ្មានការបញ្ជាក់ណាមួយ។ 
```bash
rm filename
```

### s. `tail`
Outputs the last 10 lines of file. Use `-f` to output appended data as the file grows.  
សម្រាប់បង្ហាញ់លទ្ធផលនៃឯកសារចំនួន ១០ បន្ទាត់ចុងក្រោយ។ `-f` ដើម្បីបង្ហាញទិន្ន័យបន្ថែមនៅពេលឯកសារនោះ។
```bash
tail filename
```

### t. `touch`
Updates access and modification time stamps of your file. If it doesn't exists, it'll be created.
ធ្វើបច្ចុប្បន្នភាពការចូលដំណើរការនិងការផ្លាស់ប្តូរពេលវេលានៃឯកសាររបស់អ្នក។ ប្រសិនបើវាមិនមានជាន់ឈ្មោះឯកសារណាមួយទេ វានឹងត្រូវបានបង្កើតឡើង។
```bash
touch filename
```
ឧទាហរណ៍:
```bash
$ touch trick.md
```

## 1.2. Text Operations

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
awk is the most useful command for handling text files. It operates on an entire file line by line. By default it uses whitespace to separate the fields. The most common syntax for awk command is
awk គឺជាពាក្យបញ្ជា command ដែលមានប្រយោជន៍បំផុតសម្រាប់ដោះស្រាយឯកសារអត្ថបទ។ វាដំណើរការលើខ្សែឯកសារទាំងមូលតាមបន្ទាត់។ តាមលំនាំដើមវាប្រើចន្លោះទំនេរដើម្បីបំបែកវាល។ វាជាពាក្យសម្រាប់យបញ្ជា awk

```bash
awk '/search_pattern/ { action_to_take_if_pattern_matches; }' file_to_parse
```

Lets take following file `/etc/passwd`. Here's the sample data that this file contains:
អ្នកអាចយកគំរូឯកសារ `/etc/passwd`. នេះជាទិន្នន័យគំរូដែលឯកសារនេះមាន៖

```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
So now lets get only username from this file. Where `-F` specifies that on which base we are going to separate the fields. In our case it's `:`. `{ print $1 }` means print out the first matching field.
ឥឡូវយើងសាកយកតែ username ពីឯកសារមួយនេះ។ `-F` សម្រាប់បំបែកតំបន់។ ក្នុងករណីនេះ `:`. `{ print $1 }` សម្រាប់បង្ហាញការផ្ទៀងផ្ទាត់តំបន់ដំបូង។
```bash
awk -F':' '{ print $1 }' /etc/passwd
```
After running the above command you will get following output.
បន្ទាប់ពីបានដំណើរការការបញ្ជាខាងលើអ្នកនឹងទទួលបានលទ្ធផលដូចខាងក្រោម។
```
root
daemon
bin
sys
sync
```
For more detail on how to use `awk`, check following [link](https://www.cyberciti.biz/faq/bash-scripting-using-awk).
សម្រាប់ព័ត៌មានលម្អិតការប្រើប្រាស់ `awk` អ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://www.cyberciti.biz/faq/bash-scripting-using-awk) ។ 

### b. `cut`
Remove sections from each line of files.
ការលុបផ្នែកណាមួយក្នុងឯកសារ។

*example.txt*
```bash
red riding hood went to the park to play
```

*show me columns 2 , 7 , and 9 with a space as a separator*
*ដើម្បីបង្ហាញជួរឈរទី២ ៧ និង ៩ ដែលមានដកឃ្លាទុក*
```bash
cut -d " " -f2,7,9 example.txt
```
```bash
riding park play
```

### c. `echo`
Display a line of text
បង្ហាញអត្ថបទមួយបន្ទាត់

*បង្ហាញ "Hello World"*
```bash
echo Hello World
```
```bash
Hello World
```

*display "Hello World" with newlines between words*
*បង្ហាញ "Hello World" ចុះបន្ទាត់ថ្មីក្នុងមួយពាក្យ*
```bash
echo -ne "Hello\nWorld\n"
```
```bash
Hello
World
```

### d. `egrep`
Print lines matching a pattern - Extended Expression (alias for: 'grep -E')
បង្ហាញអត្ថបទបន្ទាត់ដែលតាមលំនាំ - ការមតិបន្ថែម (alias 'grep -E')

*example.txt*
```bash
Lorem ipsum
dolor sit amet, 
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*display lines that have either "Lorem" or "dolor" in them.*
*បង្ហាញអត្ថបទបន្ទាត់ដែលមានពាក្យ "Lorem" ឬ "dolor" ក្នុងឯកសារ*
```bash
egrep '(Lorem|dolor)' example.txt
or
grep -E '(Lorem|dolor)' example.txt
```
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`
Print lines matching a pattern - FIXED pattern matching  (alias for: 'grep -F')
បង្ហាញអត្ថបទបន្ទាត់ដែលតាមលំនាំ - ការផ្គូផ្គងលំនាំ FIXED (alias 'grep -F')

*example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor) 
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Find the exact string '(Lorem|dolor)' in example.txt*
*ស្វែងរកអក្សរ '(Lorem|dolor)' ក្នុងឯកសារ example.txt*
```bash
fgrep '(Lorem|dolor)' example.txt
or
grep -F '(Lorem|dolor)' example.txt
```
```bash
foo (Lorem|dolor) 
```

### f. `fmt`
Simple optimal text formatter
ទម្រង់អក្សរមានលំដាប់

*ឧទាហរណ៍: example.txt (1 line)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*output the lines of example.txt to 20 character width*
*បង្ហាញអត្ថបទបន្ទាត់ដែលមាន ២០ពាក្យ ក្នុងឯកសារ example*
```bash
cat example.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`
Looks for text inside files. You can use grep to search for lines of text that match one or many regular expressions, and outputs only the matching lines.
ស្វែងរកពាក្យក្នុងអត្ថបទឯកសារមួយ អ្នកអាចប្រើប្រាស់ grep ដើម្បីស្វែងរកវានឹងបង្ហាញលទ្ធផលជាជួរ។
```bash
grep pattern filename
```
ឧទាហរណ៍:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
You can also force grep to ignore word case by using `-i` option. `-r` can be used to search all files under the specified directory, for example:
អ្នកអាចប្រើការស្វែងរកឯកសារដោយបង្ខំការរុករកប្រើប្រាស់ `-i`។ ចំណែក `-r` វាអាចស្វែងរកគ្រប់ឯកសារទាំងអស់ដែលស្ថិតនៅក្នុងថតឯកសារដែលអ្នកបានកំណត់។ ឧទាហរណ៍៖ 
```bash
$ grep -r admin /etc/
```
And `-w` to search for words only. For more detail on `grep`, check following [link](https://www.cyberciti.biz/faq/grep-in-bash).
ចំណែក `-w` សម្រាប់ស្វែករកតែពាក្យប៉ុណ្ណោះ។ សម្រាប់ព័ត៌មានលម្អិតការប្រើប្រាស់ `grep` អ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://www.cyberciti.biz/faq/grep-in-bash) ។ 
### h. `nl`
Number lines of files
ជាចំនួនបន្ទាត់អត្ថបទក្នុងឯកសារមួយ។

*example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*show example.txt with line numbers*
*ដើម្បីបង្ហាញចំនួនលេខបន្ទាត់អត្ថបទក្នុង example.txt *
```bash
nl -s". " example.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
Stream editor for filtering and transforming text
កំណែទម្រង់អត្ថបទដោយផ្ទាល់សម្រាប់ការបំលែងអត្ថបទ

*example.txt*
```bash
Hello This is a Test 1 2 3 4
``` 

*replace all spaces with hyphens*
*ជំនួសគ្រប់ ដកឃ្លា(space) ជាមួយសហាសញ្ញា(-)*
```bash
sed 's/ /-/g' example.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*replace all digits with "d"*
*ជំនួសគ្រប់លេខទាំងអស់ដោយអក្សរ "d"*
```bash
sed 's/[0-9]/d/g' example.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
Sort lines of text files
តម្រៀបលំដាប់អត្ថបទអក្សរជាបន្ទាត់

*example.txt*
```bash
f
b
c
g
a
e
d
```

*sort example.txt*
```bash
sort example.txt
```
```bash
a
b
c
d
e
f
g
```

*randomize a sorted example.txt*
*តម្រៀបលំដាប់អត្ថបទអក្សរដោយចៃដន្យក្នុងឯកសារ example.txt*
```bash
sort example.txt | sort -R
```
```bash
b
f
a
c
d
g
e
```

### k. `tr`
Translate or delete characters
បំលែងឬលុបអក្សរ

*example.txt*
```bash
Hello World Foo Bar Baz!
```

*take all lower case letters and make them upper case*
*បំលែងគ្រប់អក្សរតូចទាំងអស់ទៅជាអក្សរធំ*
```bash
cat example.txt | tr 'a-z' 'A-Z' 
```
```bash
HELLO WORLD FOO BAR BAZ!
```

*take all spaces and make them into newlines*
*បំលែងដកឃ្លាទាំងអស់ទៅជាចុះបន្ទាត់ថ្មី*
```bash
cat example.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
Report or omit repeated lines
រាយការណ៍ឬលុបចោលជួរមានអក្សរដដែលៗ

*example.txt*
```bash
a
a
b
a
b
c
d
c
```

*show only unique lines of example.txt (first you need to sort it, otherwise it won't see the overlap)*
*បង្ហាញអត្ថបទដែលមានតែមួយនៃ example.txt (ដំបូងអ្នកត្រូវតែតម្រៀបតាមលំដាប់ជាមុនសិន បើមិនដូច្នោះវាមិនអាចបង្ហាញអត្ថបទមានតែមួយនោះទេ)*
```bash
sort example.txt | uniq
```
```bash
a
b
c
d
```

*show the unique items for each line, and tell me how many instances it found*
*បង្ហាញអត្ថបទនៃបន្ទាត់និមួយៗ និងចំនួនដែលបានរកឃើញក្នុងជួរបន្ទាត់ជាមួយគ្នា*
```bash
sort example.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
Tells you how many lines, words and characters there are in a file.  
បង្ហាញប្រាប់អ្នកចំនួនបន្ទាត់ ពាក្យ និងពញ្ជនៈដែលមានក្នុងឯកសារ។
```bash
wc filename
```
Example:
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```
Where `7459` is lines, `15915` is words and `398400` is characters.
`7459` ចំនួនបន្ទាត់ `15915` ចំនួនពាក្យ និង `398400` ពញ្ជនៈ។

## 1.3. Directory Operations

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
Moves you from one directory to other. Running this  
អ្នកអាចផ្លាស់ទីពីទីតាំងមួយទៅទីតំាងផ្សេងទៀតដោយប្រើ 
```bash
$ cd
```
moves you to home directory. This command accepts an optional `dirname`, which moves you to that directory.
ផ្លាស់ទីអ្នកពីទីតាំងដើមទៅទីតាំង `dirname` ជាទីតាំងអ្នកប្តូរទៅ
```bash
cd dirname
```

### b. `mkdir`
Makes a new directory.  
បង្កើតថតឯកសារថ្មី
```bash
mkdir dirname
```
You can use this to create multiple directories at once within your current directory.
អ្នកអាចបង្កើតថតឯកសារថ្មីច្រើនក្នុងការបញ្ជាតែម្តងក្នុងថតដែលអ្នកស្ថិតនៅ
```bash
mkdir 1stDirectory 2ndDirectory 3rdDirectory
```
You can also use this to create parent directories at the same time. For instance, if you wanted a directory named 'project1' in another subdirectory at '/samples/bash/projects/', you could run:
អ្នកអាចបង្កើតថតឯកសារថ្មីទៅលើថតឯកសារដែលអ្នកមិនស្ថិតនៅ។ ឧទាហរណ៍អ្នកចង់បង្កើតថតឯកសារ 'project1' ក្នុង '/samples/bash/projects/' ដែលអ្នកបានស្ថិតនៅកន្លែងនោះ៖
```bash 
mkdir /samples/bash/projects/project1
```
If any of these directories did no already exist, they would be created as well.
ប្រើថតដែលអ្នកបង្កើតនោះមិនជាន់ឈ្មោះនោះទេ វានឹងបង្កើតថតឯកសារនោះឱ្យអ្នក
### c. `pwd`
Tells you which directory you currently are in.  
សម្រាប់ប្រាប់ទីតាំងបច្ចុប្បន្នដែលអ្នកស្ថិតនៅ។
```bash
pwd
```

## 1.4. SSH, System Info & Network Operations

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>   
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
   </tr>
</table>

### a. `bg`
Lists stopped or background jobs; resume a stopped job in the background.
បញ្ជីការបញ្ឈប់ឬការងារដែលបានដំណើរការនៅខាងក្រោយ ការផ្អាក់ដំណើរការការងារបានដំណើរការនៅខាងក្រោយ។
### b. `cal`
Shows the month's calendar.
បង្ហាញប្រតិទិនរបស់ខែនេះ

### c. `date`
Shows the current date and time.
បង្ហាញថ្ងៃខែ និងម៉ោងបច្ចុប្បន្ន
### d. `df`
Shows disk usage.
បង្ហាញទិន្នន័យការប្រើប្រាស់ ឌីស

### e. `dig`
Gets DNS information for domain.  
បង្ហាញព័ត៌មានឈ្មោះ DNS
```bash
dig domain
```

### f. `du`
Shows the disk usage of files or directories. For more information on this command check this [link](http://www.linfo.org/du.html)
បង្ហាញទិន្នន័យការប្រើប្រាស់ឌីសនៃឯកសារឬថតសារ។ សម្រាប់ព័ត៌មានលម្អិតការប្រើប្រាស់ អ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](http://www.linfo.org/du.html) ។ 
```bash
du [option] [filename|directory]
```
Options:
ជម្រើសបន្ថែម៖
- `-h` (human readable) បង្ហាញលទ្ធផលគិតជា គីឡូបៃត៍ (kilobytes - K) មេហ្គាបៃខ្នាត (Megabytes - M) និង ជីហ្គាបៃខ្នាត (Gigabytes - G)
- `-s` (supress or summarize) បង្ហាញទិន្នន័យសរុបឌីសនៃថតឯកសារ និង របាយការណ៍សម្រាប់ថតរង

ឧទាហរណ៍៖
```bash
du -sh pictures
1.4M pictures
```

### g. `fg`
Brings the most recent job in the foreground.
នាំមកនូវការងារថ្មីៗមកនៅផ្ទៃខាងមុខ។

### h. `finger`
Displays information about user.  
បង្ហាញព័ត៌មានអំពីអ្នកប្រើប្រាស់ user ។
```bash
finger username
```
### i. `jobs`
Lists the jobs running in the background, giving the job number.
បង្ហាញបញ្ជីការងារនិងចំនួនដែលកំពុងដំណើរនៅខាងក្រោយ។

### j. `last`
Lists your last logins of specified user.  
បង្ហាញទិន្នន័យចំនួនបានចូលប្រើប្រាស់របស់អ្នកប្រើប្រាស់ user
```bash
last yourUsername
```

### k. `man`
Shows the manual for specified command.  
បង្ហាញសៀវភៅណែនាំសម្រាប់ពាក្យបញ្ជាដែលបានបញ្ជាក់។
```bash
man command
```

### l. `passwd`
Allows the current logged user to change their password.
អនុញ្ញាតឱ្យអ្នកកំពុងប្រើប្រាស់អាចប្តូរលេខសម្ងាត់
### m. `ping`
Pings host and outputs results.  
Ping host និងបង្ហាញលទ្ធផល
```bash
ping host
```

### n. `ps`
Lists your processes.  
បង្ហាញកម្មវិធីកំពុងដំណើរការ
```bash
ps -u yourusername
```
Use the flags ef. e for every process and f for full listing. 
បង្ហាញព័ត៌មានលម្អិតពីបញ្ជីនិមួយៗដែលប្រើប្រាស់ flag
```bash
ps -ef
```

### o. `quota`
Shows what your disk quota is.  
បង្ហាញូតាឌីសរបស់អ្នក
```bash
quota -v
```

### p. `scp`
Transfer files between a local host and a remote host or between two remote hosts.
ផ្ទេរឯកសាររវាងម៉ាស៊ីនប្រើប្រាស់និងម៉ាស៊ីនបញ្ជាចម្ងាយឬរវាងម៉ាស៊ីនពីបញ្ជាពីចម្ងាយពីរ។ 

*copy from local host to remote host*
*ចម្លងពីម៉ាស៊ីនប្រើប្រាស់ទៅម៉ាស៊ីនបញ្ជាពីចម្ងាយ*
```bash
scp source_file user@host:directory/target_file
```
*copy from remote host to local host* /
*ចម្លងពីម៉ាស៊ីនបញ្ជាពីចម្ងាយមកមា៉ស៊ីនប្រើប្រាស់*
```bash
scp user@host:directory/source_file target_file
scp -r user@host:directory/source_folder target_folder
```
This command also accepts an option `-P` that can be used to connect to specific port.  
ការបញ្ជានេះមានជម្រើសបន្ថែម `-P` ដែលអាចប្រើប្រាស់សម្រាប់ភ្ជាប់ប្រើប្រាស់ Port ណាមួយបាន

```bash
scp -P port user@host:directory/source_file target_file
```

### q. `ssh`
ssh (SSH client) is a program for logging into and executing commands on a remote machine.  
shh (SSH client) គឺជាកម្មវិធីមួយសម្រាប់ចូលប្រើប្រាស់និងដំណើរការការបញ្ជាទៅកាន់ម៉ាស៊ីនបញ្ជាពីចម្ងាយ។

```bash
ssh user@host
```

This command also accepts an option `-p` that can be used to connect to specific port.  
ការបញ្ជានេះមានជម្រើសបន្ថែម `-p` ដែលអាចប្រើប្រាស់សម្រាប់ភ្ជាប់ប្រើប្រាស់ Port ណាមួយបាន

```bash
ssh -p port user@host
```

### r. `top`
Displays your currently active processes.
បង្ហាញពីដំណើរការបច្ចុប្បន្នរបស់អ្នក

### s. `uname`
Shows kernel information.  
បង្ហាញពីព័ត៌មាន kernel 
```bash
uname -a
```

### t. `uptime`
Shows current uptime.
បង្ហាញពីពេលវេលាបច្ចុប្បន្នប្រើប្រាស់កុំព្យូទ័រ

### u. `w`
Displays who is online.
បង្ហាញនរណាដែលអាចចូលប្រើប្រាស់បាន

### v. `wget`
Downloads file. 
សម្រាប់ទាញយកឯកសារ 
```bash
wget file
```

### w. `whoami`
Return current logged in username.
បង្ហាញពីឈ្មោះអ្នកដែលកំពុងប្រើប្រាស់បច្ចុប្បន្ន

### x. `whois`
Gets whois information for domain. 
បង្ហាញព័ត៌មានម្ចាស់ domain
```bash
whois domain
```

## 1.5. Process Monitoring Operations

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
Kills (ends) the processes with the ID you gave.  
បញ្ឈប់ការដំណើរការណាមួយដោយ ID
```bash
kill PID
```

### b. `killall`
Kill all processes with the name.  
បញ្ឈប់ការដំណើរការណាមួយដោយឈ្មោះ
```bash
killall processname
```

### c. &
The `&` symbol instructs the command to run as a background process in a subshell.
សញ្ញា `&` ជាការបញ្ជាបន្ថែមផ្សេងទៀត

```bash
command &
```

### d. `nohup`
nohup stands for "No Hang Up". This allows to run command/process or shell script that can continue running in the background after you log out from a shell.
nohup មកពីពាក្យ "No Hang Up" អនុញ្ញាតឱ្យអ្នកបញ្ជាឬដំណើរការ script ណាមួយដែលអ្នកបានកំណត់វានឹងដំណើរការរហូតទោះបីអ្នកបានចាកចេញក៏ដោយ។
```bash
nohup command
```
Combine it with `&` to create background processes 
ភ្ជាប់ការដំណើរការផ្សេងទៀតដោយសញ្ញា `&` ដើម្បីបង្កើតការដំណើរការខាងក្រោយ
```bash
nohup command &
```

# 2. Basic Shell Programming

The first line that you will write in bash script files is called `shebang`. This line in any script determines the script's ability to be executed like a standalone executable without typing sh, bash, python, php etc beforehand in the terminal.
បន្ទាត់ដំបូងដែលអ្នកនឹងត្រូវសរសេរជា script ត្រូវបានគេហៅថា `shebang` ។ បន្ទាត់ script នេះវាអាចមានសមត្ថភាពដំណើរ script ដោយមិនចំបាច់ប្រើប្រាស់ sh, bash, python, php etc នៅខាងដើមក្នុងផ្ទាំងពណ៌ខ្មៅដើម្បីធ្វើការបញ្ជាទៀតឡើយ។

```bash
#!/usr/bin/env bash
```

## 2.1. Variables

Creating variables in bash is similar to other languages. There are no data types. A variable in bash can contain a number, a character, a string of characters, etc. You have no need to declare a variable, just assigning a value to its reference will create it.
ការបង្កើតអថេរនៅក្នុង bash គឺស្រដៀងនឹងភាសាផ្សេងទៀត។ វាមិនមានប្រភេទទិន្នន័យទេ អថេរក្នុងប៊្លុកអាចមានលេខតួអក្សរ។ អ្នកមិនចាំបាច់ប្រកាសប្រភេទអថេរទេគ្រាន់តែផ្តល់តម្លៃទៅវា វានឹងបង្កើតដោយខ្លួនឯង។

ឧទាហរណ៍៖
```bash
str="hello world"
```

The above line creates a variable `str` and assigns "hello world" to it. The value of variable is retrieved by putting the `$` in the beginning of variable name.
ខាងលើនេះជាការបង្កើតអថេរ `str` ដែលមានតម្លៃ "hello world"។ ក្នុងការយកមកប្រើប្រាស់អ្នកគ្រាន់តែដាក់សញ្ញា `$` នៅខាងដើមអថេរជាការស្រេច។

ឧទាហរណ៍៖
```bash
echo $str   # hello world
```
## 2.2. Array
Like other languages bash has also arrays. An array is a variable containing multiple values. There's no maximum limit on the size of array. Arrays in bash are zero based. The first element is indexed with element 0. There are several ways for creating arrays in bash which are given below.

Examples:
```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```
To display a value at specific index use following syntax:

```bash
${array[i]}     # where i is the index
```

If no index is supplied, array element 0 is assumed. To find out how many values there are in the array use the following syntax:

```bash
${#array[@]}
```

Bash has also support for the ternary conditions. Check some examples below.

```bash
${varname:-word}    # if varname exists and isn't null, return its value; otherwise return word
${varname:=word}    # if varname exists and isn't null, return its value; otherwise set it word and then return its value
${varname:+word}    # if varname exists and isn't null, return word; otherwise return null
${varname:offset:length}    # performs substring expansion. It returns the substring of $varname starting at offset and up to length characters
```

## 2.3 String Substitution

Check some of the syntax on how to manipulate strings

```bash
${variable#pattern}         # if the pattern matches the beginning of the variable's value, delete the shortest part that matches and return the rest
${variable##pattern}        # if the pattern matches the beginning of the variable's value, delete the longest part that matches and return the rest
${variable%pattern}         # if the pattern matches the end of the variable's value, delete the shortest part that matches and return the rest
${variable%%pattern}        # if the pattern matches the end of the variable's value, delete the longest part that matches and return the rest
${variable/pattern/string}  # the longest match to pattern in variable is replaced by string. Only the first match is replaced
${variable//pattern/string} # the longest match to pattern in variable is replaced by string. All matches are replaced
${#varname}     # returns the length of the value of the variable as a character string
```

## 2.4. Functions
As in almost any programming language, you can use functions to group pieces of code in a more logical way or practice the divine art of recursion. Declaring a function is just a matter of writing function my_func { my_code }. Calling a function is just like calling another program, you just write its name.

```bash
function name() {
    shell commands
}
```

Example:
```bash
#!/bin/bash
function hello {
   echo world!
}
hello

function say {
    echo $1
}
say "hello world!"
```

When you run the above example the `hello` function will output "world!". The above two functions `hello` and `say` are identical. The main difference is function `say`. This function, prints the first argument it receives. Arguments, within functions, are treated in the same manner as arguments given to the script.

## 2.5. Conditionals

The conditional statement in bash is similar to other programming languages. Conditions have many form like the most basic form is `if` expression `then` statement where statement is only executed if expression is true.

```bash
if [ expression ]; then
    will execute only if expression is true
else
    will execute if expression is false
fi
```

Sometime if conditions becoming confusing so you can write the same condition using the `case statements`.

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Expression Examples:

```bash
statement1 && statement2  # both statements are true
statement1 || statement2  # at least one of the statements is true

str1=str2       # str1 matches str2
str1!=str2      # str1 does not match str2
str1<str2       # str1 is less than str2
str1>str2       # str1 is greater than str2
-n str1         # str1 is not null (has length greater than 0)
-z str1         # str1 is null (has length 0)

-a file         # file exists
-d file         # file exists and is a directory
-e file         # file exists; same -a
-f file         # file exists and is a regular file (i.e., not a directory or other special type of file)
-r file         # you have read permission
-s file         # file exists and is not empty
-w file         # you have write permission
-x file         # you have execute permission on file, or directory search permission if it is a directory
-N file         # file was modified since it was last read
-O file         # you own file
-G file         # file's group ID matches yours (or one of yours, if you are in multiple groups)

file1 -nt file2     # file1 is newer than file2
file1 -ot file2     # file1 is older than file2

-lt     # less than
-le     # less than or equal
-eq     # equal
-ge     # greater than or equal
-gt     # greater than
-ne     # not equal
```

## 2.6. Loops

There are three types of loops in bash. `for`, `while` and `until`.

Different `for` Syntax:
```bash
for x := 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements that can use $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

`while` Syntax:
```bash
while condition; do
  statements
done
```

`until` Syntax:
```bash
until condition; do
  statements
done
```

# 3. Tricks

## Set an alias

Run `nano ~/.bash_profile` and add the following line:

```bash
alias dockerlogin='ssh www-data@adnan.local -p2222'  # add your alias in .bash_profile
```

## To quickly go to a specific directory

Run `nano ~/.bashrc` and add the following line:

```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```

Now you can use the saved path:

```bash
source ~/.bashrc
cd $hotellogs
```

## Re-execute the previous command

This goes back to the days before you could rely on keyboards to have an "up" arrow key, but can still be useful. 
To run the last command in your history
```bash
!!
```
A common error is to forget to use `sudo` to prefix a command requiring privileged execution. Instead of typing the whole command again, you can:
```bash
sudo !!
```
This would change a `mkdir somedir` into `sudo mkdir somedir`.

## Exit traps

Make your bash scripts more robust by reliably performing cleanup.

```bash
function finish {
  # your cleanup here. e.g. kill any forked processes
  jobs -p | xargs kill
}
trap finish EXIT
```

## Saving your environment variables

When you do `export FOO = BAR`, your variable is only exported in this current shell and all its children, to persist in the future you can simply append in your `~/.bash_profile` file the command to export your variable
```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Accessing your scripts

You can easily access your scripts by creating a bin folder in your home with `mkdir ~/bin`, now all the scripts you put in this folder you can access in any directory.

If you can not access, try append the code below in your `~/.bash_profile` file and after do `source ~/.bash_profile`.
```bash
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Debugging
You can easily debug the bash script by passing different options to `bash` command. For example `-n` will not run commands and check for syntax errors only. `-v` echo commands before running them. `-x` echo commands after command-line processing.

```bash
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

## Contribution

- Report issues [How to](https://help.github.com/articles/creating-an-issue/)
- Open pull request with improvements [How to](https://help.github.com/articles/about-pull-requests/)
- Spread the word

## Translation
- [Chinese | 简体中文](https://github.com/vuuihc/bash-guide)
- [Turkish | Türkçe](https://github.com/omergulen/bash-guide)
- [Japanese | 日本語](https://github.com/itooww/bash-guide)

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
