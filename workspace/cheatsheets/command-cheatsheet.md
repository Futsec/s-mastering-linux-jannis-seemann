<div align="center">
    <h3>Command Cheatsheet</h3>
    <p>
        <em>A Linux command cheatsheet</em>
    </p>
</div>

<br>
<br>

#### 📂 File & Folder Management

|#|Command|Description|Example Link|#|Command|Description|Example Link|
|:---|:---|:---|:---|:---|:---|:---|:---|
|📂 File & Folder Management||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||


##### touch
_We use the touch command to create files, we can can create a signle or multiple amount of files._

```sh 
    touch ~/file.txt
    touch ~/file1.txt ~/file2.txt
    touch ~/file{1..9}.txt
```

##### mkdir
_We can us mkdir to create folders, either single or multiple, as well as entire folder structures._

```sh
    mkdir ~/folder
    mkdir ~/folder1 ~/folder2
    mkdir -p ~/folder/subfolder
```

##### mv
_The move command can both move and rename files._
     
```sh
    mv ~/file1 ~/Documents/
    mv ~/file1 ~/file2 ~/Document/
       ↪ <command> <location> <destination>
    mv ~/filee ~/filei
       ↪ <command> <old-name> <new-name>
```

##### cp
_This copies files, it can also copy a file with one name, and paste it as another name._

```sh
    cp ~/file ~/Documents/
    cp ~/file1 ~/file2 ~/Documents
       ↪ <command> <location> <destination></destination>
```

##### rm
_The remove command, removes files only, however it can remove directories if not careful._

```sh
    rm ~/file
    rm ~/file1 ~/file2
    rm -r ~/folder/file
```

##### rmdir
_Remove Direcctory is much like the `rm` command but for **empty** directories. If a directory is not empty, it will 
fail._

```sh    
    rmdir ~/folder
```

<br>

#### 🔍 Searching Folders & Files
##### ls 
_The list `ls` command is used to to view the contents of a directory._

```sh
    ls 
    ls -a
    ls -l
    ls -R
    ls -lah
```

##### tree
_`tree` is much like the `ls -R` command, however it outputs the folder structure in a nice easy to read tree like format._

```sh
    tree .
```
 
##### Globbing & Wildcards
_* | ** | ? | [1-9] are some of the globbing characters and we can using with commands, to perform tailored functions._

```sh
    echo ~/**/0[1-2]*/*.???
     ↪ *        |everything
     ↪ **       |recursive everything, includes folders
     ↪ ?        |any single char
     ↪ [1-9]    |range
```

##### find
_Use find to search for files in a specific directory, its a more sophisticated search function_

```sh
    find ~/Desktop -type d -empty -delete
    find . -name "file.txt"
    find /var/log/ -type f -size 1M
```

##### cat
_This concatenates a files, printing its contents to the terminal, we can also use globbing with this command._

```sh
    cat ~/file.txt
    cat ~/f* 
```

##### head
_This prints out the first 10 lines of a file, unless else specific._

```sh
    head ~/file.txt
    head -n 20 ~/file.txt
```

##### tail
_This is the same as the `head` command, but for the end of a fail._

```sh
    tail ~/file.txt
    tail -n 20 ~/file.txt
```

##### less
_less opens the content of a file into its own program, allowing us to view, search and read files easier._

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

#### ❓ File Infomation
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

#### 📈📉 Data Processing & Filtering
##### tee
_The `tee` command allows to redirect stdin to two places, example to the terminal and to a file._

```sh
    ping google.com 2>&1 | tee -a ping_info.txt
```

##### sort
_`Sort` sorts the contents of a file, by default it sorts aphabettically._

```sh
    sort file.txt
     ↪ -r       |sorts contents of file in reverse order
     ↪ -n       |sorts contents in reverse order
     ↪ -c       |check whether contents of file is sorted & find unsorted elements
     ↪ -k       |column number sort data by a specific column
     ↪ -u       |checks unique values only
```

##### uniq
_The `uniq` command list only the unique values of a file, however, the file needs to be sorted first, as the `uniq`
command only checks the lines subsequent to it, or directly under it. This is why people usually run `sort` and then 
pipes that stdout to `uniq`._

```sh
    sort file.txt | uniq
     ↪ _sort -u file.txt_
```

##### grep
_`grep` allows us to search for patterns within a file or whatever is parsed to its stdin._

```sh
    ls | grep -F "file.txt"
    ip addr show | grep -F "inet"
                 | grep -E "[a-z][A-Z][1-9]"
                    ↪ egrep "[a-z][A-Z][1-9]" 
```

##### tr
_`tr` which stands for **tr**anslate, translates/changes characters to something else, it works on a character level, 
meaning 'ab' 'cd', a will be change to c and b will be change d._

```sh
    echo "bash" | tr 'ba' 'di'
```
