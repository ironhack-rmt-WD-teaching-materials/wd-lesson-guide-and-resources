

# React - Forms

<!-- 


Status: draft



*** IMPORTANT ***
*** IMPORTANT ***
-
- Start creating the FORM IN THE SAME COMPONENT WHERE WE HAVE STATE.
-
*** IMPORTANT ***
*** IMPORTANT ***






Steps:
- 1. Create the Form in the same component where we store the list of movies (ie. w/o creating a specific component for the form)

- 2. Creating a specific component for the form (when the user submits, we will need to update state on the parent component -- this is what students find difficult)


Notes:

- Forms can take much longer than it seems (!!).
- Students find it very challenging/confusing (all the part when we need to change state in the parent component etc)

-->


## Step 1: form with 1 field

- In the component where we have the list of movies:
  - Create a `<section>`

- Add form with 1 field (e.g. `title`).
  (IMPORTANT: in the same component were we have state)

- Make it a controlled component (cheatsheet below)

- Process form & add the new movie (only with "Title")


  ```js
    const newMovie = {
      title: title 
    };

    // prepare an array with the new list of movies
    const newList = [newMovie, ...moviesToDisplay]

    // update the list of movies
    setMoviesToDisplay(newList)
  ```


- Clear form upon submission

  ```js
    setTitle("");
  ```




## Step 2: form with multiple fields

Practice: React Forms

<!-- 

- Initial code: https://stackblitz.com/~/github.com/ironhack-apr2024-theScriptSociety/popcorn-time

- Alternative: create a Stackblitz app from the code we do in class.
  - note: if we use the code from class, make sure to display "rating" in the homepage.
-->


- Add a new field for "year" (or "rating")
- (Bonus) Add a new field for "image Url"
- (Bonus) Research/apply html form attributes to improve user experience (required, type=number, min, max...)

Time: 15min




## (Extra) Handling multiple inputs with a single stateful variable

<!--
- Just mention that it is possible 
- Don't implement it (takes a lot of time)
-->

See comment here: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec?permalink_comment_id=4246649#gistcomment-4246649




## (Fix) Functionality to delete movies may not work as expected

How to reproduce:
- Create 2 new movies
- Delete one of them

Problem:
- The movies that we create dynamically do not have an id.
- So, when we try to delete one of them, we are deleting all the movies that were created dynamically (all of them have "id==undefined")

Fix: generate a unique id each time a movie is added
- In order to do that, we can find out the max id in the array of movies.

<!-- 

important: generate a unique id (will make our life easier when we implement routing)

-->


Exercise: Find max in array of numbers + array of objects
- Instructions: https://stackblitz.com/edit/js-wjdmct?file=index.js
- Time: 12min.
- Solution: https://stackblitz.com/edit/js-miexdw?file=index.js




Possible solution:

```js
  const addNewMovie = (newMovie) => {
    // find out id for the movie that we want to add
    const movieIds = moviesToDisplay.map(function (elm) {
      return elm.id;
    });
    const maxId = Math.max(...movieIds);
    const nextId = maxId + 1;

    // prepare an object with the details of the new movie (inc. the id)
    const movieDetails = {
      ...newMovie,
      id: nextId
    }

    const newList = [movieDetails, ...moviesToDisplay];
    setMoviesToDisplay(newList);
  }
```






## Step 3: extract to a separate component [30min.]

<!-- 

@LT: 

- Keep this as an optional session

-->

- Move the form to a specific component <AddMovie />
- Now we need to pass a callback

Note 1:
- it may be much easier to solve it first passing state and the updater function to the child
- why it is a good idea to keep the function that updates state in the same component where you have state: https://chatgpt.com/share/680b8e66-7410-8003-999c-30d534883349

Note 2: 
- after implementing it, can add a new route and render AddMovie as a specific page




## (extra) Other Fields
- <select>
- <textarea>
- ...

> Google / React docs / Student Portal




## (Extra) SearchBox:




<!--
@todo: record video
- how to implement search box (e.g. directly in app.js)
- extract to specific component (e.g. "SearchBox" component)

- or, share link to youtube.

-->



Functionality for searchbox (asked in today's lab)
- option1: show how to do 
- option2: provide an example with code so that they can see it (e.g. in popcorn time)
- option 3: pass video
  - Implement search filter (web dev simplified, 14min.): https://www.youtube.com/watch?v=E1cklb4aeXA&t=335s


<!-- IMPORTANT: keep searchBar in App.js  -->
<!-- IMPORTANT: keep searchBar in App.js  -->
<!-- IMPORTANT: keep searchBar in App.js  -->



Example commit 1 (searchBar in App.js): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/e2c1abc8e4ef0217537e30ca07e8a87357e8f49f


Example commit 2 (extract search box to a specific component "SearchBox"): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/5f8559833f5d79b08dde32243cb9daafd378f395
- From all possible patterns (without useEffect), keeping a stateful variable "searchQuery" in App.js would be the easiest (otherwise you need to keep a second stateful variable in App.js + update it every time you add/delete a movie).




## React Forms Cheatsheet:

Gist: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec

