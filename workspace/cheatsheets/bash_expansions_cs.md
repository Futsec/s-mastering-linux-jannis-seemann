<div align="center">
    <h3>Shell Expansions</h3>
    <p>
        <em>Cheatsheet on different kinds of Shell Expansions</em>
    </p>
</div>

<br>
<br>

> 💡 **Note on Word Splitting**:
> - _Wordsplitting is when bash uses the variable known as `IFS` to determine spaces, tabs, or line-breaks when a command is run._
> - _This is why we expand using double quotes, as sometimes not using this can cause unforseen errors. Not only that, but when making file or folder names with spaces, can create unintended files or folder if NO quotes are enclosing the name._


> 💡 **No Quotes vs Single Quotes vs Double Quotes**:
> - _cat $PWD/*.txt_
>   - _All Available shell expansionare being applied._
> - _cat '$PWD/*txt'_
>   - _All Expansions are disable, Wordsplitting is disabled._
> - _cat "$PWD/*.txt"_
>   - _Most expansions are disabled, such as filename, tilde and brace expansions, however variable and parameter expansions are still enabled._

<br>

|#|Type of Expansion|Description|Example|
|:---|:---|:---|:---|
|EP-01|**Filename** Expansion|This is a file name.|[View](#filename-expansion)|
|EP-02|**Tilde** Expansion|This expands the home path directory, when adding a plus to it is can expand to you current working path.|[View](#tilde-expansion)|
|EP-03|**Variable** & **Parameter** Expansion|These expand variables such as PATH or HOME|[View](#variable--parameter-expansion)|
|EP-04|**Brace** Expansion||[View](#brace-expansion)|
|EP-05|**Command Substitution**|Allow for commands to to be run and expands its output.|[View](#command-substitution)|

<br>
<br>

##### Filename Expansions
```sh
    ls *
    echo ?.txt
```

##### Tilde Expansion
```sh
    cd ~
    echo ~
     ↪ /home/futsec/
    echo ~+
     ↪ /home/futsec/workspace
```

##### Variable & Parameter Expansion
```sh
    echo "${PATH}"
    echo "${USER}"
```

##### Brace Expansion
```sh

```

##### Command Substitution
```sh
    echo "$(tput setaf 7)$(tput setab 3)$Hello, World!(tput sgr0)"
```
