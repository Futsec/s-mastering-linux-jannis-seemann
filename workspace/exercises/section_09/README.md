<div align="center">
    <h3>Section &mdash; 9</h3>
    <p>
        <em>Pipes & Data Processing through command chaining</em>
    </p>
</div>

<br>
<br>

### Task Requirements
For this exercise, you need the log file. In order to download this, please just click on the following link:
=> https://downloads.codingcoursestv.eu/055%20-%20bash/log/access.log

```sh
    wget https://downloads.codingcoursestv.eu/055%20-%20bash/log/access.log -O access.log
```

> 💡**NOTE**: 
> _Btw, in case you want to download this file directly into your VM, you can use wget to do so._
> _Please note that you might have to install it through sudo apt install wget / sudo dnf install wget first though._

##### Exercise Material: Webserver Log File Analysis

1. How many requests have downloaded .zip-files?
2. How many different .zip-files have been downloaded?

###### Tip:
- You can detect Firefox users by their user agent, it contains "Firefox/".
- You cant fully parse the logfile as a logfile, you might have to treat it as a line of text, and for example match the user agent on the whole line of text.
