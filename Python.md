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
> %f
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
eyJoaXN0b3J5IjpbNDI0MjQzMjY3LDQ1NjgyNDU4NywtMzY2MD
Y1MjU0LC05MzY0MDUxNTEsLTE1OTQxOTUxNDgsMTczOTU4MTI3
MCwtMTM4NjMzOTI3NSwtMjAzOTI4OTUxMSw5Nzk1NTE4MDgsLT
U2MDgyMTI0MSwyNzY4NzA1NTIsMzAxNzg2NTIzXX0=
-->