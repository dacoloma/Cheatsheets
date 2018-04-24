# Syntax
## Print
### V2 & V3
Python V3 | Python V2
-------- | -----
`print("test")` | `print "test"`
`print("test",x)` | `print "test",x`
`print("test number %d" % x)` | `print "test number %d" % x`

### Formatting
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
## Comment
```python
# Single line comment
''' 
Multi
line 
comment
'''
```
> Simple quote (') can be replaced by double quotes (")

## Integer
### Convert to string
```python
str(2)
```

## String
### Length
```python
len(my_string)
```
### Downcase
```python
my_string.lower()
```
### Upcase
```python
my_string.upper()
```




## Function
### Define/Call a simple function
```python
def my_function:
	# code
my_function()
```
> Indent code when defining function. 

### Define a function with argument
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
### Anonymous function

## Date & Time
### Import library
```python
from datetime import datetime
```
### Methods
#### Current datetime
```python
datetime.now()
```
#### Extract data (month, year, day, minutes...)
```python
datetime.now().month
datetime.now().year
datetime.now().day
datetime.now().minute
# etc.
```
> in python shell IDLE, type `help(datetime)`for more information

## Conditional statements
```python
if something_true:
	# code
elif something_else_true:
	# code 
else:
	# code
```
## List
```python
list = ['a','b','c']
```
### Append/Expand/Insert
```python
list.append('d')
list.expand('f','g')
list.insert(4,'e')
```
### Slice
```python
list[x:y:z]
```
> x : start index
> y : stop index (exclude)
> z : step (optional)


### Comprehension list
## Iteration
### For-loop
Looping a list : `list = [2,5,4,8,5]`
```python
for number in list:
	# code
```
## Dictionary
## Filter

# POO
## Initialize class


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2MDkzMTk3OCwxMTIzNDA3ODYzLC04Nj
A4OTQ5NzMsMTc3OTI0MTM3MCwtMjEwMTY3NzUxOCwxNjM4NTIw
OTAsNDI0MjQzMjY3LDQ1NjgyNDU4NywtMzY2MDY1MjU0LC05Mz
Y0MDUxNTEsLTE1OTQxOTUxNDgsMTczOTU4MTI3MCwtMTM4NjMz
OTI3NSwtMjAzOTI4OTUxMSw5Nzk1NTE4MDgsLTU2MDgyMTI0MS
wyNzY4NzA1NTIsMzAxNzg2NTIzXX0=
-->