<div align="center">
    <h3>Environment & Shell Variables</h3>
    <p>
        <em>A Linux Environment & Shell Variable Cheatsheet</em>
    </p>
</div>

<br>
<br>

> ⁉️  **Notes on `export` & `unset`**: 
> - _We can set and unset our own custom environment variables using_ [`export 🔍`](#export) _and_ [`unset 🔍`](#unset).
> - _To overwrite an existing variable, simply assign a new value to the variable, like so `VAR='New Value'`._
> - _Environment Variables should **ALWAYS** be in uppercase, doesn't need to be but follow best practices._


> ‼️ **Notes on Bash Expansions: `${...}` vs `$(...)`**:
> - _For now we know of two expressions syntaxes, Variable Expansion denoted by "${...}" & Command Substitution denoted by "$(...)"._
> - _Variable Expansion, is used to expand variables or parameters such as "${PATH}"._
> - _Command Substitution, is used to run commands and substitute its output, such "$(tput setaf 5)Hello"_

<br>

|#|Variable|Description|Example|
|:---|:---|:---|:---|
|**&#8226; Environment Variables**||||
|EV-01|`env`|This command displays your environment variables.|[View](#env)<br>`os:~$ env`|
|EV-02|`HOME`|Stores the currents users home directory path, /home/username or /users/username.|[View](#home)<br>`os:~$ echo "${HOME}"`|
|EV-03|`PWD`<br>`OLDPWD`|Much like the `pwd` command, it prints the current working directory, but one is a command and the other is a variable, `pwd` uses this variable to print out the path.<br>`OLDPWD`, prints the old working  directory the user was in.|[View](#pwd)<br>`os:~$ echo "${PWD}"`<br>`os:~$ echo "${OLDPWD}"`|
|EV-04|`USER`|Outputs the current Unix username of the user, which is represented in all lower-case letters.|[View](#user)<br>`os:~$ echo "${USER}"`|
|EV-05|`PATH`|This variable stores a list of directories used for executing programs, order matters, as it is searched from left to right. Mutliple directories are seperated by colons ':'.|[View](#path)<br>os:~$ echo "${PATH}"|
|EV-06|`SHELL`|Shows the default shell, and not the current working shell. An example being if your default shell is `/bin/zsh` and you running bash, `SHELL` will still output `/bin/zsh`<br>You can view the list of shells, by concatenating the shells file in `/etc/shells`.<br>To set a certain shell as default, you can use `chsh -s /bin/bash`.|[View](#shell)<br>os:~$ echo "${SHELL}"|
|**&#8226; Shell Variables**||||
|SV-01|`PS1`|This is your `Prompt String` shell variable, basically the text you see in your terminal before you start typing.<br>You would use commands such as `infocmp`_escape sequences_, `tput` inorder to customize your prompt.|[View](#ps1)<br>`username@host:directory\$ ...`|

<br>
<br>

##### env 

```sh
    env
```

##### HOME

```sh
    echo "${HOME}"
```

##### PWD

```sh
    echo "${PWD}"
    echo "${OLDPWD}"
    cd "${OLDPWD}"          #This allow you to navigate back to your old working directory.
```

##### USER

```sh
    echo "${USER}"
```

##### PATH

```sh
    echo "${PATH}"
    PATH="${PATH}:/new/path"            #Adding a temporary path to the path variable
```
> 💡 **NOTE**: _To make a new path permanent we can edit the `.bashrc` by adding the same syntax as seen above._"_PATH="${PATH}:/new/path"_"

##### SHELL

```sh
    echo "${SHELL}"
    cat /etc/shells         #View the list of shells on the system
    chsh -s /bin/bash       #Set a default shell
```

##### PS1
```sh
    echo "${PS1}"
```

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### 

##### export

```sh
    export VARNAME='Hello World!'
    VARNAME='Hello Bash!'           #This modifies the values of the variable.
```

##### unset

```sh
    unset VARNAME
```
