

# Functions Advanced


<!--- Status: complete --->



## Intro


- We've already seen how we can declare & use functions

    ```js
    function calcSum() {
        console.log("hello")
    }

    
    calcSum();
    ```

- This is called a function declaration (aka statement)
- pass arguments
- return

- JavaScript is a programming language with `first-class functions` (functions are treated like any other variable)
  - a function can be assigned as a value to a variable
  - a function can be passed as an argument to another function
  - a function can be returned by another function 

> example "a function can be passed to other functions": `forEach()`



## Function Expressions

- We know that we can store a function in a variable

- Example:

    ```js
    const calcMult = function(x, y) {
        return x * y;
    };

    calcMult(2, 3);
    ```

- Compare both syntaxes
  - notice, it's a function 'without the name'.

  - a function expression is an un-named function (aka **Anonymous Function**) that is stored in the variable.



## Function declaration vs. function expression

- The syntax we use to create them is different but:
  - to call (invoke) the function, the syntax is the same
    - `doSomething()`

  - both can be reused throughout the code.

- Main difference:
  - function declaration: a function can be invoked 'before' the function declaration
    - why? Hoisting (lesson next week)
  - function expression: we can not call the function before it has been declared
    - makes sense: show example of the same with variables


- Should I use function declarations of function expression?
  - Consistency
    - Whichever you decide to use, stick with it
    - When you join a dev team, if there's a convention, stick to it



--- 
(break)

--- 



## Anonymous functions

- An anonymous function is a function without a name.

- Why ?
  - if it will be used just in that very moment and never again in your code

- Example:
  - call setTimeout
    - create a function `sayHello` (declaration / function expression) & pass it as an argument
    - pass an anonymous function



## Callbacks I (intro)

<!--
@LT: 
- just explain the concept of a callback
- leave examples for the unit "Async and callbacks"
-->

- Callback = when we pass a function as an argument to another function
  - example: `forEach()`
  - example: `setTimeout()`


- Usually, when we pass one function as an argument we refer to it as a `'callback'` 

- Note: in the following days we'll see more examples of how this can be useful.




## Arrow Functions

- Alternative syntax to create an anonymous function
- (they're a different way to create functions)
- Introduced with ES6

- Example:

  ```js
  // function expression syntax
  const sayHello = function(userName) {
    console.log(`Hello, ${userName}!`);
  };

  // arrow function syntax
  const sayGoodbye = (name) => {
    console.log(`Goodbye, ${name}!`);
  };

  ```


- Simplifying arrow functions:
  - `only one parameter -> we can remove the parenthesis`
  - `only one line -> we can remove the curly braces & the return (return is implicit)`
  - example: `calcDouble`

- "Traditional" vs "Arrow" functions
  - quite much the same
  - which one to use: 
    - consistency
    - in some cases we'll need to use one or the other (e.g. this)

- Arrow functions don't have their own bindings to `this`.

  - > Arrow functions don't have their own bindings to this, arguments, or super, and should not be used as methods.

  - "Arrow function expressions should only be used for non-method functions because they do not have their own `this`"


  ```js
  const user = {
    userName: 'alice',
    age: 30,
    sayHello: function () {
      console.log(`hello my name is ${this.userName}`);
    },
    sayGoodbye: () => {
      console.log(`goodbye my name is ${this.userName}`);
    },
  };

  user.sayHello();
  user.sayGoodbye();

  ```

- Arrow functions... "this" is the difference:
![this is the difference](../media/images/arrow-functions-this-is-the-difference.jpg)

- f*** this:
![cant-remember-what-this-refers-to.png](../media/images/cant-remember-what-this-refers-to.png)



## Practice: arrow function syntax

Using "Arrow Functions syntax", create the following functions:

1. A function sayHello():
  - expects zero arguments.
  - displays the message "hello world".

2. A function offerDrink():
  - expects one argument (a string with the name of a drink).
  - displays the message "hello, would you like a XXX ?".

3. A function calcAverage():
  - expects 3 arguments (numbers).
  - returns the average (note: it needs to RETURN the average)


Bonus 1: a function displayCurrentDate() (may need to do some research)
Bonus 2: play further with JavaScript dates


Time: 10min.


Solution: https://stackblitz.com/edit/js-gkzf8e?file=index.js



# (skip) Refresh: Different ways of creating functions 

Summary: function declaration (statement) vs. function expression vs. arrow function

https://stackblitz.com/edit/js-evfgcy?file=index.js




## (skip) The arguments object


- Inside the body of a function, you can access an object called `arguments`.
- This object contains the values of the arguments passed to that function.


Example:
  ```js
      function printSomething() {
          console.log(arguments);
      }

      printSomething('hi');

      // [Arguments] { '0': 'hello' }

  ```

- It is a special kind of object called `array-like object`

  > "Array-like" means that arguments has a length property and properties indexed from zero, but it doesn't have Array's built-in methods like forEach() or map()

- Accessing it's values is a bit different.

  - One option is to convert it to an array. For example:

    ```js
    function printSomething() {
        const args = Array.from(arguments);
        console.log(args);
    }

    printSomething('hi', 'hello');

    ```

