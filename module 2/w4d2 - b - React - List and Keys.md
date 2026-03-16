
# React - List and Keys




## Refresh: working with arrays (skip?)

<!-- Goal: refresh forEach() & map() -->

- Instructions: https://stackblitz.com/edit/ih-react-exercise-with-arrays?file=index.js
  
- How: solve together / work in pairs
- Time: 15-20min.



- Explain: 
    - forEach() will return undefined
    - map() returns an array


- Solve together:
  - diagram map: https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_c465728a5460c8d562936d4f1b5d18cc.png
  - map vs filter vs reduce: https://miro.medium.com/max/880/0*cQwPe6QPdl_-ByOq.png


- Possible solution (w/o bonus): https://stackblitz.com/edit/ih-react-exercise-with-arrays-vefnrt?file=index.js

- Possible solution with bonus: https://stackblitz.com/edit/ih-react-exercise-with-arrays-3dwodd?file=index.js








## (skip) Intro: working with lists (arrays) in React


- What we've done so far

  ```jsx

    const tweetsArray = [];

    // ...

    <Tweet tweet={ tweetsArray[0] }>
    <Tweet tweet={ tweetsArray[1] }>
    <Tweet tweet={ tweetsArray[2] }>

  ```

- We will often work with arrays of objects but this syntax is not flexible enough.
  - e.g. if we have an array with 200 elements
  - e.g. if we don't know how many elements we will have in the array


- Inside <Main />, create 3 div's with a movie
  <!-- @update: use MovieList instead of Main -->

  ```jsx
    <div className="Main">

      <div>movie one</div>
      <div>movie two</div> 
      <div>movie three</div>

    </div>
  ```

- Put those 3 div's in an array and show how it is possible to display an array

  ```jsx
  const list = [
    <div>movie one</div>, 
    <div>movie two</div>, 
    <div>movie three</div>
  ];
  
  // ....
  
  {list}
  ```


- TAKEOVER: 
  - in JSX, we can render an array of elements (those elements can be html or any valid JSX)





## .map() - Demo I (with an array of strings)

<!-- 

Notes:
- Continue working on the same app from yesterday
- Before we import the json file, we'll do a quick demo with an array of strings 

-->


Create a component `MovieList`.


  ```js

  const movies = ["The Godfather", "Forrest Gump", "Gladiator"];

  // ...

  {movies.map()}

  ```



## .map() - Demo II (with an array of objects)


Create `data/movies.json`:


```js
[
  {
      "id": 1,
      "title": "The Godfather",
      "year": 1972,
      "genres": ["Crime", "Drama"],
      "imgURL":
          "https://m.media-amazon.com/images/M/MV5BM2MyNjYxNmUtYTAwNi00MTYxLWJmNWYtYzZlODY3ZTk3OTFlXkEyXkFqcGdeQXVyNzkwMjQ5NzM@._V1_UY268_CR3,0,182,268_AL_.jpg",
      "rating": 8
  },
  {
      "id": 2,
      "title": "Forrest Gump",
      "year": 1994,
      "genres": ["Drama", "Romance"],
      "imgURL":
          "https://m.media-amazon.com/images/M/MV5BNWIwODRlZTUtY2U3ZS00Yzg1LWJhNzYtMmZiYmEyNmU1NjMzXkEyXkFqcGdeQXVyMTQxNzMzNDI@._V1_UY268_CR1,0,182,268_AL_.jpg",
      "rating": 7
  },
  {
      "id": 3,
      "title": "Gladiator",
      "year": 2000,
      "genres": ["Action", "Adventure", "Drama"],
      "rating": 6
  }
]
```


Import:

```js
import moviesArr from "../data/movies.json";
```



## Practice: iterate through an array with .map()

Initial code: https://stackblitz.com/edit/vitejs-vite-y9qv3w?file=src%2FApp.jsx


Step 1: 
- In EventsList.jsx, import the json file.
- `import events from "../data/events.json"`

Step 2:
- In EventsList.jsx, for each element of the array, display the title and the location.

Bonus: 
- In the json file, you will find more info about each event (image, categories...). Use that to display more info about each event.


Time: 10min.

Solution: https://stackblitz.com/edit/vitejs-vite-6y5hah?file=src%2Fcomponents%2FEventsList.jsx



## Explain "key" prop

> Warning: Each child in a list should have a unique "key" prop.

