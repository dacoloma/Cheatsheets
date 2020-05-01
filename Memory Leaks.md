# Memory leaks
## Valgrind
If you run a program like this : 
```bash
$ myprog arg1 arg2
```
type this to use valgrind : 
```bash
$ valgrind --leak-check=yes myprog arg1 arg2
```	

## Leaks command (OSx)
Put this code in main.c : 
```C
__attribute__((destructor)) int end()  
{  
	while (1);  
}
```
and run in terminal: 
```bash
$ while true; do leaks corewar; sleep 1; clear;  done
```
## LLDB
```bash
lldb myprogram
r #run
b main
n #next line 
n #or enter
s #go to function
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NTQ3NzA1OTUsNjk5NTMzNTk4LC03Mj
c3OTIwMjQsMTY1NjQ5MjgsLTE5NjQ3OTEwODBdfQ==
-->