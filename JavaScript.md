# JavaScript - Basics
## Variable, constant
```javascript
// Variable assignment
let x = 3;
let test = 'abc';

// Constant assignment
const k = 'constant';
const pi = 3.14;
```
## Print
```javascript
console.log('This is a test');
```

## If ... else statment
```javascript
let age = 5;
if (age < 18) {
	console.log('Not allowed');
} else {
	console.log('You can pass');
}
```

## Function
### Declaration & ouput
```javascript
function myFunction() {
	// code
	console.log('Inside my function');
}
myFunction();
```
> Output > Inside my function

```javascript
// With parameters
function myName(name) {
	console.log('My name is ' + name + ' !');
// or "console.log('My name is ${name} !');"
}
myName('Dany');
```
> Output > My name is Dany ! 

```javascript
// With parameters and default value
function myName(name = 'Dany') {
	console.log('My name is ' + name + ' !');
// or "console.log('My name is ${name} !');"
}
myName('Marvin');
myName();
```
> Output1 > My name is Marvin ! 
> Output2 > My name is Dany ! 
```javascript
// Anonymous function
const age = function () {
// code

```
> Output > 
```javascript
// Refactor
```
> Output > 

## Scope
<!--stackedit_data:
eyJoaXN0b3J5IjpbODY2OTU2NzgzLC01NjEzODU3NDksMjExMT
Y1NjYzLDEwMDQxMDMxODcsLTY0NTUzNDU1OCwzMTQzMTU5MDIs
LTY0NTUzNDU1OCw0Mjk0NTMwNjQsLTkwMTU4MjAwMiwtMTA0OD
M1NzI2NF19
-->