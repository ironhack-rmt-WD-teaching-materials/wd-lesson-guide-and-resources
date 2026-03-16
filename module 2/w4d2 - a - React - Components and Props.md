

# React - Components & Props


<!-- 

@todo: can create a slightly more complex exercise to practice Components + props.
  - create stackblitz
  - ask students to create a child component
  - pass info from parent to child
  - (extra) create grandchild & pass info to grandchild
  - (this can also be a good exercise to warm-up tomorrow)

-->


Intro Slides (components + function vs. class components): 
https://docs.google.com/presentation/d/1iqYSImZj7p58ahLWryMSp00ooCCEf2cnIhjwc-pMFqw/edit?usp=sharing



## (brief) Function vs. Class Components

- Differences
- How to create a function component
- How to create a class component

Examples: 
- https://reactjs.org/docs/components-and-props.html#function-and-class-components



## Create components

Work on the app from yesterday and create these components:
- `<Header />`
- `<User />`
- `<Footer />`


For User:

```jsx
  function User(){
      return(
        <h1>Name: Alice</h1>
      );
  }
```



## Install React Dev Tools 
  https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en



## Know how the Component tree works
-  component tree 



## Props I (syntax)

- Intro to props & syntax:
  - passing props to the `Header` (e.g. title).


## Practice: components and props I

Initial code: https://stackblitz.com/edit/vitejs-vite-ejt8k34c?file=src%2FApp.jsx

Task:
- From the App component, pass some info to the Footer using props (e.g. pass the message "hello world")
- In the Footer component, receive props and render that message in the user interface.

Bonus:
- You can pass multiple props to the same component.
- Also, you can experiment passing different data types (e.g. string, number, array...)

Solution:
- https://stackblitz.com/edit/vitejs-vite-qgvu3vwy?file=src%2FApp.jsx


Time: 5min.



(break)


## Props II (using props to make our components more reusable)

Create a component for each user:

```jsx
function UserOne(){
    return <h1>Name: Alice</h1>;
}

export default UserOne;
```


```jsx
  <Header />
  <UserOne />
  <UserTwo />
  <UserThree />
  <Footer />
```

- Ask students what they think about the code above

- Explain: props are similar to function arguments 

  > Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called props) and return React elements describing what should appear on the screen.

  - Example with functions (show how we can create a generic function using arguments): https://stackblitz.com/edit/js-5tsf94?file=index.js



- Passing and accessing a prop
- Passing multiple props

- Note: we could also pass an object (e.g. `userDetails={}`)
- Note: As props, we can pass any valid data type



## Practice: components and props II

Initial code: 
- https://stackblitz.com/edit/vitejs-vite-udhmpb?file=src%2FApp.jsx
- note: in App.jsx, we have an array of movies

Iteration 1: 
  - create a component "Movie" (for this iteration, just display an h1 e.g. `this is the Movie component`).

Iteration 2: 
  - in App.jsx, render 3 times the Movie component

Iteration 3: 
- use props to make the component generic
- in App.jsx, you will need to send each element of the array as props.

```jsx
  <Movie details={moviesArray[0]} />
  <Movie details={moviesArray[1]} />
  <Movie details={moviesArray[2]} />
```

Bonus 1: display in the Header the number of movies.

Bonus 2: Keep challenging yourself further. 
- For example, add some cool CSS & make it look good. Here's some inspiration: https://drive.google.com/file/d/1bTCwoCxZkyJQgAaJYzONtPmbEDpMho0Z/view
- You can also display the rating as stars. Example: https://codepen.io/FredGenkin/pen/eaXYGV


Time: 20min.

Solution: https://stackblitz.com/edit/vitejs-vite-gzumrd?file=src%2FApp.jsx


<!-- 
@LT:
- solve together (brief) -- remember to fork!
- explain how to add css (className + add rules to index.css)
-->


---

Note: lab "React Tweets" (extra lab)

- They will be passing elements of an array:
    `<Tweet tweet={ tweetsArray[0] }>`
    `<Tweet tweet={ tweetsArray[1] }>`
    `<Tweet tweet={ tweetsArray[2] }>`
- Each element is an object (ie. `props.tweet` is an object)


(break)


## (skip for now) Receive props with object destructuring

  - Option1: 
    ```js
      function User(props) {

        const {name, surname} = props;

        //...
      }
    ```


  - Option2 (with props destructuring): 

  ```js
    function User({name, surname}) {
      //...
    }
  ```




## Props and Data Types

- As props you can pass...
  - string, number, boolean, array, object, function... 
  - A JS expression (e.g. foo={2+2})

- `props.children`


## props.children



## When do you use props?




## (skip) props are immutable

- props are immutable: you must never modify the `props` that a component receives.
  - https://reactjs.org/docs/components-and-props.html#props-are-read-only

  - (extra) explain the concept of a `pure function`
    > All React components must act like pure functions with respect to their props.




## (extra) Components from npm

- React Player:
  `npm install react-player`

  `<ReactPlayer src="https://www.youtube.com/watch?v=EvtMTV9mMSc" playing={true} volume={0.1} />`

- (extra) Component Libraries
  - Show an example with one of them (e.g. "Material UI"/ "Semantic UI React" / "Ant Design")
  - https://ant.design/components/button






<!-- 

@LT: install React Dev Tools

https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en

-->

