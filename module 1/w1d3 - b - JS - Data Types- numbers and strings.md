
# JS - Data Types - numbers and strings




## Numbers

- represent integers and floating-point numbers in JavaScript

```js
const age = 34; //integer
const price = 12.99; //decimal
```



### Number expressions

- `+` addition
- `-` subtraction
- `*` multiplication
- `/` division



### NaN (Not a Number)

```js
const result = 10 / 'pizza';
console.log(result);
```




### Modulo % (aka remainder operator)

<!-- 

- e.g. 10 % 3 pizzas 

- interactive demo: https://www.joshwcomeau.com/javascript/modulo-operator

-->


Example:


  ```js
  const pizzas = 10;
  const people = 3;

  const remainder = 10 % 3;
  // console.log(remainder);
  ```

  <!-- 

    Aug 2023 - Week Zero:
    - includes "Check if number is even or odd" (in unit "JS | Data types: Numbers")
    
  -->



### Practice: even or odd (together)

- Intro: even vs. odd

```js
// even --> if we divide by 2, there is no remainder
// odd --> if we divide by 2, there is a remainder
```


- How we can check if a number is even ?


Ex.: 

  ```js
  const myNumber = 25;

  if (myNumber % 2 === 0) {
    console.log('your number is even!');
  } else {
    console.log('your number is odd!');
  }

  ```

- Solve together:

Task:
- Iteration 1: display numbers 1 to 12
- Iteration 2: we want to display if each number is even or odd
  - e.g. if number is odd, display `x is odd`
  - e.g. if number is even, display `x is even`


Solution:

  ```js

  // for(initialization; condition; afterthought)

  for (let i = 1; i <= 12; i++) {
    // console.log(i);
    if (i % 2 === 0) {
      console.log(i, 'is even');
    } else {
      console.log(i, 'is odd');
    }
  }
  ```



### (skip) Practice: FizzBuzz

- how: individual / small teams (2-3 people)
- time: 20-25m + solve together
- https://stackblitz.com/edit/js-fizbuzz-exercise-p4hr4j?file=index.js

- Solution: https://stackblitz.com/edit/js-fizbuzz-exercise-a6bphh?file=index.js


<!--

Fizz-Buzz
- it is in prework ("JS | Loops and iterations")
- another option is to do this kata together: 
  - https://www.codewars.com/kata/5300901726d12b80e8000498
  - Note: a bit challenging for day3 (solve TOGETHER).
  - Concepts: loop + arrays + modulo operator

-->



### Assignment Operators

- Assignment: x = y
- Addition assignment: +=
- (brief) Others: see Student Portal



### Expressions

> Expression = a combination of any value (number, string, array, object) and set of operators that result in another value.

  ```js
  const total = 2 + 4;
  const result = (7 + 5) / 3 - 8;
  ```


### Operator Precedence

(brief) see Student Portal


> Operator Precedence 1: `2 + 2 * 5 + (4 - 2)`
> Operator Precedence 2: `4 * ( 5 - 2 ) + (2 + 2 ** 3) - 24 / 2`





## Strings


Creating a String
- "" double quotes,
- '' single quotes or
- `` backticks

  ```js
  const user1 = 'alice';
  const user2 = "bob";
  const user3 = `charlie`; // ES6
  ```

Ex:

  ```js
  const title = 'Harry Potter';

  //string concatenation with the "+" operator
  const msg1 = 'my favourite book is ' + title + ' and i love it';

  //Template Literals / String Interpolation
  const msg2 = `my favourite 
                book is ${title} 
                and i love it`;
  ```



Template literals:
- multiple lines
- interpolation



### Some string properties and methods


  ```js
  const message = "My favourite book is Harry Potter and I love it";

  console.log(message);
  console.log(message.length);
  console.log(message.charAt(1));
  console.log(message[1]);

  console.log(message.indexOf('m')); //0
  console.log(message.indexOf('w')); //-1 --> str does not exist
  console.log(message.indexOf('favourite')); //3

  const result = message.includes('f');
  console.log(result);
  ```




### Slice

  ```js
  slice(beginIndex)
  slice(beginIndex, endIndex)
  ```

  Note: character at `endIndex` not included


### Practice: strings & string methods

- Instructions: https://stackblitz.com/edit/js-1am8e2?file=index.js
- Time: 15min.
- How: individual / in pairs

- Solution: https://stackblitz.com/edit/js-tsenus?file=index.js
- Solution for bonus iterations: https://stackblitz.com/edit/js-hy613k?file=index.js



### Sorting strings - .localeCompare()

<!-- 

@LT: they need it for today's lab (iteration. 3.3) 

-->


```js
const user1 = 'bob';
const user2 = 'charlie';

const result = user1.localeCompare(user2);
console.log(result); // -1
```



Explanation: 


```js
/*

str.localeCompare()

can be used to compare strings in alphabetical/lexicographic order
(it also considers locale-specific rules, such as language-specific sorting conventions and special characters)

It returns:
-1 --> if the main string goes before the other one
0 --> same strings
1  --> if the main string goes after the other one

*/
```

