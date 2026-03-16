
# JS - Async and Callbacks

<!--- 

@todo:
- to do some cleanup & improve structure

--->




## Timeouts & intervals

- Why?
  - Sometimes we want to perform an action after a specific time.
    - Example: display a confirmation message + hide it after 10 seconds.


- Timeout

  ```js
    setTimeout(function () {
      console.log('done!');
    }, 1000);
  ```


- Interval


- Clearing timeout / interval
  - clearTimeout()
  - clearInterval()
    - demo: clear interval after 3 iterations (solve with a counter)




## Practice: timers and intervals

  1. Create an interval that displays a counter every second
    - in the console, display: "hello 1", "hello 2", "hello 3".....
    - hint: you may want to create a counter in the parent scope (e.g. `let counter = 1`)
  2. After 5 times, cancel that interval
  3. (Bonus) Apply what we've learned so far and try to solve it in a different way.
  4. (Bonus) Can you solve it without a setInterval? (hint: setTimeout + research "js recursive function")

  How: individual
  Time: 15min. + 5min. to check solutions.

  
  Solution 1 (checking the counter): 
  - https://stackblitz.com/edit/js-sjpn4f?file=index.js

  Solution 2 (with a timeout): 
  - https://stackblitz.com/edit/js-vhkxbm?file=index.js

  Solution for Bonus 2 (using a recursive function):
  - https://stackblitz.com/edit/js-nbe32j?file=index.js


Note: most students find it difficult, give them 15min. and solve together.





## Synchronicity vs. Asynchronicity

Synchronous vs. Asynchronous code:
- Synchronous code runs line by line. Each step waits for the previous one to finish.
- Asynchronous code can start a task and move on without waiting for it to finish. When the task is done, it notifies the code (e.g., with a callback, promise, or async/await).

Example:
- Synchronous: "Boil water, then make tea."
- Asynchronous: "Start boiling water, while waiting, wash the dishes. When water's ready, make tea."




## Asynchronous Programming

- Async functions allow us to continue executing our code while the async function is being executed in the background. 

- Example:

    ```js
    console.log("cooking dinner...");

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 2000);

    for (let i = 1; i <= 5; i++) {
        console.log('washing dishes....' + i);
    }
    ```


- (skip, just explain the idea) If the current script has not finished:

    ```js
    console.log('cooking dinner...');

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 200);

    //for loop with a lot of iterations...
    for (let i = 1; i <= 1000 * 1000; i++) {
        if (i % 1000 === 0) {
            console.log('washing dishes....' + i);
        }
    }
    ```


    > the function or code snippet cannot be executed until the thread that called setTimeout() has terminated.



- With a delay of 0 ms...

    ```js
    console.log('cooking dinner...');

    setTimeout(function () {
        console.log("dinner's ready!!");
    }, 0);

    console.log('washing dishes 1');
    console.log('washing dishes 2');
    console.log('washing dishes 3');

    ```

    > even though setTimeout was called with a delay of zero, it's placed on a queue and scheduled to run at the next opportunity; not immediately (currently-executing code must complete before functions on the queue are executed)



Synchronous: blocks code (ie. a line of code is not executed until previous one is completed)
Asynchronous: non-blocking



## JavaScript and (a)synchronicity

- "JavaScript is not an asynchronous language, but synchronous one with some asynchronous behaviors."

JavaScript is:
- single-threaded - only one block of code is executed at the time
- synchronous - the code gets executed line by line, from top to bottom, in the order in which they are put in.




## Callbacks II

- Callback = when we pass a function as an argument to another function
  - example: `forEach()`
  - example: `setTimeout()`

- How else can be useful?


Initial example:

    ```js
        function cookDinner() {
            console.log('Preparing dinner...');
            console.log('Dinner is ready');
        }

        function eatDinner() {
            console.log('Eating dinner');
        }

        cookDinner();
        eatDinner();
    ```



But... dinner takes time to be prepared....


    ```js
    function cookDinner() {
      console.log('Preparing dinner...');
      setTimeout(function() {
          console.log('Dinner is ready');
      }, 1000 + Math.random() * 2000);
    }

    function eatDinner() {
      console.log('Eating dinner');
    }

    cookDinner();
    eatDinner();

    ```

Options?
- add a delay in `eatDinner()`
  - problem: we need to know how much it takes to cook
- call `eatDinner()` from `cookDinner()`, once dinner is ready,
  - problem: cookDinner needs to know what to do once dinner is ready.


So we can pass it a function to be executed at the end (once dinner is ready)...

  ```js
  function cookDinner(myCallback) {
    console.log('Preparing dinner...');
    setTimeout(function() {
        console.log('Dinner is ready');
        myCallback();
    }, 1000);
  }

  function eatDinner() {
    console.log('Eating dinner');
  }

  cookDinner(eatDinner); //notice: we don't have ()

  ```



- IMPORTANT: 
  - when you're passing a function as a callback, make sure not to use ()


- When and why any function would be postponed/delayed in the real world?
  - Interact with the UI
  - Wait for some data from a database
  - Wait for some data that we get from a different server
  - ...



## (bonus) Practice: JS Callbacks

- Instructions: https://stackblitz.com/edit/js-graftg?file=index.js
- Time: 15min.

- Solution: https://stackblitz.com/edit/js-dzfqat?file=index.js




## (extra) how to pass arguments

    ```js
    cookDinner(function(){ eatDinner("wine") });
    ```




## (extra) JavaScript errors


<!-- 

@LT: just mention briefly, an error stops code execution (in most cases)

-->


In most cases, when an error occurs in JavaScript, it will halt the execution of the code at the point where the error occurred.

Exceptions:
1. Code inside a try-catch block
2. Asynchronous Code
3. Event handlers


Example:

    ```js
        const amount = 10;

        console.log("green")

        setTimeout(() => {
            console.log("orange");
        }, 1000);


        amount = 42; // error: assignment to constant variable

        console.log("blue");

    ```


## (skip) Resources

- MDN - Introducing asynchronous JavaScript: https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Async_JS/Introducing

