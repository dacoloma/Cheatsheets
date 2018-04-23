

# Navigation
## Change directory
```shell
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
- Grep : Global regular expression print
> Searches files for lines that match a pattern 
```shell
```
grep Mount mountains.txt
```
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEyNjAxMDIzNSwyMTQwNjkwODE4LC0xNj
c1MjE4NTYyLDEwMzg1OTYxNywtOTgyODE3MDUyLC0xMzEyNzY2
Mzg0LDE5NTY2MzM5NjcsNTk5OTc0ODE4LC0xMDcyNjU1Mjc4LD
E0MTQ3ODU3ODIsLTE1NTI2NjkzOTQsLTQ3ODI5NDg0MywtMTMx
MTAxODM1Nl19
-->