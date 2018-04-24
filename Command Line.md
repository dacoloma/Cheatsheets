

# Navigation
## Change directory
```bash
$ cd 
$ cd Desktop/
$ cd ..
```
## List files 
- Current directory
```shell 
$ ls
```
- Specific directory 
```shell 
$ ls Desktop/
```
- With options
```shell
$ ls -a
```
> -a : list all contents of a directory, including hidden files and directories
> -l : list all contents in long format with access rights, last modification date...
> -t : order by time (last modification date)

- Combination of options 
```shell
$ ls -alt
```
## Print working directory
```shell
$ pwd
```

# Manipulating files/directories
## Create file
```shell
$ touch myFile
```
## Create directory
```shell
$ mkdir myDirectory
```
## Copy file
- Copy a file in a directory
```shell
$ cp fichier.txt myDirectory/
```
- Copy a file from a directory in another directory
```shell
$ cp myDirectory1/fichier.txt myDirectory2/
```
- Copy many files 
```shell
$ cp fichier1.txt fichier2.txt myDirectory/
```
- Wildcard
```shell
$ cp *.txt myDirectory2/
$ cp m*.txt myDirectory3/
```
## Word counting
```shell
$ wc hello.txt
>>      1     1     6 hello.txt
```
> Return the number of lines, words, and characters
## Move/Rename
- Move a file 
```shell
$ mv myfile.txt myDirectory/
```
- Rename a file
```shell
$ mv fichier.txt myFile.txt
```

## Remove file/directory
- Remove a file 
```shell
$ rm myFile.txt
```
- Remove a directory 
```shell
$ rm -r myDirectory/
```  
> Careful when using this command, especially with the options combined -rf

# Redirecting Input/Output

## Print to terminal
- Print a string
```shell
$ echo "Hello"
>> Hello
``` 
- Output content of a file to the terminal 
```shell
$ cat  hello.txt
>> Hello World!
``` 
- Redirect to a file 
```shell
$ echo "Hello" > myfile.txt
``` 
## Redirection
- Create/Overwrite a file
```shell
$ echo "Hello" > myfile.txt
$ cat  myfile.txt
>> Hello
$ cat file1.txt > file2.txt
``` 

- Append stdout to a file
```shell
$ cat file1.txt >> file2.txt
```  

- Pipe : | (OSx : Shift + alt + L)
> "command to command" redirection.
```shell
$ cat hello.txt | wc
>>      1     1     6 
```
- Combination
```shell
$ cat ListOfWords.txt | sort > SortedList.txt
```
- Sort
```shell
$ sort MyFileToSort.txt
```
- Filter
	>Print unique elements in a list 
```shell
$ uniq list.txt
```
## Search
Grep : Global regular expression print
- Search for lines of a file matching a pattern and return the lines
```shell
$ grep Mount mountains.txt
$ grep -i Mount mountains.txt
$ grep -rl Mount my_directory/
```
> -i : case insensitive 
> -r : return all the filenames with lines that match the pattern (even in subdirectories)
> -l : return list of filename that match the pattern

Sed : Stream editor ('find and replace')
```
$ sed 's/snow/rain/' forests.txt
$ sed 's/snow/rain/g' forests.txt
```
# Environment
## Alias
Go to ~/.bash_profile and write : 
```
alias myAlias="my_new_shortcut"
```
Save and quit, then type : 
```shell
$ source ~/.bash_profile
```
## Environment variable
Go to ~/.bash_profile and write : 
```
export USER="Jane Doe"
```
Save and quit, then type : 
```shell
$ source ~/.bash_profile
```
To check, type : 
```
echo $USER
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5MzY4MjY5OSwtMTA3MzU1NTMyMywtMT
EyMTcyNDIwMiwtNjUzMzE1MDk2LDE3Nzk0NDU1MDUsMjEyMDI4
NTEyMCwtMTYxMjQ4OTI2MiwxNTU1MzQ4MDM4LDcwNDc0NTI4MS
wyMTQwNjkwODE4LC0xNjc1MjE4NTYyLDEwMzg1OTYxNywtOTgy
ODE3MDUyLC0xMzEyNzY2Mzg0LDE5NTY2MzM5NjcsNTk5OTc0OD
E4LC0xMDcyNjU1Mjc4LDE0MTQ3ODU3ODIsLTE1NTI2NjkzOTQs
LTQ3ODI5NDg0M119
-->