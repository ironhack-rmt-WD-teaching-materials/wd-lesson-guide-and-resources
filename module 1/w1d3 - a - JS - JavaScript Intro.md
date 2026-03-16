

# JS - JavaScript Intro

<!--- 

@todo: 
- improve notes & examples
- add mini-exercise

-->


## Intro

<!-- Skip or make some brief slides. -->

- ECMAScript & versions

-  JS version history: https://cdn-media-1.freecodecamp.org/images/uBY4n5MuFWvc81VWSWVk2wc1ZYQ4MF1RM39A


- Create blank project on stackblitz


## Basic concepts
- console.log
- comments


## Variables
- what is a variable?
- declaring a variable
- declare vs. initialize
  - if you don't assign a value to a variable when you declare it, its default value will be initialized to `undefined`.
- naming a variable


## Changing values

```js
  let userName = 'alice'; //declare + initialize
  userName = 'bob'; //reassign
  console.log(userName);
```



## Type

- data types
- operator typeof



## Type Conversion

> You can reassign values and change the data type of variables in JavaScript.


```js
  let amount = 10;
  amount = 'eleven';
  console.log(amount);
```



## Scope


```js

  // Scope === where in the code we can access a variable
  //
  // - global
  // - function scope
  // - block scope

  const a = 1;

  function sayHello(){
    const b = 2;

    if(true){
      const c = 3;
    }
  }

```


```js
  // - children have access to parent's scope
  // - parent do not have access to child's scope

```


## var, let, const

Note: make sure we've explained SCOPE FIRST.


Const:
- const is used when declaring a variable which value will be constant (ie. we're not planning to reassign the variable).


Scope Differences:
- var: global / function scope
- let, const: global / function scope / block scope


(Extra) Video:
- let vs. var vs. const - Mosh (7m): 
  https://www.youtube.com/watch?v=XgSjoHgy3Rk




## First-Class functions

- In a variable, we can store any valid data type (number, string, array....)

- We can also store a function


```js
const sayHello = function () {
  console.log('hello world');
};

sayHello();
```



```js
/*

first-class functions = functions are treated like any other variable

1. we can store a function in a variable
2. we can pass a function as an argument to another function
3. a function can return a function

*/
```
