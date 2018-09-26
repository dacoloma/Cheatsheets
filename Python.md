# Python
## Syntax
### Print
#### V2 & V3
Python V3 | Python V2
-------- | -----
`print("test")` | `print "test"`
`print("test",x)` | `print "test",x`
`print("test number %d" % x)` | `print "test number %d" % x`

#### Formatting
```python
name = "Mike"
print("Hello %s" % name)
print("The %s who %s %s!" % "Knights", "say", "Ni")
print("%d" % 4)
```
> %s : string format
> %d : integer format
> %02d : print at least 2 digits
> %.2f : float format. Print 2 digits after comma
### Comment
```python
# Single line comment
''' 
Multi
line 
comment
'''
```
> Simple quote (') can be replaced by double quotes (")

### Integer
#### Convert to string
```python
str(2)
```

### String
#### Length
```python
len(my_string)
```
#### Downcase
```python
my_string.lower()
```
#### Upcase
```python
my_string.upper()
```




### Function
#### Define/Call a simple function
```python
def my_function:
	# code
my_function()
```
> Indent code when defining function. 

#### Define a function with argument
```python
def my_function(x):
	# code
my_function(my_var)
```
... and return something
```python
def my_function(x):
	# code
	return something
my_function(my_var)
```
#### Anonymous function

### Date & Time
#### Import library
```python
from datetime import datetime
```
#### Methods
##### Current datetime
```python
datetime.now()
```
##### Extract data (month, year, day, minutes...)
```python
datetime.now().month
datetime.now().year
datetime.now().day
datetime.now().minute
# etc.
```
> in python shell IDLE, type `help(datetime)`for more information

### Conditional statements
```python
if something_true:
	# code
elif something_else_true:
	# code 
else:
	# code
```
### List
#### Declare a list
```python
list = ['a','b','c']
```
#### Declare quickly a list of numbers 
```python
numbers = range(X,Y,Z)
```
> X: start number
> Y: stop number (exclude)
> Z: step (default = 1)

Quicker way
```python
numbers = range(10)
```
> [0,1,2,3,4,5,6,7,8,9]

### Append/Expand/Insert
```python
list.append('d')
list.expand('f','g')
list.insert(4,'e')
```
> You can concatenate 2 lists the same way you would do for string concatenation
### Slice
```python
list[x:y:z]
```
> x : start index
> y : stop index (exclude)
> z : step (default = 1)

### Sort
```python
list.sort()
```
### Delete
#### By index
```python
list.pop(1)
```
> Return the removed element
```python
del(list[1])
```
> Doesn't return anything

#### By value
```python
list.remove('b')
```
> Doesn't return anything

### Join
```python
letters = ['a', 'b', 'c', 'd']
print " ".join(letters)
```
> a b c d

### Control flow
```python
if 'h' in letters:
	# code
if 'h' not in letters:
	# code 
```
### Comprehension list
## Iteration
### For-loop
 `list = [2,5,4,8,5]`
#### Looping over a list 
```python
for number in list:
	# code
```
> Same way for iterating over a string
#### Looping n times
```python
for i in range(n):
	# code
```
### While-loop
```python
while condition:
	# code

while condition:
	# code
else:
	# code
```
## Dictionary
### Define a dictionary
```python
my_dict = {
	key1 = value1
	key2 = value2
}
```
### Add a new key 
```python
my_dict[key3]=value3
```
## Filter

# POO
## Initialize class


<!--stackedit_data:
eyJoaXN0b3J5IjpbNzQyMzg2OTQyLC03MTkyNzgxNTQsLTEyOT
YwNDkxOSwxOTkxNTYzNzg3LC0xNjU5ODc3NCwxNTA4NDM2MjIz
LC02MjczNjA1MjksLTg4MjUxMjAwNywxNjQ0ODAxOTA2LC0xMD
A5Nzg4NjQ3LDI5MjMwNzQwNiwtMTk1MjA2MTEzOSwxOTU1NDA1
NzEyLC03OTYzNjI5NjAsMTEyMzQwNzg2MywtODYwODk0OTczLD
E3NzkyNDEzNzAsLTIxMDE2Nzc1MTgsMTYzODUyMDkwLDQyNDI0
MzI2N119
-->