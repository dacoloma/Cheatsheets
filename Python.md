# Syntax
## Print
Python V3
```python
print("test")
print("test",x)
```
Python V2
```python
print "test"
print "test",x
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
## String
### Methods
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
#### Convert to string
```python
str(2)
```
### Formatting
```python
name = "Mike"
print "Hello %s" % (name)
print "The %s who %s %s!" % ("Knights", "say", "Ni")
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
eyJoaXN0b3J5IjpbLTE1OTQxOTUxNDgsMTczOTU4MTI3MCwtMT
M4NjMzOTI3NSwtMjAzOTI4OTUxMSw5Nzk1NTE4MDgsLTU2MDgy
MTI0MSwyNzY4NzA1NTIsMzAxNzg2NTIzXX0=
-->