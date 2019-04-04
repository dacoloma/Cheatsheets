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
n #next line 
n #or enter
s #go to function
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcyNzc5MjAyNCwxNjU2NDkyOCwtMTk2ND
c5MTA4MF19
-->