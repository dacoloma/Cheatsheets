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
const age = function (nb) {
	if (nb === 25) {
		console.log('I am 25 yo');
	} else {
		console.log('I am not 25 yo');
	}
}

// Refactor
const age = nb => nb === 25 ? console.log('I am 25 yo') : console.log('I am not 25 yo');
```

## Scope

## Array


<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA3NTE5MjkyMiw2NDg4NzA2NTEsLTg2Nj
A4MjM0NSwtNTYxMzg1NzQ5LDIxMTE2NTY2MywxMDA0MTAzMTg3
LC02NDU1MzQ1NTgsMzE0MzE1OTAyLC02NDU1MzQ1NTgsNDI5ND
UzMDY0LC05MDE1ODIwMDIsLTEwNDgzNTcyNjRdfQ==
-->