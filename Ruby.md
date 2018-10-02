# Ruby
## Syntax
### Print
```ruby
print "Something"
puts "Something2"
```
> Output > SomethingSomething2
### IF Statement
```ruby
if [condition] ? [variable]
	# code
end
```
### List
```ruby
list = [var1, var2, var3]
```
## Loops
### While-loop
```ruby
while [condition]
	#code
end
```
### Until-loop
```ruby
until [condition]
	#code
end
```
### For-loop
```ruby
for i in 1..10 # 1 to 10 included
	#code
end
```
### Loop
```ruby
loop do
	next if [condition1]
		# code
	break if [condition2]
		# code
end
```
## Iteration
### Each element of a list
```ruby
liste.each do |item|
	puts "{item}"
end
```
### Number of times 
```ruby
10.times {puts "Hello"}
```
## Function
### String
#### Character included in String
```ruby
str.include? c
```
> return True if the variable c is in the string 'str', else return False
#### Convert String to Array
```ruby
str.split
```
> return an Array
#### Replace a character by another (REGEX)
```ruby
str.gsub(/char1/,char2)
```
> return a string

### Array
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMDgxMjA2MjVdfQ==
-->