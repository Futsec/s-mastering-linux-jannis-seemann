<div align="center">
    <h3>Shell Expansions</h3>
    <p>
        <em>Cheatsheet on different kinds of Shell Expansions</em>
    </p>
</div>

<br>
<br>

> 💡 **Note on Word Splitting**:
> - _Wordsplitting is when bash uses the variable IFS to determine spaces, tabs, or line-breaks when a command is run._
> - _This is why we expand using quotes, as sometimes not using this can cause unforseen errors. Not only that, but when making file or folder names with spaces, without a space, this can create unintended files or folder if no quotes are around the name._


> 💡 **No Quotes vs Single Quotes vs Double Quotes**:
> - _cat $PWD/*.txt_
>   - _All Available shell expansion are being applied._
> - _cat '$PWD/*txt'_
>   - _All Expansion are disable, Wordsplitting is disabled._
> - _cat "$PWD/*.txt"_
>   - _Most expansion are disabled, but variable and parameter expansions are still enabled._

<br>

|#|Type of Expansion|Description|Example|
|:---|:---|:---|:---|
|EP-01|**Filename** Expansion|This is a file name.|[View](#filename)|
|EP-02|**~** Expansion<br>**~+** Expansion|This expands the home path directory, when adding a plus to it is can expand to you current working path.|[View](#tilde)|
|EP-03|**Variable** & **Parameter** Expansion|These expand variables such as PATH or HOME|[View](#variable--parameter)|
|EP-04|**Brace** Expansion||[View](#brace)|
|EP-05|**Command Substitution**|Allow for commands to to be run and expands its output.|[View](#command-substitution)|
