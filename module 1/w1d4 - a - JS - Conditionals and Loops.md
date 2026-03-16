

# JS - Conditionals and Loops


Methodology:
- we probably don't need to go in detail for the theory
- instead, ask them to solve "FizzBuzz" + solve it together


FizzBuzz:
  - how: small teams (2-3 people)
  - time: 20-25m + solve together
  - https://stackblitz.com/edit/js-fizbuzz-exercise-p4hr4j?file=index.js

  - Solution: https://stackblitz.com/edit/js-fhyx8t?file=index.js


<!-- 

may 2023:
- FizzBuzz is in prework but not in module zero

-->


## Notes


- if…else +++
- if…else if…else  ++
- nested if…else +
- switch (skip)
- while
- do…while
- for ++
- for…of +
- continue
  - The continue statement breaks one iteration (in the loop) if a specified condition occurs, and continues with the next iteration in the loop.
- break
  - The break statement exits a switch statement or a loop (for, for … in, while, do … while).
- (extra) ternary operator


## Switch

SKIP (tell students that are not familiar with it to go through it self-guided)



```js
switch (expression) {
  case value1:
    // executed code when the expression === value1
    break;
  case value2:
    //...
    break;
  case value3:
    //...
    break;
  default:
  // executed code when none of the values match the expression
}
```



## for...of

```js
const someIterable = 'hello world';
 
for (const value of someIterable) {
  console.log(value);
}
```



## continue

> The continue statement stops the current iteration, and continues with the next iteration.



## break

> The break statement exits a switch statement or a loop (for, for … in, while, do … while).




## EXTRA: Ternary operator

- Syntax:

  `condition ? exprIfTrue : exprIfFalse`


- Example 1: initial code with if-else 

  ```js
  const userName = 'alice';
  let points;

  if (userName === 'alice') {
    points = 20;
  } else {
    points = 30;
  }

  console.log(points);
  ```



- Example 1 with ternary operator:

  ```js
  const userName = 'alice';
  const points = userName === 'alice' ? 20 : 30;

  console.log(points);
  ```



- Example 2, returning from a function:
  
  ```js
  function getUserRole() {
    
    let name = "alice";

    if (name === "alice") {
      return 'admin';
    } else {
      return 'standard';
    }
  }

  const role = getUserRole();
  console.log(role);

  ```

- Example 2, with ternary operator:

  ```js
  function getUserRole() {
    let name = "alice";

    return (name === "alice") ? 'admin' : 'standard';
  }

  const role = getUserRole();
  console.log(role);
  ```

