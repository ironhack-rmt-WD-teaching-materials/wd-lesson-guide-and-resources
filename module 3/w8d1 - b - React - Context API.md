

# React - Context API

<!-- 

@todo: create cheatsheet

@todo: create lab
- it. 1: context api for language
- bonus: explain the possible approaches and their limitations
  - a) just using the context api
  - b) extract translation to a different file + a function to get the translation
  - c) using a package for translations

-->




## Syntax Intro

- Do a demo with the basic syntax (without wrapper component etc)

- Initial Code: https://stackblitz.com/edit/vitejs-vite-boufar?file=src%2FApp.jsx
  <!-- @LT: remember to fork -->
  
  - a) Show initial code
  - b) Fork + show demo with prop drilling
  - c) Fork + show demo with context api
    - fork
    - in App.js (exposing info):
      - create context
        - `const CounterContext = createContext();`
      - wrap all child components with the Provider
        - `<CounterContext.Provider value={counter}>`
      - export the context so that it can be used in other files
        - `export { CounterContext };`
    - in GrandChild.js (consuming info):
      - import the context (e.g.: `import { CounterContext } from '../App.jsx'`)
      - read with `const counter = useContext(CounterContext);`


App:

  ```jsx
  import { useState, createContext } from 'react';
  import Child from './components/Child';
  import './App.css';

  const CounterContext = createContext();

  function App() {
    const [counter, setCounter] = useState(0);

    const increaseCounter = () => {
      setCounter(counter + 1);
    };

    return (
      <>
        <CounterContext.Provider value={counter}>
          <h1>App component... {counter}</h1>
          <button onClick={increaseCounter}>Increase</button>

          <Child />
        </CounterContext.Provider>
      </>
    );
  }

  export { CounterContext };
  export default App;
  ```


Grandchild:

  ```jsx
    import { useContext } from 'react';
    import { CounterContext } from '../App.jsx';

    function GrandChild() {
      const result = useContext(CounterContext);

      return (
        <div>
          <h1>GrandChild component</h1>
          <h2>Value of the counter... {result}</h2>
        </div>
      );
    }

    export default GrandChild;
  ```




## Slides: Passing information between components

- https://docs.google.com/presentation/d/1VqmAj_VPWQ2htbWhEXrXT-L1KatZo1FEcixcVyAS2Z4/edit?usp=sharing

- topics: props drilling, context API, Redux




## Demo


- (Preferred) Option 1 - fork from Github:
  - Initial code: https://github.com/ironhack-rmt-WD-student-materials/react-context-api-demo
    <!-- @LT: remember to fork !! -->


- Option 2 - Stackblitz:
  - Initial code: https://stackblitz.com/edit/vitejs-vite-kx7enk?file=src%2FApp.jsx
    <!-- @LT: remember to fork !! -->


- explain goal. Demo: https://wnj6h.csb.app/projects/

- ask students to have a look & understand the initial code

- follow Student Portal
  - 2 steps: providing context + consuming

- documentation:
  - (old): https://reactjs.org/docs/context.html#reactcreatecontext
  - (new) https://react.dev/reference/react/useContext

- Final result:
  - Repo: https://github.com/ironhack-sept2024-devstructors/react-context-api-demo
  - CodeSandbox:
    https://codesandbox.io/s/m3-react-context-lesson-code-example-v2-wnj6h?from-embed


- Steps:
  1. Create the component `ThemeProviderWrapper` (for now, just a function component)
    - create the file `src/context/theme.context.jsx`
    - for now, create just a simple function component 
  2. Render `<ThemeProviderWrapper>` around the whole application.
    - We'll see that we need to use props.children
  3. In the file theme.context.jsx, create the context:
    - `const ThemeContext = createContext();`
      - Note: this needs to be outside of the function so that it can be exported
    - `export { ThemeContext, ThemeProviderWrapper };`
  4. In the file theme.context.jsx, render the Provider:
    - `<ThemeContext.Provider value="light">`
  5. From the component `ProjectCard`, read info from the contextAPI and use it to render a class
    - const result = useContext(ThemeContext)
    - `className={"ProjectCard " + result}`
  6. Add css
    - Get the css from the Student Portal
  7. Now, the them can change over time, we'll use state.
  8. ...


## Things to keep in mind

- When does a component re-render ?

  > A component calling useContext will always re-render when the context value changes.

