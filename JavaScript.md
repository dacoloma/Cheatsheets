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
	console.log('I am 25 yo');
}

// Refactor
const age = () => {
	console.log('I am 25 yo');
}
```

## Scope
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg2NjA4MjM0NSwtNTYxMzg1NzQ5LDIxMT
E2NTY2MywxMDA0MTAzMTg3LC02NDU1MzQ1NTgsMzE0MzE1OTAy
LC02NDU1MzQ1NTgsNDI5NDUzMDY0LC05MDE1ODIwMDIsLTEwND
gzNTcyNjRdfQ==
-->