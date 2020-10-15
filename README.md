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
ប្រើសម្រាប់បង្ហាញអំពីមជ្ឈដ្ឋាន variable ក្នុងការដំឡើងកម្មវិធីអ្វីមួយ។ ប្រសិនបើអ្នកចង់មើល variable ដែលបានប្រើនោះគ្រាន់តែប្រើ `echo $VARIABLE_NAME` ។

```bash
export
```

ឧទាហរណ៍៖
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
whatis សម្រាប់បង្ហាញព័ត៌មានបន្ថែមពី ការបញ្ជា `ការបញ្ជា`, `ព្រឹតិ្តការណ៍`, `បណ្ណាល័យ` , `មុខងារ`និង , `ទំព័រពាក់ព័ន្ធ` ។

```bash
whatis something
```
ឧទាហរណ៍៖
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

whereis សម្រាប់អនុវត្តស្វែងរកប្រភពឯកសារ និង ទំព័រពាក់ព័ន្ធដែលបានដំឡើងប្រើប្រាស់នៅក្នុងប្រព័ន្ធស្វ័យប្រវត្តិ។
```bash
whereis name
```
ឧទាហរណ៍៖
```bash
$ whereis php
/usr/bin/php
```

### d. `which`

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

វាសម្រាប់សម្អាតអត្ថបទដែលមាននៅលើអេក្រង់បង្ហាញ window ។

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
វាឃើញប្រើភាគច្រើននៅក្នុង UNIX ឬ Linux។
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

chmod ដែលមកពីពាក្យ "change mode" ដែលអនុញ្ញាតឱ្យអ្នកអាចប្តូរម៉ូដឯកសារ read write ឬ execute លើឯកសារនិងថតឯកសារ។ សម្រាប់ព័ត៌មានលម្អិតលោកអ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://ss64.com/bash/chmod.html) ។ 
```bash
chmod -options filename
```

### c. `chown`

chown ដែលមកពីពាក្យ "change owner" ដែលអនុញ្ញាតឱ្យអ្នកអាចប្តូរម្ចាស់កម្មសិទ្ធិលើឯកសារឬថតឯកសារណាមួយបាន ដែលត្រូវបានកំណត់ជា user ឬ group។ ការប្រើប្រាស់ភាគច្រើនគឺអនុញ្ញាតពី user មួយទៅ group មួយទៀតដើម្បីមានសិទ្ធិចូលមកប្រើប្រាស់ដែរ។ 
```bash
chown -options user:group filename
```

### d. `cp`

សម្រាប់ចម្លងឯកសារពីកន្លែងមួយទៅកន្លែងណាមួយផ្សេងទៀត។
```bash
cp filename1 filename2
```

`filename1` ត្រូវតែជាទីតាំងរួមឈ្មោះឯកសារ និង `filename2` ជាទីតាំងរួមទាំងឈ្មោះឯកសារដែលលោកអ្នកចង់ចម្លងទៅ។
### e. `diff`

សម្រាប់ប្រៀបធៀបឯកសារ និងបង្ហាញបញ្ជីពីភាពខុសគ្នានៃឯកសារ។ 
```bash
diff filename1 filename2
```

### f. `file`

សម្រាប់កំណត់ប្រភេទឯកសារ។
```bash
file filename
```
ឧទាហរណ៍៖
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`

សម្រាប់ស្វែងរកឯកសារនិងទីតាំងណាមួយ។
```bash
find directory options pattern
```

ឧទាហរណ៍៖
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gunzip`

សម្រាប់ពន្លាឯកសារដែលបានបង្រួមដោយ gzip ។
```bash
gunzip filename
```

### i. `gzcat`

អនុញ្ញាតឱ្យអ្នកមើលឯកសារ gzipped ដោយមិនចាំបាច់មាន gunzip ។
```bash
gzcat filename
```

### j. `gzip`
 
សម្រាប់បង្រួមឯកសារ។
```bash
gzip filename
```

### k. `head`

សម្រាប់បង្ហាញអត្ថបទ ១០បន្ទាត់ដំបូងក្នុងឯកសារ។
```bash
head filename
```

### l. `lpq`

