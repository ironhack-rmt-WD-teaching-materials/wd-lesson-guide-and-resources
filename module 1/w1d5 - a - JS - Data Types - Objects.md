

# JS - Data Types in JavaScript - Objects



## Intro:

- Array & Objects: 2 ways of organizing information (more on that in a moment: "Why we use objects")

- Object = collections of properties 
- key-value pair
- keys are unique (one key will always have just one value associated to it)

- example:

  ```js
  let user = {
    key1: value,
    key2: value,
    key3: value
  };


  const userOne = {
    userName: 'alice',
    age: 30,
    isLoggedIn: true,
  };

  ```

- Data types: we can store any valid data type


## Why we use objects

- group values that belong together
- relationships between variables

<!-- 

Arrays vs Objects:
- array: collection of things
- object: info about 1 single thing

-->


- Arrays: useful for organizing and accessing data based on the position.

- Objects: useful for organizing and accessing data using meaningful labels.

- Examples:
  - arrays:
    - array of students
    - array of teachers
    - array of numbers
  - objects:
    - user details (userName, email, status...)
    - company object (founder, marketing director, front-end developer...)


  Example 1:

  ```js  
  const employees = ['alice', 'bob', 'charlie'];

  const company = {
    director: 'alice',
    pm: 'bob',
    developer: 'charlie',
  };
  ```



  Example 2:

  ```js  
  const userDetails = ['bob', 20, 'bogotá', false];

  const user = {
    userName: 'bob',
    age: 20,
    city: 'Bogotá',
    isLoggedIn: false,
  };
  ```



## How to create an object:


- Object literal syntax

    ```js
    let someObject = {
        key1: value,
        key2: value,
        key3: value
    };
    ```

- (skip) Object constructor syntax

  ```js
	let someObject = new Object();
  ```


## Read properties (dot notation / bracket notation)
- dot notation
- square bracket notation (with a string inside brackets)


- dot notation vs bracket notation
  - in most cases we use dot notation (more simple and easier to read)
  - you may need bracket notation for:
    - access keys with multiple words (`myObj["marketing manager"]`)
    - access keys with dynamic names (`myObj[myVariable]`)
    - (skip) access keys with numeric values (`myObj[400]`)


```js
const errorCodeLookupTable = {
  "400": 'Bad Request',
  "401": 'Unauthorized',
  "404": 'Not Found',
  "500": 'Internal Server Error',
};
```



## Add properties (dot notation / bracket notation)

- dot notation
- bracket notation


## Update properties (dot notation / bracket notation)



## (skip) Remove properties (delete operator)

  ```js
	delete olympicRecords.doubleOllie;	// dot
	delete olympicRecords['doubleOllie'];	// bracket
  ```


## (skip) Check if a property exists (in operator)
	
  ```js
      let myCar = {
          make: 'Honda',
          model: 'Accord',
          year: 1998
      };

      'make' in myCar; // returns true
      'model' in myCar; // returns true
  ```
        


___

(Break)
___



## List properties: Object.keys() 

- Object.keys(myObj) 
  - returns and array (we can then loop through the array etc)

- `const listOfKeys = Object.keys(userOne);`


## List values: Object.values()

- Object.values(myObj)
  - returns an array

- `const listOfValues = Object.values(userOne);`


## Loop through objects

- (just mention it) We can loop through the array returned by Object.keys()
- (just mention it) We can loop through the array returned by Object.values()
- (demo) for ... in loop

  ```js
  for (const key in user) {
    console.log(user[key]);
  }
  ```


___

(Break)
___



## Declaring an object with CONST
- we can add/update/delete properties
- but we can not reassign the object
    - is fixed to the same reference (address) in the memory
    - the variable declared with const can't be reassigned to a different value


    > In the case of declaring an object using the const keyword, this means that new properties and values can be added BUT the value of the object itself is fixed to the same reference (address) in the memory and the object (or any variable declared with const) can't be reassigned.



## Practice: JS Objects


- Instructions: https://stackblitz.com/edit/js-5d6bhn?file=index.js

- Time: 15min.


<!--

Goals: 
- practice objects
- get a nice name for our class ;)

- examples from prev. cohorts:
  - Bug Busters
  - The Script Society
  - Byte Warriors
  - Coding Ninjas
  - Angry Cats
  - Remote Raccoons

-->


## Choose name for our cohort :) 




## Extra resources

- Summary / Sample code:
  https://stackblitz.com/edit/js-jcxkmx?file=index.js



