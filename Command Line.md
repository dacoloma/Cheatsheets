# Navigation
## Change directory
```bash
$ cd 
$ cd Desktop/
$ cd ..
```
Go to previous directory
```bash
cd -
```
## List files 
- Current directory
```bash 
$ ls
```
- Specific directory 
```bash 
$ ls Desktop/
```
- With options
```bash
$ ls -a
```
> -a : list all contents of a directory, including hidden files and directories
> -l : list all contents in long format with access rights, last modification date...
> -t : order by time (last modification date)

- Combination of options 
```bash
$ ls -alt
```
## Print working directory
```bash
$ pwd
```

# Manipulating files/directories
## Create file
```bash
$ touch myFile
```
## Create directory
```bash
$ mkdir myDirectory
```
## Copy file
- Copy a file in a directory
```bash
$ cp fichier.txt myDirectory/
```
- Copy a file from a directory in another directory
```bash
$ cp myDirectory1/fichier.txt myDirectory2/
```
- Copy many files 
```bash
$ cp fichier1.txt fichier2.txt myDirectory/
```
- Wildcard
```bash
$ cp *.txt myDirectory2/
$ cp m*.txt myDirectory3/
```
## Word counting
```bash
$ wc hello.txt
>>      1     1     6 hello.txt
```
> Return the number of lines, words, and characters
## Move/Rename
- Move a file 
```bash
$ mv myfile.txt myDirectory/
```
- Rename a file
```bash
$ mv fichier.txt myFile.txt
```

## Remove file/directory
- Remove a file 
```bash
$ rm myFile.txt
```
- Remove a directory 
```bash
$ rm -r myDirectory/
```  
> Careful when using this command, especially with the options combined -rf

# Redirecting Input/Output

## Print to terminal
- Print a string
```bash
$ echo "Hello"
>> Hello
``` 
- Output content of a file to the terminal 
```bash
$ cat  hello.txt
>> Hello World!
``` 
- Redirect to a file 
```bash
$ echo "Hello" > myfile.txt
``` 
## Redirection
- Create/Overwrite a file
```bash
$ echo "Hello" > myfile.txt
$ cat  myfile.txt
>> Hello
$ cat file1.txt > file2.txt
``` 

- Append stdout to a file
```bash
$ cat file1.txt >> file2.txt
```  

- Pipe : | (OSx : Shift + alt + L)
> "command to command" redirection.
```bash
$ cat hello.txt | wc
>>      1     1     6 
```
- Combination
```bash
$ cat ListOfWords.txt | sort > SortedList.txt
```
- Sort
```bash
$ sort MyFileToSort.txt
```
- Filter
	>Print unique elements in a list 
```bash
$ uniq list.txt
```
## Search
Grep : Global regular expression print
- Search for lines of a file matching a pattern and return the lines
```bash
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
```bash
$ source ~/.bash_profile
```
## Environment variable
Go to ~/.bash_profile and write : 
```
export USER="Jane Doe"
```
Save and quit, then type : 
```bash
$ source ~/.bash_profile
```
To check, type : 
```
echo $USER
```

- find 
- file
- diff / patch
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMDEwMDY0NjIsLTE3MDMxMzgyNzIsMT
IyNTA0MjcxMCwtMTA3MzU1NTMyMywtMTEyMTcyNDIwMiwtNjUz
MzE1MDk2LDE3Nzk0NDU1MDUsMjEyMDI4NTEyMCwtMTYxMjQ4OT
I2MiwxNTU1MzQ4MDM4LDcwNDc0NTI4MSwyMTQwNjkwODE4LC0x
Njc1MjE4NTYyLDEwMzg1OTYxNywtOTgyODE3MDUyLC0xMzEyNz
Y2Mzg0LDE5NTY2MzM5NjcsNTk5OTc0ODE4LC0xMDcyNjU1Mjc4
LDE0MTQ3ODU3ODJdfQ==
-->