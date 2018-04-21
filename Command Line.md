

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

# Manipulating files
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
- Overwrite a file
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

 "command to command" redirection.
> 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcwODI4NDcwNyw1OTk5NzQ4MTgsLTEwNz
I2NTUyNzgsMTQxNDc4NTc4MiwtMTU1MjY2OTM5NCwtNDc4Mjk0
ODQzLC0xMzExMDE4MzU2XX0=
-->