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
print "Hello %s" % (name)
print "The %s who %s %s!" % ("Knights", "say", "Ni")
```
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
### Formatting

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
### Convert to string
```python
str(2)
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
elsif something_else_true:
	# code 
else:
	# code
## Iteration
### For-loop
## List
### Append/Expand
### Comprehension list
## Dictionary
## Filter

# POO
## Initialize class


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIzOTc1MTIyNCw0NTY4MjQ1ODcsLTM2Nj
A2NTI1NCwtOTM2NDA1MTUxLC0xNTk0MTk1MTQ4LDE3Mzk1ODEy
NzAsLTEzODYzMzkyNzUsLTIwMzkyODk1MTEsOTc5NTUxODA4LC
01NjA4MjEyNDEsMjc2ODcwNTUyLDMwMTc4NjUyM119
-->