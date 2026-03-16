
# Codealong - Popcorn-Time-I




## Initial Setup

- open VS Code + a terminal
- navigate to your module2 directory
- create app with Vite:
  - `npm create vite@latest popcorn-time -- --template react`
- 'Install with npm and start now?': select 'no'
- cd popcorn-time
- code -r .
- npm install
- npm run dev
  - Note: in case you need to define a custom port (for example, if you have another app running in your computer): `npm run dev -- --port 3000`

- git init
- initial commit
- upload to github


## Cleanup initial code from Vite

- Cleanup App.jsx
- Delete App.css
- Cleanup index.css
- Update readme
  - eg. React Popcorn-Time - An app to practice React fundamentals (state, routing, forms)
- Commit


## Practice: Create the initial structure for "popcorn-time"

<!-- @LT: if short of time, do as a codealong instead -->

Iteration 0: Cleanup - delete initial code from Vite

Iteration 1: Create the initial structure. 
  - Create 3 function components: Header, MovieList, Footer
  - for each of them, just display a text, (eg: `<h1>this is the Header</h1>`).
  - render all of them in App


Iteration 2: Make a commit + Upload repo to GitHub

Bonus: add some css for the Header component with a specific file
    - create `Header.css` + add rules for `h1` (e.g. `color: orange`)
    - in Header.jsx, import the css file you've created: `import "./Header.css";`
    - NOTE: any css rules would apply to the whole application. To avoid this, you can do the following:
      - add a className to the parent html element of your component. Ex: `<header className="Header">`
      - in the css, add the class to all rules
        - eg: https://github.com/Ironborn-Ironhack-March-2022/react-popcorn-time/blob/main/src/components/Header.css


Time: 10min. + solve together.

<!-- @LT: explain pattern of creating one CSS file per component -->



## Import json file

From `MovieList.jsx`, load list of movies from a `json` file:
- Create `data/movies.json`
- Sample json file: https://github.com/ironhack-nov2025-theDevBlinders/w4d3-popcorn-time/blob/main/src/data/movies.json
- In MovieList.js: `import movies from "../data/movies.json";`

  <!-- IMPORTANT: add this in MovieList.js -->
  <!-- IMPORTANT: add this in MovieList.js -->
  <!-- IMPORTANT: add this in MovieList.js -->





## Display a list of movies

  - IMPORTANT: do not create a specific component

  <!-- 
  @LT:
    - Keep everything inside the "MovieList" component 
    - (do not create a specific component!)
  -->


  ```js
  {moviesArray.map( movie => {
      return <div>Title: {movie.title}</div>
  })}
  ```

- Fix: 'Each child in a list should have a unique "key" prop'

- Display year + rating + image

- Add some basic css:

  <!-- alternative: add these rules to index.css, so that they can be reused -->

  ```css
  .MovieList .card {
    max-width: 80%;
    margin: 1rem auto;
    padding: 1rem;
    border: 1px solid #666;
    box-shadow: 5px 5px 10px -5px;
    transition: 0.4s;
  }

  .MovieList .card:hover {
      cursor: pointer;
      box-shadow: 5px 5px 10px 0px;
  }
  ```

- Commit




## Removing elements from a list (will apply State)

Initial step:
- add: `<button>Delete this movie</button>`

Discuss: 
- how we can implement functionality to delete movies

Steps:
- Store the list in state (e.g. `moviesToDisplay`)
- Render the list from state (e.g. `moviesToDisplay.map()`)
- Delete Button (note: we need to pass the Id of the movie)
  ```jsx
  <button onClick={() => deleteMovie(movie._id)}>
    Delete
  </button>
  ```
- Update state when user clicks on button

```js
  const deleteMovie = (movieId) => {
    const filteredMovies = movies.filter(movie => {
      return movie._id !== movieId;
    });

    setMovies(filteredMovies);
  };
```

<!-- map vs filter vs reduce: https://miro.medium.com/max/880/0*cQwPe6QPdl_-ByOq.png -->




## Display a title with the number of movies 

<!--
@LT: 
- do this today (will help so that tomorrow we intro "lifting state up")
- IMPORTANT: display in the same component where we have the list of movies (e.g. MovieList.js)
-->

  - e.g. `<h1>Number of movies: {movies.length}</h1>`
  - IMPORTANT: display that in the `<MovieList>` component !!!
  - NOTE: many students solve it adding a new stateful variable (introduce the concept of "Single Source of Truth")



## (extra challenges)...
  
- In MovieList.jsx, display a title: `<h1>We currently have XXX movies available</h1>`

- For each movie, display genres (note: it's an array)

- Implement a button "Show only top-rated"
  - When the user clicks, display only movies with rating > 8

- Add button to sort by rating

- Add favIcon
  - Can use these images: https://github.com/Ironhack-Team-Triangle-July2021/ironhack-cinema/commit/f4cf21c91608b1fdf95b359031e676c90cbf8c3f#diff-09e657b7706f48b0af84577d8d340912648fa2d247d808a18e26e3459df1a26b

- Research: JSX spread attributes.
  - `<Movie {...movieObj}>`
  - Demo: https://stackblitz.com/edit/vitejs-vite-eu9l16?file=src%2FApp.jsx
  - More info: https://reactpatterns.js.org/docs/jsx-spread-attributes/

