<div align="center">
    <h3>Enviroment Variables</h3>
    <p>
        <em>A Linux Enviroment Variable Cheatsheet</em>
    </p>
</div>

<br>
<br>

> 💡 **QUICK NOTE**: 
> _We can set and unset our own custom environment variables using_ [`export 🔍`](#export) _and_ [`unset 🔍`](#unset).
> _To overwrite an existing variable, simply assign a new value to the variable, like so `VAR='New Value'`._
> _Environment Variables should **ALWAYS** be in uppercase, doesn't need to be but follow best practices._

<br>

|#|Variable|Description|Example|
|:---|:---|:---|:---|
|EV-01|`env`|This command displays your enviroment variables.|[View](#env)<br>`os:~$ env`|
|EV-02|`HOME`|Stores the currents users home directory path, /home/username or /users/username.|[View](#home)<br>`os:~$ echo "${HOME}"`|
|EV-03|`PWD`<br>`OLDPWD`|Much like the `pwd` command, it prints the current working directory, but one is a command and the other is a variable, `pwd` uses this variable to print out the path.<br>`OLDPWD`, prints the old working  directory the user was in.|[View](#pwd)<br>`os:~$ echo "${PWD}"`<br>`os:~$ echo "${OLDPWD}"`|
|EV-04|`USER`|Outputs the current Unix username of the user, which is represented in all lower-case letters.|[View](#user)<br>`os:~$ echo "${USER}"`|
|EV-05|`PATH`|This variable stores a list of directories used for executing programs, order matters, as it is searched from left to right. Mutliple directories are seperated by colons ':'.|[View](#path)<br>os:~$ echo "${PATH}"|
|EV-06|`SHELL`|Shows the default shell, and not the current working shell. An example being if your default shell is `/bin/zsh` and you running bash, `SHELL` will still output `/bin/zsh`|[View](#shell)<br>os:~$ echo "${SHELL}"|
|EV-07|`PS1`|This is you `Prompt String` variable, basically the text you see in your terminal.|[View](#ps1)|
|EV-08|``||[View](#)|
|EV-09|``||[View](#)|
|EV-10|``||[View](#)|
|EV-11|``||[View](#)|
|EV-12|``||[View](#)|
|EV-13|``||[View](#)|
|EV-14|``||[View](#)|
|EV-15|``||[View](#)|
|EV-16|``||[View](#)|
|EV-17|``||[View](#)|
|EV-18|``||[View](#)|
|EV-19|``||[View](#)|
|EV-20|``||[View](#)|

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
> 💡 **NOTE**: _To make a new path permanent we can edit the `.bashrc` by adding the same syntax as seen above._
> _PATH="${PATH}:/new/path"

##### SHELL

```sh
    echo "${SHELL}"
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
