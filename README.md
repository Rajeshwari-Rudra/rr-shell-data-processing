# rr-shell-data-processing
Big data - shell data processing using Powershell and GitBash commands

## Powershell 
- mkdir - creates a new directory
- cd - changes the directory
- cd .. - changes to root directory
- ni - creates new item
- rm - removes an item
- ls - list the items
- ALT SPACE C -To close the window

## GitBash
- git clone repoUrl - clones the cloud repo to local machine
- git add remote origin repoUrl - adds remote folders to cloud repo
- git add . - adds the files
- git commit -m "initial commit" - commits the repo with message
- git push origin branchName - pushes the changes to that specific branchName
- cat - concatenate files and print on the standard output

## Creating a project 
- Start a new project, Right click on folder and select "Open PowerShell window here as administrator".
- Create a new subfolder by running a command "mkdir rr-shell-data-processing" where rr-shell-data-processing is subfolder.
- Change directory to your subfolder by cd "rr-shell-data-processing".
- Make an empty new items named as "README.md" and  as ".gitignore" using command "ni README.md" and "ni .gitignore".
- Find an interesting web page (http://shakespeare.mit.edu/julius_caesar/full.html (Links to an external site.)) and copy it.
- Use curl to return the page text. Hint: curl "http://shakespeare.mit.edu/julius_caesar/full.html"  
- Commands to return the next text by using curl and output to a file
```curl "yourlongurl" -O 
   curl "yourlongurl" -O "data.txt"
```
To request content from an HTTPS url,use the command:
```
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
```
- Then close the window in PowerShell. 

## To process the text data using Bash commands
* Transform each space ' ' into a return character '\12' (aka ASCII line feed) [2] 
``` 
  tr ' ' '\12' < data.txt
```
* Functionally, this "flat maps" each line into individual words. 
Pipe the output to sort (send the results of one command as input into another command)
```
tr ' ' '\12' < data.txt | sort
```
* Pipe the sorted output to uniq -c to count
```
 tr ' ' '\12' < data.txt | sort | uniq -c
 ```
* Pipe the reduced output to sort with -nr flag
```
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr
```
* To redirect the output to result.txt
```
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr > result.txt
```

## Text files:-
- Input file [data.txt](https://github.com/Rajeshwari-Rudra/rr-shell-data-processing/blob/master/data.txt)
- Output file [result.txt](https://github.com/Rajeshwari-Rudra/rr-shell-data-processing/blob/master/result.txt)
