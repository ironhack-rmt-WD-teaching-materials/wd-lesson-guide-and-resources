
# React - State hook and events

<!--

Status: draft

@todo: 
- improve the planning for this unit (examples & steps to follow)
- create slides (e.g. syntax, functional updates etc.)

-->


## Intro

- 2 Types of components
  - Function components
  - Class components


- Hooks:
  > Hooks let you use different React features from your components. 
  

- We've learned how to pass info with props
  - props = info that comes from outside of the component

- State:
  - Allows components to store internal data ("information")
  - We can use that information in JSX, when we describe the User Interface

> "State is similar to props, but it is private and fully controlled by the component."


- State: 
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)

<!--

(es)

Estado:
- Almacena información que pertenece a un componente
- Puede cambiar con el tiempo
- Queremos reflejar los cambios en la interfaz (JSX)

-->



## State in function components


Option 1: 
- work on the app we built yesterday

Option 2 (preferred): 
- work here: https://stackblitz.com/edit/react-s2s6wx?file=src%2FApp.js
  <!-- @LT: use this option (since easier to share the code with an isolated example of state) -->

  <!-- remember to FORK -->
  <!-- remember to FORK -->
  <!-- remember to FORK -->



DEMO: add a counter in `<Header />`:

  <!-- @LT: DEMO (we will do an exercise in a few moments)  -->

  - Display a message: "Number of likes: XXXX"
  - Add button 
  - Add onClick event
  - Explain these two patterns (before implementing the function):
    - `onClick={() => { console.log("clicked...")}}`
    - `onClick={increaseCounter}`
  - Explain how to send an argument:
    - `onClick={ () => {increaseCounter(20)}}`
  - Try to solve with a normal variable & see how that doesn't work.

      ```js
          let counter = 0;

          const increaseCounter = () => {
              console.log("increasing counter....")
              counter++;
              console.log(counter)
          }
      ```

  - Intro State: 
    - Store information that belongs to a component
    - Can change over time
    - We want to reflect the changes in the UI (JSX)




  - useState hook:
    - https://react.dev/reference/react/useState#reference

  -  Syntax:
    - `const [something, setSomething] = useState(initialValue);`


  - Solve with State

    ```js
      const [counter, setCounter] = useState(0);
    ```

    ```js
    counter++; // never
    setCounter( counter + 1 );
    setCounter( counter++ ); // avoid (will modify state directly)

    ```



## Practice: React State

<!-- @LT: remember to FORK  -->

Instructions: https://gist.github.com/luisjunco/b6e7ea8236c8256158290de6d2be5372

Time: 20min. (try to do at least iterations 1, 2 and 3)

How: individual / in pairs




## Multiple state variables

In a component we can have multiple stateful variables

```js
const [counter, setCounter] = useState(0);
const [pizza, setPizza] = useState("margherita");
```



## (extra) add a counter to a component that repeats multiple times (e.g. User/Movie)

See how the counter of each component is independent (state belongs to the component)

<!-- @todo: create example on stackblitz & share with students -->
<!-- note: can also be done as an exercise -->





## (skip) Explain: Functional update

Why should I use a function if the new state depends on the previous? Example: https://stackoverflow.com/a/57828519/11298742





## Using State correctly

<!-- @todo: create slides -->

- Remember (https://reactjs.org/docs/state-and-lifecycle.html#using-state-correctly):
  - Do Not Modify State Directly
    - note: `counter++` modifies state directly
  - State Updates May Be Asynchronous

- A Component will Re-render if:
  - receives new props from the outside
  - its own state changes

- Useful:
  - See how component re-renders when we update state
  - See state in React Dev Tools





## When should we use the state

- State: 
  - Store information that belongs to a component
  - Can change over time
  - We want to reflect the changes in the UI (JSX)



## State vs. Props

- See Student Portal


