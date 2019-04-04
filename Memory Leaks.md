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

## LLDB
```bash
lldb myprogram
r #run
b main
n 
n	#or enter
s #go to function
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQxNzUxNTk0MiwxNjU2NDkyOCwtMTk2ND
c5MTA4MF19
-->