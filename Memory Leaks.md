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

## Key config:

<kbd>space</kbd> : pause

  

<kbd>+</kbd>  <kbd>-</kbd> : small speed adjustment

<kbd>*</kbd>  <kbd>/</kbd> : big speed adjustment

<kbd>ESC</kbd> : quit program
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg5MzAyNDUzNywtNzI3NzkyMDI0LDE2NT
Y0OTI4LC0xOTY0NzkxMDgwXX0=
-->