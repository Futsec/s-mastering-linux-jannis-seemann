<div align="center">
    <h3>Command Cheatsheet</h3>
    <p>
        <em>A Linux command cheatsheet</em>
    </p>
</div>

<br>
<br>

<details>
    <summary>📂 File & Folder Management</summary>

|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|FFM-01|`touch`|We use the touch command to create files, we can can create single or multiple files.|[View](#touch)|
|FFM-02|`mkdir`|We can us mkdir to create folders, either single or multiple, as well as entire folder structures.|[View](#mkdir)|
|FFM-03|`mv`|The move command can both move and rename files.|[View](#mv)|
|FFM-04|`cp`|This copies files, it can also copy a file with one name, and paste it as another name.|[View](#cp)|
|FFM-05|`rm`|The remove command, removes files only, however it can remove directories if not careful.|[View](#rm)|
|FFM-06|`rmdir`|Remove Direcctory is much like the `rm` command but for **empty** directories. If a directory is not empty, it will fail.|[View](#rmdir)|

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
</details>

<br>

<details>
    <summary>🔍 Searching Files & Folders</summary>

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
    echo ~/**/0[1-2]*/*.???
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
</details>
 
<br>

<details>
    <summary>❓ File Information</summary>

|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|||||
|||||


##### wc
_`wc` returns the amount of either lines, words or chars/bytes within a file._

```sh
    wc ~/file.txt
    wc -lwc ~/file.txt 
     ↪ -l       |lists the amount of lines
     ↪ -w       |list the amount of words
     ↪ -c       |lists the amount of chars, or bytes of the file
```

##### du
_Disk Usage shows how much disk usage the file is using, there are specific units that this is measured in._

```sh
    du ~/file.txt 
    du -h file.txt
     ↪ -s       |display only a total for each argument
     ↪ -h       |display in human-readable format
     ↪ -k       |display block size
```
</details>

<details>
    <summary>Data Processing & Filtering</summary>
    
|#|Command|Description|Example Link|
|:---|:---|:---|:---|
|DPF-01|`tee`|The `tee` command allows to redirect stdin to two places, example to the terminal and to a file.|[View](#tee)|
|DPF-02|`sort`|`Sort` sorts the contents of a file, by default it sorts aphabettically.|[View](#sort)|
|DPF-03|`uniq`|The `uniq` command list only the unique values of a file, however, the file needs to be sorted first, as the `uniq` command only checks the lines subsequent to it, or directly under it. This is why people usually run `sort` and then pipes that stdout to `uniq`.|[View](#uniq)|
|DPF-04|`grep`|`grep` allows us to search for patterns within a file or whatever is parsed to its stdin.|[View](#grep)|
|DPF-05|`tr`|`tr` which stands for **tr**anslate, translates/changes characters to something else, it works on a character level, meaning 'ab' 'cd', a will be change to c and b will be change d.|[View](#tr)|

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
```
</details>