ពិនិត្យមើលលទ្ធផលបង្ហាញជាជួរៗ។
```bash
lpq
```
ឧទាហរណ៍៖
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`

សម្រាប់បង្ហាញលទ្ធផលឯកសារ។
```bash
lpr filename
```

### n. `lprm`

សម្រាប់លុបអ្វីមួយពីលទ្ធផលបង្ហាញជាជួរនោះ។
```bash
lprm jobnumber
```

### o. `ls`

សម្រាប់បង្ហាញឯកសារជាបញ្ជី។ `ls` មានជម្រើសជាច្រើន `-l` បង្ហាញព័ត៌មានឯកសារពី ទំហំ ម្ចាស់កម្មសិទ្ធិ និងថ្ងៃកំណែចុងក្រោយ។ `-a` សម្រាប់បង្ហាញបញ្ជីឯកសារ និងបង្ហាញឯកសារដែលមិនត្រូវបានបង្ហាញ។ សម្រាប់ព័ត៌មានលម្អិតលោកអ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://ss64.com/bash/ls.html) ។ 
```bash
ls option
```

ឧទាហរណ៍៖
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

សម្រាប់បង្ហាញផ្នែកដំបូងនៃឯកសារ (លោកអ្នកអាចរំកិលចុះក្រោមដោយប្រើ `space` ឬចុច `q` ដើម្បីបញ្ចប់)។
```bash
more filename
```

### q. `mv`

សម្រាប់ផ្លាស់ប្តូរទីតាំងឯកសារទៅកន្លែងផ្សេងមួយទៀត។

```bash
mv filename1 filename2
```

`filename1` ត្រូវតែជាទីតាំងរួមឈ្មោះឯកសារ និង `filename2` ជាទីតាំងរួមទាំងឈ្មោះឯកសារដែលលោកអ្នកចង់ផ្លាស់ប្តូរទៅ។

វាក៏អាចប្រើសម្រាប់កែឈ្មោះឯកសារផងដែរ។
```bash
mv old_name new_name
```

### r. `rm`

សម្រាប់លុបចេញឯកសារ។ ការប្រើប្រាស់ `command` នេះនៅលើថតឯកសារផ្តល់ឱ្យអ្នកនូវកំហុស។
`rm: directory: is a directory`

ដើម្បីលុបថតឯកសារអ្នកត្រូវប្រើ `-r` ដែលនឹងលុបអត្ថបទវិលជុំ(recursive)។ ជម្រើសផ្សេងអ្នកអាចប្រើ `-f` សម្រាប់បង្ខំ(force) ឱ្យលុបដោយគ្មានការបញ្ជាក់ណាមួយ។ 
```bash
rm filename
```

### s. `tail`

សម្រាប់បង្ហាញលទ្ធផលនៃឯកសារចំនួន ១០ បន្ទាត់ចុងក្រោយ។ `-f` ដើម្បីបង្ហាញទិន្នន័យបន្ថែមនៅពេលឯកសារនោះ។
```bash
tail filename
```

### t. `touch`

ការបង្កើតឯកសារថ្មី និងការផ្លាស់ប្តូរពេលវេលានៃឯកសាររបស់អ្នក។ ប្រសិនបើវាមិនមានជាន់ឈ្មោះឯកសារណាមួយទេ វានឹងត្រូវបានបង្កើតឡើង។
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

`awk` គឺជាពាក្យបញ្ជា `command` ដែលមានប្រយោជន៍បំផុតសម្រាប់ដោះស្រាយឯកសារអត្ថបទ។ វាដំណើរការលើឯកសារទាំងមូលតាមបន្ទាត់។ តាមលំនាំដើមវាប្រើចន្លោះទំនេរដើម្បីបំបែកវាល។ វាជាពាក្យសម្រាប់យបញ្ជា `awk`

```bash
awk '/search_pattern/ { action_to_take_if_pattern_matches; }' file_to_parse
```

អ្នកអាចយកគំរូឯកសារ `/etc/passwd`. នេះជាទិន្នន័យគំរូដែលឯកសារនេះមាន៖

```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```

ឥឡូវយើងសាកយកតែ `username` ពីឯកសារមួយនេះ។ `-F` សម្រាប់បំបែកតំបន់។ ក្នុងករណីនេះ `:`. `{ print $1 }` សម្រាប់បង្ហាញការផ្ទៀងផ្ទាត់តំបន់ដំបូង។
```bash
awk -F':' '{ print $1 }' /etc/passwd
```

បន្ទាប់ពីបានដំណើរការការបញ្ជាខាងលើអ្នកនឹងទទួលបានលទ្ធផលដូចខាងក្រោម។
```
root
daemon
bin
sys
sync
```

សម្រាប់ព័ត៌មានលម្អិតការប្រើប្រាស់ `awk` អ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://www.cyberciti.biz/faq/bash-scripting-using-awk) ។ 

### b. `cut`
ការលុបផ្នែកណាមួយក្នុងឯកសារ។

*example.txt*
```bash
red riding hood went to the park to play
```

*ដើម្បីបង្ហាញជួរឈរទី២ ៧ និង ៩ ដែលមានដកឃ្លាទុក*
```bash
cut -d " " -f2,7,9 example.txt
```
```bash
riding park play
```

### c. `echo`

បង្ហាញអត្ថបទមួយបន្ទាត់

*បង្ហាញ "Hello World"*
```bash
echo Hello World
```
```bash
Hello World
```


*បង្ហាញ "Hello World" ចុះបន្ទាត់ថ្មីក្នុងមួយពាក្យៗ*
```bash
echo -ne "Hello\nWorld\n"
```
```bash
Hello
World
```

### d. `egrep`
បង្ហាញអត្ថបទជាបន្ទាត់ដែលតាមលំនាំ - ការមតិបន្ថែម (alias 'grep -E')

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
ទម្រង់អក្សរមានលំដាប់

*ឧទាហរណ៍: example.txt (1 line)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*បង្ហាញអត្ថបទបន្ទាត់ដែលមាន ២០ពាក្យក្នុងឯកសារ example*
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
វែងរកពាក្យក្នុងអត្ថបទឯកសារមួយ អ្នកអាចប្រើប្រាស់ grep ដើម្បីស្វែងរកវានឹងបង្ហាញលទ្ធផលជាជួរ។
```bash
grep pattern filename
```

ឧទាហរណ៍៖
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```

