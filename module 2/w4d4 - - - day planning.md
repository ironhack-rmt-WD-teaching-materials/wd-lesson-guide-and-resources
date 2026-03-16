
# w4d4


<!-- 

- We'll continue working on "popcorn-time"

-->



## Refresh

Show the app we were building yesterday
- list of movies loaded from `json` (in most apps, it would come from an API)
- component hierarchy (see react dev tools + see code)

- Refresh syntax useState():

  ```jsx
  const [isLoggedIn, setIsLoggedIn] = useState(false);
  ```


  ```jsx
  { isLoggedIn === true 
      ? <h1>Welcome to Popcorn Time!</h1> 
      : <h1>Sorry, you need to login</h1>
  }
  ```

- props vs. State:

    - When should we use the PROPS:
      - Pass information to a child component
      - e.g. reusable component that has different behavior depending on info that it receives.

    - When should we use the STATE:
      - Store information that belongs to a component
      - Can change over time
      - We want to reflect the changes in the UI (JSX)

    - A Component will Re-render if:
      - receives new props from the outside
      - its own state changes

- Remember:
  - NEVER MODIFY STATE DIRECTLY 
  - State Updates May Be Asynchronous



## Day Planning
 
- LAB Q&A [20m]

- Refresh (see notes above) [10m]

- Callbacks & Lifting State Up [2h]

- Routing:
  - Examples of routing: 
    - https://brews-and-bites.netlify.app/
    - airbnb
  - Routing intro [1h]
  - Routing advanced - url params [1h]
    <!-- Implement routing in the app "popcorn-time" -->
  - Routing advanced - query string [10m]
    - (just some notes / show cheatsheet) 
    - In lab "React Cohort Tools": not needed (as of may24)
    - In lab "React Stack Tracker" it's a bonus iteration.



## Active Learning

- (individual) LAB | React Cohort Tools

- (in pairs) Mini Project | React App (Day 3)

- Bonus: 
  - LAB | React Stack Tracker


