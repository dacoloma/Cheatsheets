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
### Declare a list
```python
list = ['a','b','c']
```
Declare quickly a list of numbers 
```python
numbers = range(X,Y
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
### Comprehension list
## Iteration
### For-loop
 `list = [2,5,4,8,5]`
#### Looping a list 
```python
for number in list:
	# code
```
#### Looping n times
```python
for i in range(n):
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
eyJoaXN0b3J5IjpbNzAxMzE5NjMwLC0xMDA5Nzg4NjQ3LDI5Mj
MwNzQwNiwtMTk1MjA2MTEzOSwxOTU1NDA1NzEyLC03OTYzNjI5
NjAsMTEyMzQwNzg2MywtODYwODk0OTczLDE3NzkyNDEzNzAsLT
IxMDE2Nzc1MTgsMTYzODUyMDkwLDQyNDI0MzI2Nyw0NTY4MjQ1
ODcsLTM2NjA2NTI1NCwtOTM2NDA1MTUxLC0xNTk0MTk1MTQ4LD
E3Mzk1ODEyNzAsLTEzODYzMzkyNzUsLTIwMzkyODk1MTEsOTc5
NTUxODA4XX0=
-->