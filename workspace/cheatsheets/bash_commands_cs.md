<div align="center">
    <h1>Command Cheatsheet</h1>
    <p>
        <em>A Linux command-line cheatsheet</em>
    </p>
</div>

<br>
<br>

## Table of Contents
1. [Command Information & Help](#command-information--help)
2. [File & Folder Management](#file--folder-management)
3. [Searching Files & Folders](#searching-files--folders)
4. [File Information](#file-information)
5. [Data Processing & Filtering](#data-processing--filtering)
6. [Shell Related Commands](#shell-related-commands)
7. [User Management](#user-management)
8. [File Permissions & Access Control](#file-permissions--access-control)
9. [Linux Processes](#linux-processes)
10. [Job Control](#job-control)

<br>
<br>

## Command Overview
|Row    |A                  |B        |C              |D                  |E                |F            |G                    |H            |I                  |J            |K                  |L            |M              |N              |O      |P                |Q      |R                |S                  |T              |U                  |V      |W            |X      |Y      |Z      |
|:---:  |:---:              |:---:    |:---:          |:---:              |:---:            |:---:        |:---:                |:---:        |:---:              |:---:        |:---:              |:---:        |:---:          |:---:          |:---:  |:---:            |:---:  |:---:            |:---:              |:---:          |:---:              |:---:  |:---:        |:---:  |:---:  |:---:  |      
|1      |[adduser](#adduser)|[bg](#bg)|[cat](#cat)    |[deluser](#deluser)|[$?](#exit-code) |[fg](#fg)    |[gpg](#gpg)          |[head](#head)|[infocmp](#infocmp)|[jobs](#jobs)|[kill](#kill)      |[less](#less)|[man](#man)    |[nice](#nice)  |[](#)  |[passwd](#passwd)|[](#)  |[renice](#renice)|[sed](#sed)        |[tail](#tail)  |[umask](#umask)    |[](#)  |[wait](#wait)|[](#)  |[](#)  |[](#)  |
|2      |[alias](#alias)    |[](#)    |[chmod](#chmod)|[df](#df)          |[export](#export)|[find](#find)|[grep](#grep)        |[help](#help)|[](#)              |[](#)        |[killall](#killall)|[ln](#ln)    |[mkdir](#mkdir)|[nohup](#nohup)|[](#)  |[ps](#ps)        |[](#)  |[rev](#rev)      |[set](#set)        |[tee](#tee)    |[uniq](#uniq)      |[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|3      |[&](#ampersand)    |[](#)    |[chown](#chown)|[diff](#diff)      |[](#)            |[](#)        |[groupadd](#groupadd)|[](#)        |[](#)              |[](#)        |[](#)              |[ls](#ls)    |[mv](#mv)      |[](#)          |[](#)  |[](#)            |[](#)  |[rm](#rm)        |[shopt](#shopt)    |[touch](#touch)|[unset](#unset)    |[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|4      |[apropos](#apropos)|[](#)    |[chsh](#chsh)  |[du](#du)          |[](#)            |[](#)        |[groupdel](#groupdel)|[](#)        |[](#)              |[](#)        |[](#)              |[](#)        |[](#)          |[](#)          |[](#)  |[](#)            |[](#)  |[rmdir](#rmdir)  |[shred](#shred)    |[tput](#tput)  |[useradd](#useradd)|[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|5      |[](#)              |[](#)    |[cp](#cp)      |[](#)              |[](#)            |[](#)        |[groupmod](#groupmod)|[](#)        |[](#)              |[](#)        |[](#)              |[](#)        |[](#)          |[](#)          |[](#)  |[](#)            |[](#)  |[](#)            |[sort](#sort)      |[tr](#tr)      |[userdel](#userdel)|[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|6      |[](#)              |[](#)    |[cut](#cut)    |[](#)              |[](#)            |[](#)        |[groups](#groups)    |[](#)        |[](#)              |[](#)        |[](#)              |[](#)        |[](#)          |[](#)          |[](#)  |[](#)            |[](#)  |[](#)            |[strings](#strings)|[tree](#tree)  |[usermod](#usermod)|[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|7      |[](#)              |[](#)    |[](#)          |[](#)              |[](#)            |[](#)        |[](#)                |[](#)        |[](#)              |[](#)        |[](#)              |[](#)        |[](#)          |[](#)          |[](#)  |[](#)            |[](#)  |[](#)            |[stty](#stty)      |[type](#type)  |[](#)              |[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|8      |[](#)              |[](#)    |[](#)          |[](#)              |[](#)            |[](#)        |[](#)                |[](#)        |[](#)              |[](#)        |[](#)              |[](#)        |[](#)          |[](#)          |[](#)  |[](#)            |[](#)  |[](#)            |[su](#su)          |[](#)          |[](#)              |[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |
|9      |[](#)              |[](#)    |[](#)          |[](#)              |[](#)            |[](#)        |[](#)                |[](#)        |[](#)              |[](#)        |[](#)              |[](#)        |[](#)          |[](#)          |[](#)  |[](#)            |[](#)  |[](#)            |[sudo](#sudo)      |[](#)          |[](#)              |[](#)  |[](#)        |[](#)  |[](#)  |[](#)  |

<br>
<br>

### Command Information & Help
To find more information about a command, we can use various other commands such as `man`, `help`, or even `--help`. However, how do you know which to use for which command?
For that we use `type` and we will see that some commands are either _shell built-in_ or its a _/usr/bin_ command. _Shell Built-in_ commands do not have man pages, so using `help` or `--help` is the only way of getting more info on a command.

|Command|Description|Example|
|:---|:---|:---|
|`type`|Displays information about a command type.|[View](#type)|
|`man`|an interface to the system reference manuals.|[View](#man)|
|`help`<br>`--help`|Display information about builtin commands.|[View](#help)|
|`apropos`|search the manual page names and descriptions.|[View](#apropos)|

#### type
```sh
    type cd
    type mkdir
```

#### man
```sh
    man mkdir
    man -k "execute command"
```

#### help
```sh
    help cd
```

#### apropos
```sh
    apropos "execute command"
```

<br>

### File & Folder Management
|Command|Description|Example|
|:---|:---|:---|
|`touch`|We use the touch command to create files, we can can create single or multiple files.|[View](#touch)|
|`mkdir`|We can us mkdir to create folders, either single or multiple, as well as entire folder structures.|[View](#mkdir)|
|`mv`|The move command can both move and rename files.|[View](#mv)|
|`cp`|This copies files, it can also copy a file with one name, and paste it as another name.|[View](#cp)|
|`rm`|The remove command, removes files only, however it can remove directories if not careful.<br>_This command doesnt completely remove the file from disk, it might not be in your trash, but it is still recoverable using some apps._|[View](#rm)|
|`rmdir`|Remove Direcctory is much like the `rm` command but for **empty** directories. If a directory is not empty, it will fail.|[View](#rmdir)|
|`shred`|Overwrites a file to hide its contents, and optionally delete it.|[View](#shred)|
|`gpg`|OpenPGP encryption and signing tool. Allows for encrypting your files.|[View](#gpg)|
|`ln` _Hardlink_<br>`ln -s` _Softlink_|These allow us to both create hard & softlinks, Hardlinks cannot point to a directory, while softlinks can point to files and directories.<br>Hard & softlinks point to the same inode, difference being when removing the original file, hardlink will retain the data as its pointing to the same inode, while softlinks will not as its just a reference to the path.<br>Think of hardlinks as a way making copies, as it points to the inode its basically another file on disk, pointing to the same inode as the original file, while softlinks are a type of shortcut that reference the path to an inode.|[View](#ln)|

#### touch
```sh 
    touch ~/file.txt
    touch ~/file1.txt ~/file2.txt
    touch ~/file{1..9}.txt
```

#### mkdir
```sh
    mkdir ~/folder
    mkdir ~/folder1 ~/folder2
    mkdir -p ~/folder/subfolder
```

#### mv
```sh
    mv ~/file1 ~/Documents/
    mv ~/file1 ~/file2 ~/Document/
       ↪ <command> <location> <destination>
    mv ~/filee ~/filei
       ↪ <command> <old-name> <new-name>
```

#### cp
```sh
    cp ~/file ~/Documents/
    cp ~/file1 ~/file2 ~/Documents
       ↪ <command> <location> <destination></destination>
```

#### rm
```sh
    rm ~/file
    rm ~/file1 ~/file2
    rm -r ~/folder/file
```

#### rmdir
```sh    
    rmdir ~/folder
```

#### shred
```sh
    shred -vuz -n 100 file.txt
     ↪ -v           |Verbose the actions of the command.
     ↪ -u           |Remove the file after each overwrite.
     ↪ -z           |On the final overwrite, add zeros to hide shredding.
     ↪ -n           |Specify the amount of time to overwrite the file.
```

#### gpg
```sh
    gpg -c file.txt
     ↪ -c           |Encrypt with a symmetric cipher using a passphrase.
```



#### ln
```sh
    ln <Target> <Link>
    ln ~/workspace/project/data.csv data.csv
    ln -s ~/Downloads/images images
```

<br>

### Searching Files & Folders
|Command|Description|Example|
|:---|:---|:---|
|`ls`|The list `ls` command is used to to view the contents of a directory.|[View](#ls)|
|`tree`|`tree` is much like the `ls -R` command, however it outputs the folder structure in a nice easy to read tree like format.|[View](#tree)|
|`globbing & Wildcards`|(\*/\*\*/\?/\[1-9]) are some of the globbing characters and we can using with commands, to perform tailored functions.|[View](#globbing--wildcards)|
|`find`|Use find to search for files in a specific directory, its a more sophisticated search function.|[View](#find)|
|`cat`|This concatenates a files, printing its contents to the terminal, we can also use globbing with this command.|[View](#cat)|
|`head`|This prints out the first 10 lines of a file, unless else specific.|[View](#head)|
|`tail`|This is the same as the `head` command, but for the end of a fail.|[View](#tail)|
|`less`|less opens the content of a file into its own program, allowing us to view, search and read files easier.|[View](#less)|
|`watch`|Executes a program periodically.|[View](#watch)|

#### ls
```sh
    ls 
    ls -a
    ls -l
    ls -R
    ls -lah
```

#### tree
```sh
    tree .
```

#### Globbing & Wildcards
```sh
    # IMG_7789.png IMG_7789.mov
    
    echo IMG?7789.*
     ↪ *        |everything
     ↪ **       |recursive everything, includes folders
     ↪ ?        |any single char
     ↪ [1-9]    |range
```

#### find
```sh
    find ~/Desktop -type d -empty -delete
    find . -name "file.txt"
    find /var/log/ -type f -size 1M
```

#### cat
```sh
    cat ~/file.txt
    cat ~/f* 
```

#### head
```sh
    head ~/file.txt
    head -n 20 ~/file.txt
```

#### tail
```sh
    tail ~/file.txt
    tail -n 20 ~/file.txt
```

#### less
```sh
    less file.txt
     ↪ :50p      |move 50% of the file
     ↪ -N        |shows line numbers
     ↪ =         |show info on the page, including percentages
     ↪ /         |forward search
     ↪ ?         |backwards search
     ↪ q         |quit
```

#### watch
```sh
    watch [options] [command]

    watch ipconfig
     ↪ -n           |Sets the intervals for when something should be re-run, or refreshed.
     ↪ -d           |Highlights the differences between updates.

    watch -n 3 -d ipconfig
```

<br>

### File Information
|Command|Description|Example|
|:---|:---|:---|
|`wc`|`wc` returns the amount of either lines, words or chars/bytes within a file.|[View](#wc)|
|`du`|Disk Usage shows how much disk usage the file is using, there are specific units that this is measured in.|[View](#du)|
|`diff`|This is a lot like when using `git diff` as an example, allowing us view differences within a file.|[View](#diff)|
|`df`|Disk free, reports file system space usage, we can use this for example to view our _inodes_ information.|[View](#df)|

#### wc
```sh
    wc ~/file.txt
    wc -lwc ~/file.txt 
     ↪ -l       |lists the amount of lines
     ↪ -w       |list the amount of words
     ↪ -c       |lists the amount of chars, or bytes of the file
```

#### du
```sh
    du ~/file.txt 
    du -h file.txt
     ↪ -s       |display only a total for each argument
     ↪ -h       |display in human-readable format
     ↪ -k       |display block size
```

#### diff
```sh
    diff file1.txt file2.txt
    diff < <(ls ./folder1) < <(ls ./folder2) 
```
#### df
```sh
    df -ih  #Displays the inode usage on our system
```

<br>

### Data Processing & Filtering
|Command|Description|Example|
|:---|:---|:---|
|`tee`|The `tee` command allows to redirect stdin to two places, example to the terminal and to a file.|[View](#tee)|
|`sort`|`Sort` sorts the contents of a file, by default it sorts aphabettically.|[View](#sort)|
|`uniq`|The `uniq` command list only the unique values of a file, however, the file needs to be sorted first, as the `uniq` command only checks the lines subsequent to it, or directly under it. This is why people usually run `sort` and then pipes that stdout to `uniq`.|[View](#uniq)|
|`grep`|`grep` allows us to search for patterns within a file or whatever is parsed to its stdin.|[View](#grep)|
|`strings`|Prints the sequences of printable characters in files such as binary files.|[View](#strings)|
|`tr`|`tr` which stands for **tr**anslate, translates/modifies a string of characters to something else, it works on a character level, meaning 'ab' 'cd', a will be change to c and b will be change d. We can also remove characters using `-d`, as well as work with ranges.|[View](#tr)|
|`rev`|`rev` reverses a string.|[View](#rev)|
|`cut`|`cut` allows us to modify a string by cutting out byte, characters or fields for a specific range.|[View](#cut)|
|`sed`|The `sed` tool allows us to quickly execute commands on a file or stdin. Example of how the commands would work is `sed 'command1; command2; ...'` and they allow us to do things such as `delete lines` or `insert lines` or whatever other command is available to us.|[View](#sed)|

#### tee
```sh
    ping google.com 2>&1 | tee -a ping_info.txt
```

#### sort
```sh
    sort file.txt
     ↪ -r       |sorts contents of file in reverse order
     ↪ -n       |sorts contents in reverse order
     ↪ -c       |check whether contents of file is sorted & find unsorted elements
     ↪ -k       |column number sort data by a specific column
     ↪ -u       |checks unique values only
```

#### uniq
```sh
    sort file.txt | uniq
     ↪ _sort -u file.txt_
```

#### grep
```sh
    ls | grep -F "file.txt"
    ip addr show | grep -F "inet"
                 | grep -E "[a-z][A-Z][1-9]"
                    ↪ egrep "[a-z][A-Z][1-9]" 
```

#### strings
```sh
    strings /usr/bin/ls
    sudo strings /dev/nvme1n1p2 | less
    sudo strings /dev/mem | less
```

#### tr
```sh
    echo "bash" | tr 'ba' 'di'
    echo "awesome" | tr 'a-z' 'A-Z'
    echo "Try removing the spaces inbetween" | tr -d ' '
```

#### rev
```sh
    echo 'Was it a cat I saw?' | rev
```

#### cut
```sh
    uptime | cut -b '2-9'
           | cut -c '2-9' # difference between b and c is c allows for more bytes as some character require 2 bytes or more
           | cut -d ' ' -f 1 
```

#### sed
```sh
    echo 'Hello Bash' | sed 's/Hello/Bye/g'
    echo 'Hello Bash' | sed 's/Hello/Bye/g'
```

<br>

### Shell Related Commands
|Command|Description|Example|
|:---|:---|:---|
|`export`<br>`unset`|`export` allows us to set environment variables, while unset removes these variables.|[View](#export--unset)|
|'chsh'|Allows us to change our default shell. [Read More](./env_variables_cs.md) on the **Environment & Shell Variables** page.|[View](#chsh)|
|`alias`|This allows us to shorten or create more abbreviated commands, by setting an alias.|[View](#alias)|
|`set`|Allows us to control the behaviour of our shell.|[View](#set)|
|`shopt`|Much like `set`, this also allows us to alter the behaviour of our shell.|[View](#shopt)|
|`infocmp`|Shows the escape sequences for our terminal|[View](#infocmp)|
|`tput`|Allows us to use the easier form of `infocmp`_escape sequences_, example `setaf` instead of `\E[%?%p1%{8}%<%t3%p1%d%e%p1%{16}%<%t9%p1%{8}%-%d%e38;5;%p1%d%;m,`.|[View](#tput)|

#### export
```sh
    export VARNAME='Hello, thiis has a typo'
    VARNAME="Hello, World!"
```

#### unset
```sh
    unset VARNAME
```

#### chsh
```sh
    chsh -s /bin/bash
```


#### alias
```sh
    alias updateme='sudo apt update && sudo apt upgrade'
    alias ls ='ls --color=Auto'
    alias cp='cp -v'
    alias mv='mv -v'
    alias mkdir='mkdir -v'
```

#### set
```sh
    set -x          #Sets a function or behaviour
    set +x          #Unsets a function or behaviour
```

#### shopt
```sh
    shopt -t        #This closes a terminal after a single command has run
```

#### infocmp
```sh
    infocmp
```

#### tput
```sh
    echo "$(tput setaf 4)$(tput setab 5)Hello, World!$(tput sgr0)"
```

<br>

### User Management
These next few commands will require some knowledge on what roles `/etc/passwd`, `/etc/shadow` & `/etc/group` play. 
As well as, looking at the three main groups of users and groups, there can be more depending on your system or OS. 

#### /etc/passwd 
Contains basic user account information.
```md
    cat /etc/passwd
    user:x:1000:1000:User:/home/user:/bin/bash
      |  |   |    |    |       |         |
      |  |   |    |    |       |         Login Shell (Users default shell)
      |  |   |    |    |       Home Directory
      |  |   |    |    GECOS (Comment - usually full name or description)
      |  |   |    Group ID (GID)
      |  |   User ID (UID)
      |  Password Placeholder (Real password stored in /etc/shadow)   
      Username (Login name)    
``` 

#### /etc/shadow
Stores encrypted user passwords and password aging information.The file is only readable for the root user or users with elevated priviledges.
The encryption used on passwords here are known as `bcrypt`.

```md
    cat /etc/shadow
    user:$6$hD...:20346:0:99999:7: : :
      |       |       |  |   |   | | | |
      |       |       |  |   |   | | | Reserved for future use.
      |       |       |  |   |   | | Account expiration date (blank - no expiration).
      |       |       |  |   |   | Inactive days after expiration (blank = disabled).
      |       |       |  |   |   Warning days before password expires.
      |       |       |  |   Maximum days password is valid.
      |       |       |  Minimum days before password can be changed again.
      |       |       Last password change.
      |       Password hash.
      Username.
``` 

#### /etc/group
```md
    cat /etc/group
    user:x:1000:
      |   |   |  |
      |   |   |  Group Members.
      |   |   Group ID (GID).
      |   Password placeholder (group passwaords are rarely used, stored in /etc/gshadow).
      Group Name.
```

#### Users on Linux 
- Root user &rarr; _The Root User has the Highest priviledges, indicated by the UID of 0. There can only be one root user._
- Standard User &rarr; _Limited Priviledges, Can temporarily gain administrative priviledges._
- Service User &rarr; _Limited Priviledges, users for specfic tasks, often not needing a GUI, e.g maintaining a Web Server._
- Groups &rarr; _All users must have a primary group, and can be assigned zero to unlimited additional groups._

#### Groups on Linux
- root &rarr; _The superuser group with administrative priviledges, allowing complete control over the system._
- sudo / wheel &rarr; _Members can use `sudo`. May also be called wheel on other unix operating systems._
- adm (admin) &rarr; _Members are allowed to read log files._
- lpadmin / lp &rarr; _Members can manage printers & print queues (CUPS). May also be called "lp"._
- www-data &rarr; _A group for web server processes (such as Apache or Nginx), gives access to web content._
- plugdev &rarr; _Allows users to manage pluggable devices (USB Sticks, External HHDs...)._

|Command|Description|Example|
|:---|:---|:---|
|`useradd`|We can create users using `useradd`.|[View](#useradd)|
|`passwd`|We can set the user password using `passwd`.|[View](#passwd)|
|`usermod`|We can modify another users details, including ourselves, but its best we logout to do  that.|[View](#usermod)|
|`userdel`|We can delete users from the system using the userdel command.|[View](#userdel)|
|`groups`|We can view ours or other users groups using this command.|[View](#groups)|
|`adduser`<br>`deluser`|These are some additional commands for debian users, this is another way of handling the operations of adding and removing users from groups.|[View](#adduser)<br>[View](#deluser)|
|`groupadd`|Can add our own groups, incase we want to define our own permissions.|[View](#groupadd)|
|`groupmod`|We can change or edit group information|[View](#groupmod)|
|`groupdel`|We can remove our custom groups using this command|[View](#groupdel)|
|`su`|Allows us to switch the user, su stands for 'Switch User'.|[View](#su)|
|`sudo`|Superuser do, gives temporary elevated priviledges of the root user to a standard user, however there is more to sudo when it comes to its options. Take a look at the `/etc/sudoers` file using the command `visudo`, as there is more configurations one can do within the file, it is also the reason why %sudo has the ability to elevate priviledges for certain users that are part of %sudo.|[View](#sudo)|

#### useradd
```sh
    "useradd [options] username"

    sudo useradd -m -d /home/lauren lauren
     ↪ -m           |Create home directory.
     ↪ -d           |Set custom directory.
     ↪ -s           |Set the default shell.
     ↪ -g           |Specify a primary group, instead of the default configuration.
     ↪ -G           |Add user to secondary groups.

    useradd -m -d /home/lauren lauren
```

#### passwd
```sh
    "passwd [options] username"

    passwd -S
    sudo passwd -S lauren
     ↪ -S           |Display password status.
     ↪ -d           |Delete  password.
     ↪ -n           |Set Minimum password age (Minimum wait time before changing password).
     ↪ -x           |Set Maximum password age (How  long the password last until it expires).
     ↪ -l           |Lock the user account.
     ↪ -u           |Unlock the user account.
    sudo passwd lauren
```

#### usermod
```sh
    "usermod [options] username"    

    sudo usermod -s /bin/bash -c "Lauren J." lauren
     ↪ -c            |Change users descition (full name).
     ↪ -s            |Change default shell.
     ↪ -d            |Change home directory (coupled with -m, we can also move the location of the home directory).
     ↪ -l            |Change the username.
     ↪ -g            |Change the primary group.
     ↪ -G            |Change secondary groups.
     ↪ -aG           |Add secondary groups.

    sudo usermod -G adm,lpadmin,sudo,plugdev lauren     |Adding secondary groups to a user
    sudo usermod -G adm,lpadmin,plugdev lauren          |Removing a group, you will need to specify all groups again, leaving out the group you dont want.  
    sudo usermod -aG www-data lauren                    |Adding a secondary group without having to re-write all existing groups.
```

#### userdel
```sh
    userdel [options] username

    userdel steve
     ↪ -r            |Removes the users home directory & emails if any.
     ↪ -f            |Basically the same as -r, however forces the removal even if the user is still logged in.
                     |Might also delete a group with the same name as this user (depending on system configuration).
    
    userdel -r steve 
```

#### groups
```sh
    groups [username/s]
    
    groups                      |Will print out the currents users groups.
    groups autumn               |Will print out a specific users groups.
    groups autumn bob lauren    |Can print out multiple users groups as well.
```

#### adduser
```sh
    adduser [user] [group]
    
    adduser lauren adm
```

#### deluser
```sh
    deluser [user] [group]

    deluser lauren adm
```

##### groupadd
```sh
    groupadd [options] groupname

    sudo groupadd -g 2500 myapp
     ↪ -g           |Set custom GID (usually a custom GID should be above 1000, but some companies can set a rule be above 5000 or 6000).
```

#### groupmod
```sh
    groupmod [options] groupname

    sudo groupmod -n myapps -g 5000 myapp
     ↪ -n            |Change the group name.
     ↪ -g            |Change the group ID (GID).
```

#### groupdel
```sh
    groupdel [options] groupname

    sudo groupdel groupname
```

#### su
```sh
    su [other-user]
   
    su              |Just using su, switches to the root user. 
    su lauren
    su -l lauren
     ↪ -l           |Start a login shell as if the user has just logged in. This loads the users environment path, so '/home/lauren'
```

#### sudo
```sh
    sudo [options] 
     ↪ -k           |Invalidates the users cached credentials
     ↪ -s           |Will start a shell with elevated rights
    
    sudo -u [user] -g [group] bash
    sudo -u lauren bash
     ↪ -u           |Start a program as a different user
     ↪ -g           |Start a program as a specific group
    
    sudo -u lauren touch /home/lauren/hello_world.txt
```

<br>

### File Permissions & Access Control

In Linux, file permissions are divided into 3 categories, Owner(u), Group(g) and Other(o). 
We can see this when listing files, for example this file.

```sh
    -rw-rw-r-- 1 owner group  18K Sep 21 17:53 bash_commands_cs.md

    -(rw-)(rw-)(r--)
    |  |    |    |
    |  |    |    Other(o)
    |  |    Group(g)
    |  Owner(u) 
    File type
```

#### Types of permissions
You can set file permissions symbolically or numerically.

- Read (r / 4) &rarr; The ability to read a file or list a directory.
- Write (w / 2) &rarr; The Ability to modify a file or creating or deleting files in a directory. _This also needs the execute permission enabled._
- Execute (x / 1) &rarr; Allows running the file as a program or changing into & traverse this directory.

```sh
      Read
      |Write
      ||Execute
      |||   
    -(rwx)(rw-)(r--)
      |||  ||   |
      421  42   4 
       7    6    4
```

#### Understanding umask in Linux
Umask is a Linux setting that defines the default permissions removed from new files and directories. New files start with 666 and directories with 777; the umask “masks out” bits to make them more restrictive. For example, a umask of 022 produces files with 644 and directories with 755.

|Command|Description|Example|
|:---|:---|:---|
|`chmod`|Sets the permissions on files or directories.|[View](#chmod)|
|`chown`|Sets the owner and group of a file.|[View](#chown)|
|`umask`|Sets the baseline security for files and directories. You can configure this umask value within your `login.defs` file, dor system wide rules, or use umask for the current session, or you can configure it in `.bashrc` file.|[View](#umask)|

#### chmod
```sh
    chmod u+rwx file.txt            |rwx    = 7
    chmod g+rw file.txt             |rw     = 6
    chmod o+r file.txt              |r      = 4
     ↪ chmod 764 file.txt
             |||
             ||Other(o)
             |Group(g)
             Owner(u)

    chmod 777 -R ./directory
```

#### chown
```sh
    chown user:group file.txt
     ↪ chown root:root file.txt

    chown user:group -R ./directory
```

#### umask
```sh
    umask
    umask 0002          |664 > -rw-rw-r--
    umask 0022          |644 > -rw-r--r--
    
    chmod +t ./folder/
     ↪ This sets the sticky (0)002 value for directories only, giving further permissions, for the owner to be the only person that can remove files or directories. 
    
    chmod u+s ./python3
    chmod u+S ./python3
     ↪ -rwsr-xr-x           |(SUID) Set User ID + executable
     ↪ -rwSr-xr-x           |(SUID) Set User ID + Not executable

    chmod g+s ./python3
    chmod g+S ./python3
     ↪ -rwxr-s-r-x          |(SGID) Set Group ID + executable
     ↪ -rwxr-S-r-x          |(SGID) Set Group ID + Not executable
```

<br>

### Linux Processes

#### Process states
- R &rarr; _Running State._
- S &rarr; _Sleeping (An Interruptable State)._
- D &rarr; _Uninterruptible Sleep State._
- T &rarr; _Traced or Stopped State._
- Z &rarr; _Zombie Process State_

|Command|Description|Example|
|:---|:---|:---|
|`ps`|Stands for **Process Status**, Displays information about running processes.|[View](#)|
|`nice`<br>`renice`|You can change the scheduling priority of a program by setting its "niceness". The range of niceness is from -20 to +19, with the default being 0. The lower the niceness e.g -20, the more priority a program takes, while a higher niceness e.g +19, the less priority it takes.<br>With renice, we can change the priority of a program that is already running.|[View](#nice)<br>[View](#renice)|
|`kill`|&#8226; Used to send signals to a process, this is usually done using the `kill` command. Use the link provided to practice this comamnd: `https://downloads.codingcoursestv.eu/055%20-%20bash/wget/download-slow`.<br>_Link provided from the course._|[View](#kill)|
|`killall`|kills the all the processes with a given name, e.g firefox. killall default signal is also SIGTERM.<br>Very similar to `kill -s SIGTERM $(pgrep -f firefox)`.|[View](#killall)|
|`$?`<br>_Exit Code_|We can use this to see the **exit code**.|[View](#exit-code)|

#### ps
```sh
    ps
     ↪ -A/e             |Shows all processes, from all users and sessions. (Can use either `-A` or `-e`)
     ↪ -f               |Full format listing, shows extended information such as , User, PPID and terminal.
     ↪ -p               |Show processes with process ID.
     ↪ --forest         |Shows process and parent processes in the form of an ASCII tree. (can be coupled with `-ef`)
     ↪ -l               |Shows entries in long format, basically adds some additional info. (can be coupled with `-ef`)
    
    ps aux
     ↪ -a               |Shows all processes of all users.
     ↪ -u               |Display the information in a more user-orientated manner.
     ↪ -x               |Shows processes without a tty.
```

#### nice
```sh
    nice -n [niceness] [program]

    nice -n +19 gedit
    sudo nice -n -20 gedit
```

#### renice
```sh
    renice -n [niceness] [process-ID]

    gedit           |Process ID of 23456
    renice -n 10 23456
    sudo renice -n -19 23456
    renice -n 19 $(pgrep -f firefox)
```

#### kill
```sh
    `https://downloads.codingcoursestv.eu/055%20-%20bash/wget/download-slow`            
    
    kill    
     ↪ -l                           |List available signals.
     ↪ -s                           |Specifiy the signal to be sent.
    
    kill -s [SIGNAL] [process-ID]
    kill -s SIGINT 12345
     ↪ kill -SIGINT 12345           |Another way of writing this without the flag.
    kill -s SINGINT $(pgrep wget)   |Using command subst... with pgrep to kill the process.
             ↪ SIGTERM              |Is the default signal for the kill command, asks the process nicely if it can terminat the process, if it cant, no problem.
             ↪ SIGINT               |Much like SIGTERM, however, tell the process to terminate so we can gain back control of our terminal.
             ↪ SIGKILL              |SIGINT & SIGTERM can be ignored by the process, the SIGKILL forces a termination.
             ↪ SIGHUP               |Signals that the terminal has closed, the program usually then exits.
             ↪ SIGSTOP              |Places a process into a stopped state, meaning a process has been paused.
             ↪ SIGCONT              |If we want to resume a process after its been stopped or paused, we can then continue it.
```

#### killall
```sh
    killall [process-ID]
    killall [SIGNAL] [process-ID]
    
    killall firefox
     ↪ kill -s SIGTERM $(pgrep -f firefox)
```

#### Exit Code
```sh
    echo $?
```

<br>

### Job Control

|Command|Description|Example|
|:---|:---|:---|
|`&`|Using the ampersand symbol at the end of a command, we can background a running process. This allows us to have or regain control of our terminal while a process is running, especially if it takes a long time.|[View](#ampersand)|
|`jobs`|This is how we can list the active jobs in our terminal.|[View](#jobs)|
|`fg`|Used to bring a background job to the foreground.|[View](#fg)|
|`bg`|Used to send foreground jobs to the background. This in combination with `Ctrl + Z`, to suspend or stop the process in the fg and we can then use `bg %[job-ID]` to continue the job in the background, same with `fg %[job-ID] &`.|[View](#bg)|
|`kill`|We can also kill a job, using the `kill` command, followed by the job number.|[View](#kill-job)|
|`stty`|Is a tool to change / print the terminal line settings, we can use the option `tostop` & `-tostop` to activate or disable having commands suspended if its output is being printed to the terminal.|[View](#stty)|
|`wait`|Waits for a background job to complete before doing _xyz_ for example.|[View](#wait)|
|`nohup`|We can use `nohup` to launch a program that will remain open|[View](#)|

#### Ampersand
```sh
    cmatrix &
    ping -c 100 localhost > /dev/null & 
```

#### jobs
```sh
    jobs
```

#### fg
```sh
    fg %[job-ID]
```

#### bg
```sh
    bg %[job-ID]
```

#### kill Job
```sh
    kill %[job-ID]
    kill -s SIGKILL %[job-ID]
```

#### stty
```sh
    stty tostop             |To enable the feature.
     ↪ stty -tostop         |To disable the feature.
```

#### wait
```sh
    wait                    |waits until all currently running jobs have changed their state.
    wait 123                |waits for a process of the ID of 123.
    wait %[job-ID]          |waits for a job number.
    wait -n                 |waits until anything has completed.
```

#### nohup
```sh
    nohup ping -c 100 localhost &
```

























