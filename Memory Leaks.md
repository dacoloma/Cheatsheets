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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NjQ3OTEwODBdfQ==
-->