<div align="center">
    <h3>Enviroment Variables</h3>
    <p>
        <em>A Linux Enviroment Variable Cheatsheet</em>
    </p>
</div>

<br>
<br>

> 💡 **QUICK NOTE**: 
> _We can set and unset our own custom environment variables using [`export🔍`](#export) and [unset🔍](#unset)._

|#|Variable|Description|Example|
|:---|:---|:---|:---|
|EV-01|`env`|This command displays your enviroment variables.|[View](#env)<br>`os:~$ env`|
|EV-02|`HOME`|Stores the currents users home directory path, /home/username or /users/username.|[View](#home)<br>`os:~$ echo "${HOME}"`|
|EV-03|`PWD`<br>`OLDPWD`|Much like the `pwd` command, it prints the current working directory, but one is a command and the other is a variable, `pwd` uses this variable to print out the path.<br>`OLDPWD`, prints the old working  directory the user was in.|[View](#pwd)<br>`os:~$ echo "${PWD}"`<br>`os:~$ echo "${OLDPWD}"`|
|EV-04|`USER`|Outputs the current Unix username of the user, which is represented in all lower-case letters.|[View](#user)<br>`os:~$ echo "${USER}"`|
|EV-05|`env`||[View](#env)|
|EV-06|`env`||[View](#env)|
|EV-07|`env`||[View](#env)|
|EV-08|`env`||[View](#env)|
|EV-09|`env`||[View](#env)|
|EV-10|`env`||[View](#env)|
|EV-11|`env`||[View](#env)|
|EV-12|`env`||[View](#env)|
|EV-13|`env`||[View](#env)|
|EV-14|`env`||[View](#env)|
|EV-15|`env`||[View](#env)|
|EV-16|`env`||[View](#env)|
|EV-17|`env`||[View](#env)|
|EV-18|`env`||[View](#env)|
|EV-19|`env`||[View](#env)|
|EV-20|`env`||[View](#env)|

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
    cd "${OLDPWD}" # This allow you to navigate back to your old working directory.
```

##### USER

```sh
    echo "${USER}"
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

##### 

##### 

##### 

##### export

```sh
    
```

##### unset

```sh

```
