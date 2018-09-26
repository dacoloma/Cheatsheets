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
function myName(name) {
	console.log('My name is ' + name + ' !');
	console.log('My name is ${name} !');
}
myName('Dany');
```
> Output > My name is Dany ! 
> Output > My name is Dany ! 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY5ODIyMTQ5OCw0Mjk0NTMwNjQsLTkwMT
U4MjAwMiwtMTA0ODM1NzI2NF19
-->