អ្នកអាចប្រើការស្វែងរកឯកសារដោយបង្ខំលើកលែងពាក្យដោយប្រើប្រាស់ `-i`។ ចំណែក `-r` វាអាចស្វែងរកគ្រប់ឯកសារទាំងអស់ដែលស្ថិតនៅក្នុងថតឯកសារដែលអ្នកបានកំណត់។ ឧទាហរណ៍៖ 
```bash
$ grep -r admin /etc/
```

ចំណែក `-w` សម្រាប់ស្វែករកតែពាក្យប៉ុណ្ណោះ។ សម្រាប់ព័ត៌មានលម្អិតការប្រើប្រាស់ `grep` អ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](https://www.cyberciti.biz/faq/grep-in-bash) ។ 

### h. `nl`
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
កំណែទម្រង់អត្ថបទដោយផ្ទាល់សម្រាប់ការបំលែងអត្ថបទ

*example.txt*
```bash
Hello This is a Test 1 2 3 4
``` 

*ជំនួសគ្រប់ ដកឃ្លា(space) ជាមួយសហាសញ្ញា(-)*
```bash
sed 's/ /-/g' example.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*ជំនួសគ្រប់លេខទាំងអស់ដោយអក្សរ "d"*
```bash
sed 's/[0-9]/d/g' example.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
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
បំលែងឬលុបអក្សរ

*example.txt*
```bash
Hello World Foo Bar Baz!
```

*បំលែងគ្រប់អក្សរតូចទាំងអស់ទៅជាអក្សរធំ*
```bash
cat example.txt | tr 'a-z' 'A-Z' 
```
```bash
HELLO WORLD FOO BAR BAZ!
```

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

*បង្ហាញអត្ថបទនៃបន្ទាត់នីមួយៗ និងចំនួនដែលបានរកឃើញក្នុងជួរបន្ទាត់ជាមួយគ្នា*
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
បង្ហាញប្រាប់អ្នកចំនួនបន្ទាត់ ពាក្យ និងពញ្ជនៈដែលមានក្នុងឯកសារ។
```bash
wc filename
```

ឧទាហរណ៍៖
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```

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
អ្នកអាចផ្លាស់ប្តូរពីទីតាំងមួយទៅទីតំាងផ្សេងទៀតដោយប្រើ 
```bash
$ cd
```
ផ្លាស់ប្តូរអ្នកពីទីតាំងដើមទៅទីតាំង `dirname` ជាទីតាំងអ្នកប្តូរទៅ
```bash
cd dirname
```

### b. `mkdir`
បង្កើតថតថ្មី
```bash
mkdir dirname
```

អ្នកអាចបង្កើតថតថ្មីច្រើនក្នុងការបញ្ជាតែម្តងក្នុងថតដែលអ្នកស្ថិតនៅ
```bash
mkdir 1stDirectory 2ndDirectory 3rdDirectory
```

អ្នកអាចបង្កើតថតថ្មីទៅលើថតដែលអ្នកមិនស្ថិតនៅ។ ឧទាហរណ៍ អ្នកចង់បង្កើតថត 'project1' ក្នុង '/samples/bash/projects/' ដែលអ្នកបានស្ថិតនៅកន្លែងនោះ៖
```bash 
mkdir /samples/bash/projects/project1
```

ប្រើថតដែលអ្នកបង្កើតនោះមិនជាន់ឈ្មោះនោះទេ វានឹងបង្កើតថតនោះឱ្យអ្នក

### c. `pwd`  
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
បញ្ជីការបញ្ឈប់ឬការងារដែលបានដំណើរការនៅខាងក្រោយ ការផ្អាក់ដំណើរការការងារបានដំណើរការនៅខាងក្រោយ។

### b. `cal`
បង្ហាញប្រតិទិនរបស់ខែនេះ

### c. `date`
បង្ហាញថ្ងៃខែ និងម៉ោងបច្ចុប្បន្ន

### d. `df`
បង្ហាញទិន្នន័យការប្រើប្រាស់ ឌីស

### e. `dig`
បង្ហាញព័ត៌មានឈ្មោះ DNS
```bash
dig domain
```

### f. `du`
បង្ហាញទិន្នន័យការប្រើប្រាស់ឌីសនៃឯកសារឬថតសារ។ សម្រាប់ព័ត៌មានលម្អិតការប្រើប្រាស់ អ្នកអាចអានក្នុង [តំណភា្ជប់នេះបាន ](http://www.linfo.org/du.html) ។ 
```bash
du [option] [filename|directory]
```

ជម្រើសបន្ថែម៖
- `-h` (human readable) បង្ហាញលទ្ធផលគិតជា គីឡូបៃត៍ (kilobytes - K) មេហ្គាបៃខ្នាត (Megabytes - M) និង ជីហ្គាបៃខ្នាត (Gigabytes - G)
- `-s` (supress or summarize) បង្ហាញទិន្នន័យសរុបឌីសនៃថតឯកសារ និង របាយការណ៍សម្រាប់ថតរង

ឧទាហរណ៍៖
```bash
du -sh pictures
1.4M pictures
```

### g. `fg`
នាំមកនូវការងារថ្មីៗមកនៅផ្ទៃខាងមុខ។

### h. `finger`
បង្ហាញព័ត៌មានអំពីអ្នកប្រើប្រាស់ user ។
```bash
finger username
```
### i. `jobs`
បង្ហាញបញ្ជីការងារនិងចំនួនដែលកំពុងដំណើរនៅខាងក្រោយ។

### j. `last`
បង្ហាញទិន្នន័យចំនួនបានចូលប្រើប្រាស់របស់អ្នកប្រើប្រាស់ user
```bash
last yourUsername
```

### k. `man`
បង្ហាញសៀវភៅណែនាំសម្រាប់ពាក្យបញ្ជាដែលបានបញ្ជាក់។
```bash
man command
```

### l. `passwd`
អនុញ្ញាតឱ្យអ្នកកំពុងប្រើប្រាស់អាចប្តូរលេខសម្ងាត់

### m. `ping`
Ping host និងបង្ហាញលទ្ធផល
```bash
ping host
```

### n. `ps`
បង្ហាញកម្មវិធីកំពុងដំណើរការ
```bash
ps -u yourusername
```

បង្ហាញព័ត៌មានលម្អិតពីបញ្ជីនីមួយៗដែលប្រើប្រាស់ flag
```bash
ps -ef
```

### o. `quota`
បង្ហាញតាឌីសរបស់អ្នក
```bash
quota -v
```

### p. `scp`
ផ្ទេរឯកសាររវាងម៉ាស៊ីនប្រើប្រាស់និងម៉ាស៊ីនបញ្ជាចម្ងាយឬរវាងម៉ាស៊ីនពីបញ្ជាពីចម្ងាយពីរ។ 

*ចម្លងពីម៉ាស៊ីនប្រើប្រាស់ទៅម៉ាស៊ីនបញ្ជាពីចម្ងាយ*
```bash
scp source_file user@host:directory/target_file
```

*ចម្លងពីម៉ាស៊ីនបញ្ជាពីចម្ងាយមកមា៉ស៊ីនប្រើប្រាស់*
```bash
scp user@host:directory/source_file target_file
scp -r user@host:directory/source_folder target_folder
```

ការបញ្ជានេះមានជម្រើសបន្ថែម `-P` ដែលអាចប្រើប្រាស់សម្រាប់ភ្ជាប់ប្រើប្រាស់ Port ណាមួយបាន
```bash
scp -P port user@host:directory/source_file target_file
```

### q. `ssh`
shh (SSH client) គឺជាកម្មវិធីមួយសម្រាប់ចូលប្រើប្រាស់និងដំណើរការការបញ្ជាទៅកាន់ម៉ាស៊ីនបញ្ជាពីចម្ងាយ។

```bash
ssh user@host
```

ការបញ្ជានេះមានជម្រើសបន្ថែម `-p` ដែលអាចប្រើប្រាស់សម្រាប់ភ្ជាប់ប្រើប្រាស់ Port ណាមួយបាន

```bash
ssh -p port user@host
```

### r. `top`
បង្ហាញពីដំណើរការបច្ចុប្បន្នរបស់អ្នក

### s. `uname`
បង្ហាញពីព័ត៌មាន kernel 
```bash
uname -a
```

### t. `uptime`
បង្ហាញពីពេលវេលាបច្ចុប្បន្នប្រើប្រាស់កុំព្យូទ័រ

### u. `w`
បង្ហាញនរណាដែលអាចចូលប្រើប្រាស់បាន

### v. `wget`
សម្រាប់ទាញយកឯកសារ 
```bash
wget file
```

### w. `whoami`
បង្ហាញពីឈ្មោះអ្នកដែលកំពុងប្រើប្រាស់បច្ចុប្បន្ន

### x. `whois`
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
បញ្ឈប់ការដំណើរការណាមួយដោយ ID
```bash
kill PID
```

### b. `killall`
បញ្ឈប់ការដំណើរការណាមួយដោយឈ្មោះ
```bash
killall processname
```

### c. &
សញ្ញា `&` ភា្ជប់ការបញ្ជាបន្ថែមផ្សេងទៀត

```bash
command &
```

### d. `nohup`
nohup មកពីពាក្យ "No Hang Up" អនុញ្ញាតឱ្យអ្នកបញ្ជាឬដំណើរការ script ណាមួយដែលអ្នកបានកំណត់វានឹងដំណើរការរហូតទោះបីអ្នកបានចាកចេញក៏ដោយ។
```bash
nohup command
```

ភ្ជាប់ការដំណើរការផ្សេងទៀតដោយសញ្ញា `&` ដើម្បីបង្កើតការដំណើរការខាងក្រោយ
```bash
nohup command &
```

# 2. Basic Shell Programming
បន្ទាត់ដំបូងដែលអ្នកនឹងត្រូវសរសេរជា `script` ត្រូវបានគេហៅថា `shebang` ។ បន្ទាត់ `script` នេះវាអាចមានសមត្ថភាពដំណើរ `script` ដោយមិនចំបាច់ប្រើប្រាស់ `sh`, `bash`, `python`, `php` etc នៅខាងដើមក្នុងផ្ទាំងពណ៌ខ្មៅដើម្បីធ្វើការបញ្ជាទៀតឡើយ។

```bash
#!/usr/bin/env bash
```

## 2.1. Variables
ការបង្កើតអថេរនៅក្នុង bash គឺស្រដៀងនឹងភាសាផ្សេងទៀត។ វាមិនមានប្រភេទទិន្នន័យទេ អថេរក្នុងប៊្លុកអាចមានលេខតួអក្សរ។ អ្នកមិនចាំបាច់ប្រកាសប្រភេទអថេរទេគ្រាន់តែផ្តល់តម្លៃទៅវា វានឹងបង្កើតដោយខ្លួនឯង។

ឧទាហរណ៍៖
```bash
str="hello world"
```

ខាងលើនេះជាការបង្កើតអថេរ `str` ដែលមានតម្លៃ "hello world"។ ក្នុងការយកមកប្រើប្រាស់អ្នកគ្រាន់តែដាក់សញ្ញា `$` នៅខាងដើមអថេរជាការស្រេច។

ឧទាហរណ៍៖
```bash
echo $str   # hello world
```
## 2.2. Array
វាក៏ដូចជាភាសាដទៃដែរគឺមាន array ដូចគ្នា។ Array មួយយើងបានដឹងហើយវាអាចផ្ទុកតម្លៃជាច្រើនក្នុងអថេរតែមួយដែលវាមានទំហំមិនអាចកំណត់បានឡើយ។ Array នៅក្នុង bash ក៏ចាប់ផ្តើមពី index ទីសូន្យ។ ខាងក្រោមនេះជាវិធីបង្កើត array ក្នុង bash ៖

ឧទាហរណ៍៖
```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```

ដើម្បីបង្ហាញតម្លៃស្ថិតនៅ index ណាមួយអ្នកអាចប្រើប្រាស់ដូចខាងក្រោមនេះ

```bash
${array[i]}     # where i is the index
```

ប្រសិនបើអ្នកមិនបានដឹងពីចំនួនធាតុ array ឬមិនដឹងវាបានបង្កើតដោយមាន array ប្រើចំនួនលំដាប់លេខ index ទីសូន្យឬនោះទេ។ ដើម្បីទាញយកតម្លៃក្នុង array មកប្រើដោយមិនស្គាល់ប្រភេទ index អ្នកអាចធ្វើតាមវិធីខាងក្រោម៖
```bash
${#array[@]}
```
Bash ក៏ស្គាល់សម្រាប់ល័ក្ខខ័ណ្ឌពិសេសមួយចំនួន។ ខាងក្រោមនេះជាឧទាហរណ៍៖

```bash
${varname:-word}    # if varname exists and isn't null, return its value; otherwise return word
${varname:=word}    # if varname exists and isn't null, return its value; otherwise set it word and then return its value
${varname:+word}    # if varname exists and isn't null, return word; otherwise return null
${varname:offset:length}    # performs substring expansion. It returns the substring of $varname starting at offset and up to length characters
```

## 2.3 String Substitution
ដើម្បីពិនិត្យ syntax របៀបរៀបចំប្រភេទ string

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
ដូចគ្នាទៅនឹងភាសាដទៃ អ្នកអាចប្រើប្រាស់មុខងារ (function) ដើម្បីបែងចែកជាក្រុមងាយស្រួលក្នុងការអនុវត្តទៅការងារផ្សេងៗ។ ការបង្កើតមុខងារ (function) គឺគ្រាន់តែសរសេរ ឈ្មោះមុខងារ { កូដការងារ }។ ការហៅមកប្រើប្រាស់មុខងារនោះគ្រាន់តែហៅឈ្មោះរបស់វា។

```bash
function name() {
    shell commands
}
```

ឧទាហរណ៍៖
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

ពេលអ្នកគ្រាន់តែហៅឈ្មោះមុខងារថា `hello` នោះវានឹងបង្ហាញលទ្ធផល "world!"។ មុខងារទាំងទីពីរមាន `hello` និង `say` ក៏ជា function ដូចគ្នា។ ភាពខុសគ្នារបស់មុខងារនេះគឺ function say វាត្រូវការប៉ារ៉ាម៉ែត្រដើម្បីយកទៅបង្ហាញលទ្ធផលក្នុងមុខងាររបស់ខ្លួនវាផ្ទាល់។ 

## 2.5. Conditionals
ការគ្រប់គ្រងល័ក្ខខ័ណ្ឌ (Conditionals statement) ក្នុង bash គឺស្រដៀងទៅនឹងភាសាដទៃដែរ។ ល័ក្ខខ័ណ្ឌមានច្រើនទម្រង់ដូចជាទម្រង់មូលដ្ឋានបំផុតគឺ if ប្រសិនបើល័ក្ខខ័ណ្ឌត្រឹមត្រូវវានឹងដំណើរការកិច្ចដែលសិ្ថតនៅក្នុងខ្លួនវា។ 

```bash
if [ expression ]; then
    will execute only if expression is true
else
    will execute if expression is false
fi
```

ប្រសិនបើវាមានល័ក្ខខ័ណ្ឌច្រើនស្មុកស្មាញ អ្នកអាចប្រើល័ក្ខខ័ណ្ឌមួយទៀតហៅថា `case statements`។ 

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

ឧទាហរណ៍ល័ក្ខខ័ណ្ឌ៖

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
ការវិលជុំមានបីប្រភេទក្នុង bash គឺ `for`, `while` និង `until` ។

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
ដំណើរការ `nano ~/.bash_profile` និងបន្ថែមកូដចូលទៅក្នុង editor៖ 
```bash
alias dockerlogin='ssh www-data@adnan.local -p2222'  # add your alias in .bash_profile
```

## To quickly go to a specific directory
ដំណើរការ `nano ~/.bashrc` និងបន្ថែមកូដចូលទៅក្នុង editor៖ 
```bash
export hotellogs="/workspace/hotel-api/storage/logs"
```

អ្នកអាចរក្សាទុក path ខាងលើបានដោយប្រើ៖ 
```bash
source ~/.bashrc
cd $hotellogs
```

## Re-execute the previous command
អ្នកអាចត្រលប់ទៅកាន់ការបញ្ជាពីមុនៗបានដោយចុចសញ្ញា "ព្រួញឡើងលើ" នៅលើក្តារចុច ឬប្រើសញ្ញាឧទានពីរក៏អាចត្រលប់ទៅកាន់ការបញ្ជាចាស់បាន។
```bash
!!
```

ការបញ្ជាមួយចំនួនអាច errro គឺវាត្រូវការ `sudo` ដើម្បីបញ្ជាជាប្រតិបត្តិដែលមានឯកសិទ្ធិ។ អ្នកអាចប្រើប្រាស់ដូចខាងក្រោមនេះបាន៖
```bash
sudo !!
```
This would change a `mkdir somedir` into `sudo mkdir somedir`.
អ្នកគួរតែប្តូរការសរសេរ `mkdir somedir` ទៅជា `sudo mkdir somedir` ដែលទាក់ទងនឹងប្រតិបត្តិដែលមានឯកសិទ្ធិ។

## Exit traps
ការសរសេរ script ក្នុង bash ឱ្យមានភាពងាយអានមានសណ្តាប់ឆ្នាប់និងស្អាតដែលមាន comment ព័ត៌មានបន្ថែម។
```bash
function finish {
  # your cleanup here. e.g. kill any forked processes
  jobs -p | xargs kill
}
trap finish EXIT
```

## Saving your environment variables
ពេលអ្នកប្រើ `export FOO = BAR` អថេររបស់អ្នកត្រូវតែ export ដាក់ចូលទៅ shell និង shell កូនដែលពាក់ព័ន្ធព្រោះជៀសវាងបញ្ហាថ្ងៃក្រោយភ្លេច export ចូល `~/.bash_profile` ពេលអ្នកហៅអថេរណាមួយមិនត្រឹមត្រូវក្នុង shell នោះ។

```bash
echo export FOO=BAR >> ~/.bash_profile
```

## Accessing your scripts
អ្នកងាយស្រួលក្នុងការចូលទៅប្រើប្រាស់ script ដែលបានបង្កើតក្នុងថតឯកសារ bin ក្នុងទំព័រដើមដោយ `mkdir ~/bin` ព្រោះគ្រប់ script ទាំងអស់ដែលស្ថិតក្នុងថតនេះវាអាចមានសិទ្ធិប្រើប្រាស់គ្រប់ថតទាំងអស់។

ប្រសិនបើអ្នកមិនអាចចូលប្រើប្រាស់បាន អ្នកអាចប្រើប្រាស់កូដខាងក្រោមនេះបាននៅក្នុង `~/.bash_profile` និងបន្ទាប់មកប្រើ command `source ~/.bash_profile` ៖
```bash
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Debugging
អ្នកអាច debug ក្នុង bash script ដោយបញ្ចូលជម្រើសផ្សេងគ្នាទៅក្នុង `bash` command។ ឧទាហរណ៍ `-n` វានឹងមិនដំណើរការការបញ្ជាទេ និងពិនិត្យ syntax ដែល error។ `-v`echo commands មុនដំណើរការ `command`។ `-x` echo commands បន្ទាប់ពី `command-line` បានដំណើរការ។ 

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
- [English | Original](https://github.com/Idnan/bash-guide)
- [Chinese | 简体中文](https://github.com/vuuihc/bash-guide)
- [Turkish | Türkçe](https://github.com/omergulen/bash-guide)
- [Japanese | 日本語](https://github.com/itooww/bash-guide)
- [Vietnamese | Tiếng Việt](https://github.com/nguyenvanhieuvn/hoc-bash)
- [Khmer | ភាសាខ្មែរ](https://github.com/samreachyan/bash-guide)

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
