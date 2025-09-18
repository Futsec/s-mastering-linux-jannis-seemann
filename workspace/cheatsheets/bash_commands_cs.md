<div align="center">
    <h3>Command Cheatsheet</h3>
    <p>
        <em>A Linux command cheatsheet</em>
    </p>
</div>

<br>
<br>

### Table of Content
- [File & Folder Management](#file-folder-management)
- [Searching Files & Folders](#searching-files-folders)
- [File Information](#file-information)
- [Data Processing & Filtering](#data-processing-filtering)
- [Shell Related Commands](#shell-related-commands)
- [User Management](#user-management)

<br>
<br>

##### &#8226; File & Folder Management
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|FFM-01|`touch`|We use the touch command to create files, we can can create single or multiple files.|[View](#touch)|
|FFM-02|`mkdir`|We can us mkdir to create folders, either single or multiple, as well as entire folder structures.|[View](#mkdir)|
|FFM-03|`mv`|The move command can both move and rename files.|[View](#mv)|
|FFM-04|`cp`|This copies files, it can also copy a file with one name, and paste it as another name.|[View](#cp)|
|FFM-05|`rm`|The remove command, removes files only, however it can remove directories if not careful.|[View](#rm)|
|FFM-06|`rmdir`|Remove Direcctory is much like the `rm` command but for **empty** directories. If a directory is not empty, it will fail.|[View](#rmdir)|
|FFM-07|`ln` _Hardlink_<br>`ln -s` _Softlink_|These allow us to both create hard & softlinks, Hardlinks cannot point to a directory, while softlinks can point to files and directories.<br>Hard & softlinks point to the same inode, difference being when removing the original file, hardlink will retain the data as its pointing to the same inode, while softlinks will not as its just a reference to the path.<br>Think of hardlinks as a way making copies, as it points to the inode its basically another file on disk, pointing to the same inode as the original file, while softlinks are a type of shortcut that reference the path to an inode.|[View](#ln)|

##### touch
```sh 
    touch ~/file.txt
    touch ~/file1.txt ~/file2.txt
    touch ~/file{1..9}.txt
```

##### mkdir
```sh
    mkdir ~/folder
    mkdir ~/folder1 ~/folder2
    mkdir -p ~/folder/subfolder
```

##### mv
```sh
    mv ~/file1 ~/Documents/
    mv ~/file1 ~/file2 ~/Document/
       ↪ <command> <location> <destination>
    mv ~/filee ~/filei
       ↪ <command> <old-name> <new-name>
```

##### cp
```sh
    cp ~/file ~/Documents/
    cp ~/file1 ~/file2 ~/Documents
       ↪ <command> <location> <destination></destination>
```

##### rm
```sh
    rm ~/file
    rm ~/file1 ~/file2
    rm -r ~/folder/file
```

##### rmdir
```sh    
    rmdir ~/folder
```

##### ln
```sh
    ln <Target> <Link>
    ln ~/workspace/project/data.csv data.csv
    ln -s ~/Downloads/images images
```

<br>

##### &#8226; Searching Files & Folders
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|SFF-01|`ls`|The list `ls` command is used to to view the contents of a directory.|[View](#ls)|
|SFF-02|`tree`|`tree` is much like the `ls -R` command, however it outputs the folder structure in a nice easy to read tree like format.|[View](#tree)|
|SFF-03|`globbing & Wildcards`|(\*/\*\*/\?/\[1-9]) are some of the globbing characters and we can using with commands, to perform tailored functions.|[View](#globbing--wildcards)|
|SFF-04|`find`|Use find to search for files in a specific directory, its a more sophisticated search function.|[View](#find)|
|SFF-05|`cat`|This concatenates a files, printing its contents to the terminal, we can also use globbing with this command.|[View](#cat)|
|SFF-06|`head`|This prints out the first 10 lines of a file, unless else specific.|[View](#head)|
|SFF-07|`tail`|This is the same as the `head` command, but for the end of a fail.|[View](#tail)|
|SFF-08|`less`|less opens the content of a file into its own program, allowing us to view, search and read files easier.|[View](#less)|

##### ls
```sh
    ls 
    ls -a
    ls -l
    ls -R
    ls -lah
```

##### tree
```sh
    tree .
```

##### Globbing & Wildcards
```sh
    # IMG_7789.png IMG_7789.mov
    
    echo IMG?7789.*
     ↪ *        |everything
     ↪ **       |recursive everything, includes folders
     ↪ ?        |any single char
     ↪ [1-9]    |range
```

##### find
```sh
    find ~/Desktop -type d -empty -delete
    find . -name "file.txt"
    find /var/log/ -type f -size 1M
```

##### cat
```sh
    cat ~/file.txt
    cat ~/f* 
```

##### head
```sh
    head ~/file.txt
    head -n 20 ~/file.txt
```

##### tail
```sh
    tail ~/file.txt
    tail -n 20 ~/file.txt
```

##### less
```sh
    less file.txt
     ↪ :50p      |move 50% of the file
     ↪ -N        |shows line numbers
     ↪ =         |show info on the page, including percentages
     ↪ /         |forward search
     ↪ ?         |backwards search
     ↪ q         |quit
```

<br>

##### &#8226; File Information
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|FI-01|`wc`|`wc` returns the amount of either lines, words or chars/bytes within a file.|[View](#wc)|
|FI-02|`du`|Disk Usage shows how much disk usage the file is using, there are specific units that this is measured in.|[View](#du)|
|FI-03|`diff`|This is a lot like when using `git diff` as an example, allowing us view differences within a file.|[View](#diff)|
|FI-04|`df`|Disk free, reports file system space usage, we can use this for example to view our _inodes_ information.|[View](#df)|

##### wc
```sh
    wc ~/file.txt
    wc -lwc ~/file.txt 
     ↪ -l       |lists the amount of lines
     ↪ -w       |list the amount of words
     ↪ -c       |lists the amount of chars, or bytes of the file
```

##### du
```sh
    du ~/file.txt 
    du -h file.txt
     ↪ -s       |display only a total for each argument
     ↪ -h       |display in human-readable format
     ↪ -k       |display block size
```

##### diff
```sh
    diff file1.txt file2.txt
    diff < <(ls ./folder1) < <(ls ./folder2) 
```
##### df
```sh
    df -ih  #Displays the inode usage on our system
```

<br>

##### &@8226; Data Processing & Filtering
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|DPF-01|`tee`|The `tee` command allows to redirect stdin to two places, example to the terminal and to a file.|[View](#tee)|
|DPF-02|`sort`|`Sort` sorts the contents of a file, by default it sorts aphabettically.|[View](#sort)|
|DPF-03|`uniq`|The `uniq` command list only the unique values of a file, however, the file needs to be sorted first, as the `uniq` command only checks the lines subsequent to it, or directly under it. This is why people usually run `sort` and then pipes that stdout to `uniq`.|[View](#uniq)|
|DPF-04|`grep`|`grep` allows us to search for patterns within a file or whatever is parsed to its stdin.|[View](#grep)|
|DPF-05|`tr`|`tr` which stands for **tr**anslate, translates/modifies a string of characters to something else, it works on a character level, meaning 'ab' 'cd', a will be change to c and b will be change d. We can also remove characters using `-d`, as well as work with ranges.|[View](#tr)|
|DPF-06|`rev`|`rev` reverses a string.|[View](#rev)|
|DPF-07|`cut`|`cut` allows us to modify a string by cutting out byte, characters or fields for a specific range.|[View](#cut)|
|DPF-08|`sed`|The `sed` tool allows us to quickly execute commands on a file or stdin. Example of how the commands would work is `sed 'command1; command2; ...'` and they allow us to do things such as `delete lines` or `insert lines` or whatever other command is available to us.|[View](#sed)|

##### tee
```sh
    ping google.com 2>&1 | tee -a ping_info.txt
```

##### sort
```sh
    sort file.txt
     ↪ -r       |sorts contents of file in reverse order
     ↪ -n       |sorts contents in reverse order
     ↪ -c       |check whether contents of file is sorted & find unsorted elements
     ↪ -k       |column number sort data by a specific column
     ↪ -u       |checks unique values only
```

##### uniq
```sh
    sort file.txt | uniq
     ↪ _sort -u file.txt_
```

##### grep
```sh
    ls | grep -F "file.txt"
    ip addr show | grep -F "inet"
                 | grep -E "[a-z][A-Z][1-9]"
                    ↪ egrep "[a-z][A-Z][1-9]" 
```

##### tr
```sh
    echo "bash" | tr 'ba' 'di'
    echo "awesome" | tr 'a-z' 'A-Z'
    echo "Try removing the spaces inbetween" | tr -d ' '
```

##### rev
```sh
    echo 'Was it a cat I saw?' | rev
```

##### cut
```sh
    uptime | cut -b '2-9'
           | cut -c '2-9' # difference between b and c is c allows for more bytes as some character require 2 bytes or more
           | cut -d ' ' -f 1 
```

##### sed
```sh
    echo 'Hello Bash' | sed 's/Hello/Bye/g'
    echo 'Hello Bash' | sed 's/Hello/Bye/g'
```

<br>

##### &#8226; Shell Related Commands
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|SRC-01|`export`<br>`unset`|`export` allows us to set environment variables, while unset removes these variables.|[View](#export--unset)|
|SRC-02|'chsh'|Allows us to change our default shell. [Read More](./env_variables_cs.md) on the **Environment & Shell Variables** page.|[View](#chsh)|
|SRC-03|`alias`|This allows us to shorten or create more abbreviated commands, by setting an alias.|[View](#alias)|
|SRC-04|`set`|Allows us to control the behaviour of our shell.|[View](#set)|
|SRC-05|`shopt`|Much like `set`, this also allows us to alter the behaviour of our shell.|[View](#shopt)|
|SRC-06|`infocmp`|Shows the escape sequences for our terminal|[View](#infocmp)|
|SRC-07|`tput`|Allows us to use the easier form of `infocmp`_escape sequences_, example `setaf` instead of `\E[%?%p1%{8}%<%t3%p1%d%e%p1%{16}%<%t9%p1%{8}%-%d%e38;5;%p1%d%;m,`.|[View](#tput)|

##### export & unset
```sh
    export VARNAME='Hello, thiis has a typo'
    VARNAME="Hello, World!"
    unset VARNAME
```

##### chsh
```sh
    chsh -s /bin/bash
```


##### alias
```sh
    alias updateme='sudo apt update && sudo apt upgrade'
    alias ls ='ls --color=Auto'
    alias cp='cp -v'
    alias mv='mv -v'
    alias mkdir='mkdir -v'
```

##### set
```sh
    set -x          #Sets a function or behaviour
    set +x          #Unsets a function or behaviour
```

##### shopt
```sh
    shopt -t        #This closes a terminal after a single command has run
```

##### infocmp
```sh
    infocmp
```

##### tput
```sh
    echo "$(tput setaf 4)$(tput setab 5)Hello, World!$(tput sgr0)"
```

<br>

##### &#8226; User Management
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|||||

<br>

