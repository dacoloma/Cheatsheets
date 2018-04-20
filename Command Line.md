# Navigation
## Change directory
```
$ cd 
$ cd Desktop/
$ cd ..
```
## List files 
Current directory
```
$ ls
```
Specific directory 
```
$ ls Desktop/
```
With options
```
$ ls -a
```
> -a : list all contents of a directory, including hidden files and directories
> -l : list all contents in long format with access rights, last modification date...
> -t : order by time (last modification date)

Combination of options 
```
$ ls -alt
```
## Print working directory
```
$ pwd
```

# Manipulating files
## Create file
```
$ touch myFile
```
## Create directory
```
$ mkdir myDirectory
```
## Copy file
Copy a file in a directory
```
$ cp fichier.txt myDirectory/
```
Copy a file from a directory in another directory
```
$ cp myDirectory1/fichier.txt myDirectory2/
```
Copy many files 
```
$ cp fichier1.txt fichier2.txt myDirectory/
```
Wildcard
```
$ cp *.txt myDirectory2/
$ cp m*.txt myDirectory3/
```
## Move/Rename
Move a file 
```
$ mv myfile.txt myDirectory/
```
Rename a file
```
$ mv fichier.txt myFile.txt
```

## Remove file/directory
Remove a file 
```
$ rm myFile.txt
```
Remove a directory 
```
$ rm -r myDirectory/
```  

> Careful when using this command, especially with the options combined -rf

# Redirecting Input/Output

## Print to terminal
Print a string
```
$ echo "Hello"
>> Hello
``` 
Output content of a file to the terminal 
```
$ cat  hello.txt
>> Hello World!
``` 
Redirect to a file 
```
$ echo "Hello" > myfile.txt
``` 
## Redirection
Overwrite a file
```
$ echo "Hello" > myfile.txt
$ cat  myfile.txt
>> Hello
$ cat file1.txt > file2.txt
``` 

Append stdout to a file
```
$ cat file1.txt >> file2.txt
```  

# Pipe : | 
> OSx : Shift + alt + L

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1NTI2NjkzOTQsLTQ3ODI5NDg0MywtMT
MxMTAxODM1Nl19
-->