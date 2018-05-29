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
## Search & Replace
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

Sed : Stream editor 
```bash
$ sed 's/snow/rain/' forests.txt
$ sed 's/snow/rain/g' forests.txt
```
Find specific pattern in files and replace whole line by another one
```bash
$ grep -rl 'pattern' . | xargs sed -i '' -e 's/.*pattern.*/new_string/g'
```
> `-i` : for Mac users, specify the argument `''` 
# Environment
## Alias
Go to ~/.bash_profile and write : 
```bash
alias myAlias="my_new_shortcut"
```
Save and quit, then type : 
```bash
$ source ~/.bash_profile
```
## Environment variable
Go to ~/.bash_profile and write : 
```bash
export USER="Jane Doe"
```
Save and quit, then type : 
```bash
$ source ~/.bash_profile
```
To check, type : 
```bash
echo $USER
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbODk1NDk1NzAyLDE3MDAyNDYwOTQsLTIwNT
IxMzUxNzksMTk0MTg3Mzg4NSwtMTcwMzEzODI3MiwxMjI1MDQy
NzEwLC0xMDczNTU1MzIzLC0xMTIxNzI0MjAyLC02NTMzMTUwOT
YsMTc3OTQ0NTUwNSwyMTIwMjg1MTIwLC0xNjEyNDg5MjYyLDE1
NTUzNDgwMzgsNzA0NzQ1MjgxLDIxNDA2OTA4MTgsLTE2NzUyMT
g1NjIsMTAzODU5NjE3LC05ODI4MTcwNTIsLTEzMTI3NjYzODQs
MTk1NjYzMzk2N119
-->