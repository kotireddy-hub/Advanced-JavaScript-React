# Advanced-JavaScript-React
1. Default Parameters
2. Template Literals
3. Three dots operator(...)
4. Destructuring Assignment 
5. Let and Const
6. Arrow Functions 
7. Modules
8. Map
9. Filter
10. Reduce
11. Promises
12. Async & await

## Default Parameters
ES6 allows function parameters to have
default values.But, in ES5, OR operator had
to be used.
```javascript
//ES5
var userName = function (firstName, lastName) {
    firstName = firstName || 'random';
    lastName = lastName || "random";
    //logic
}

//ES6
//normal function
let userName = function (firstName = 'random', lastName = 'random') {
    //logic
}
//arrow function 
let userName =  (firstName = 'random', lastName = 'random') => {
    //logic
}
```
## Template Literals 

ES6 introduces very simple string templates
along with placeholders for the variables.
The syntax for using the string template is
${PARAMETER} and is used inside of the
back-ticked string.

```javascript
//ES5
var name = 'Your name is' + firstName + ''+ lastName; 

//ES6
const name = `Your name is ${firstName} ${lastName};
```
## Three dots operator 

In ES6, The three dots operator (...)
- The spread operator
- The rest operator

The rest and spread operators help in adding values 
to the array and object

### Spread Operator

```javascript 
//Array
const arr1 = [1, 2];
const arr2 = [3, 4];
const combined = [...arr1, ...arr2];

//Object
const obj1 = {a:1};
const obj2 = {b:2};
const obj3 = {...obj1, ...obj2}
```
- Merging arrays or objects.
- Shallow copying of arrays or objects, that is copying without modifying them in any way.

## Rest operator
- It possible to
create a function that accepts any
number of arguments.
- It is used for destructuring arrays and
objects.
- The rest parameter has to be the last
parameter in the function.

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}
console.log(sum(1, 2, 3, 4)); 
```

## Destructuring Assignment

- Destructuring allows easy to assign values from arrays or objects into different variables.

```javascript
// Object Destructuring

const person = { name: 'random', age: 32 };
const { name, age } = person;

//Array Destructuring

const numbers = [1, 2, 3];
const [first, second] = numbers;
```

## Let and Const
- JavaScript developers had only one way of declaring their variables and that was using the var keyword; however, it had its vices which included variable hoisting and scope leakage. ES6 introduced let and const to address these issues.

![VAR_LET_CONST](Var_Let_Const.jpeg)

## Arrow Functions 

- It provides a more concise syntax for
writing function expressions by removing
the "function" and "return" keywords.
- Arrow functions are defined using the fat
arrow (=>) notation.
- Unlike ordinary functions, arrow functions
do not have their own this keyword.
- The value of this inside an arrow function
is always bound to the value of this in the
closest non-arrow function.
Arrow functions are not hoisted. They
must be defined before they are used.

```javascript
syntax:- 
() => {}

//ES5 function expersion 
var sum = function(a,b) {
    return a + b;
}

//ES6
const sum = (a,b) => a + b;
```

## Modules
We can use the "import" or "export"
statement in a module to import or
export variables, functions, classes or
any other component from/to different
files and modules.

```javascript
//export demo.js
export const firstName = "random";
export const lastName = "random";

//import

import { firstName, lastName } from 'demo';
```

## Map
- map is a array method and retrn a new array.

```javascript
const data = [ 
    {},
    {}
];

//syntax 
data.map ( () => {})
```
## Filter
- filter is a array method and retrn a new array with filterd values.

```javascript
const data = [ 
    {},
    {}
];

//syntax 
data.filter ( () => {})
```
## 24-07-2025

```javascript
const details = {
  type:'TATA',
  modal:'Nexon',
  color:'Black',
}

 const {type:cardType, registaton: {city} = {}} = details;

//console.log(city)
/* 
var a 

cosole.log(a)

a = 20;

console.log(a)
*/

//console.log(a); // be default undefied 

var a = 20;

//console.log(a)

let b = 20;

//console.log(b);

const c = 20;

var d = 40;
const f = 30;
let e = 50;
var d = 50;
const f = 40;
let e = 50

{
 var d = 30;
 let e = 30 
 const f = 40;
 console.log(d, "=== e", e,f, "block");
}
 console.log(d, "global",f); // 30

function userName () {
  
  var user = 'random';

let firstName = 'random1'

const lastName = 'random2'
  
 // console.log(user);
  //console.log(firstName);
  //console.log(lastName);
}


userName();
console.log(user);
console.log(firstName);
console.log(lastName);

// demo.js

export const todayDate = new Date();

export deafult todayDate = new Date();

// demo1.js

// import & export  - > consume | provider 

import  {todayDate} from 'demo.js';

import todayDate from 'demo.js';
```

## 25-07-2025

```javascript

// syntax arrow 
//() =>  {}

//ES5
function functionName () {
  //logic
}

functionName()
//ES6 Arrow
const userName = () => {};

userName()

// parameters 

function funcParams(arg1,arg2){
  console.log(arg1,arg2)
};

funcParams('test','test1')

//Arrow 

const funParamsArrowFn = (par1,par2) => {
   console.log(par1,par2)
}
funParamsArrowFn('arrow1', 'arrow2');



//normal fun
function FnWithNoArg(){
  console.log(arguments);
  console.log(arguments[0])
};

FnWithNoArg("Hi","test","today")

//arrow fun

// const arrFnWithNoArg = () => {
//   console.log(arguments);
// };

// arrFnWithNoArg("hi","test","today");

// normal fun Object

const obj1 = {
  name:'random',
  age:30,
  fn: function(){
    console.log(this);
  }
};


obj1.fn();// current Obj;


const obj2 = {
  name:'random',
  age:30,
  fn: function(){
    function fn1(){
     console.log(this)
    }
    fn1()
  }
};

//obj2.fn() // window

//arrow fun obj

const obj3 = {
   name:'random',
  age:30,
  fn: () => {
    console.log(this);
  }
}

//obj3.fn();// window

const obj4 = {
  name:'random',
  age:30,
  fn: function(){
   const fn1 =() => {
     console.log(this)
    }
    fn1()
  }
}
  
obj4.fn(); // current obj


//normal retrun 

function fnWithReturn (a,b){ 
  return a + b;
};
console.log(fnWithReturn(2,4));


// arrow return 

const fnWithReturnArr = (a,b) =>  a + b;
console.log(fnWithReturnArr(2,4));


// normal function hoisting

funBefoeIn();

function funBefoeIn(){
  console.log("hello")
}

// // arrow not hoisting

// funBefoeInArrow();

// const funBefoeInArrow = () => {
//   console.log("hello")
// }


// Map

const arr = [1,2,3,4,5];

// const sqNumber = arr.map( (num) => {
//   return num * num;
// });

const sqNumber = arr.map( (num) => num * num);

const sqNUmberWithNormalFn = arr.map(function(num) {
  return num * num;
})
console.log(sqNUmberWithNormalFn)

const arrObj = [
  {
  id:1,
  title:'first'
},
{
 id:2,
 title:'second' 
},
];

const arrObjMap = arrObj.map( (item) => {
  return item.title;
});

console.log(arrObjMap)

// Filter

const arrObjeFilter = arrObj.filter( (item) => {
  return item.title === "second"
})

console.log(arrObjeFilter)
```