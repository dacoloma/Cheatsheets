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
## Iteration
### For-loop
## List
```python
list = ['a','b','c']
```
### Append/Expand
```python
list.append('d')
list.expand('e','f','g')
```
### Slice
```python
list[x
### Comprehension list
## Dictionary
## Filter

# POO
## Initialize class


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTczNjc0NDIyNiwtODYwODk0OTczLDE3Nz
kyNDEzNzAsLTIxMDE2Nzc1MTgsMTYzODUyMDkwLDQyNDI0MzI2
Nyw0NTY4MjQ1ODcsLTM2NjA2NTI1NCwtOTM2NDA1MTUxLC0xNT
k0MTk1MTQ4LDE3Mzk1ODEyNzAsLTEzODYzMzkyNzUsLTIwMzky
ODk1MTEsOTc5NTUxODA4LC01NjA4MjEyNDEsMjc2ODcwNTUyLD
MwMTc4NjUyM119
-->