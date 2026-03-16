

# React - Building the Rest API

<!--
@todo: improve planning & notes
-->


<!--


- Codealong final result:
  https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commits/main


  note: the last commits are for Auth ("functionality to register" + "functionality for authentication")


- Approach: 
  - option 1: codealong (takes quite a bit of time, 4h )
  - option 2: giving students the code & ask them to try to understand it ? (they may feel overwhelmed)

-->




## What is REST API ?

- Slides (REST + endpoints we will implement): 
  https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing

- Video: What is a REST API? (explains RESTful) (6 min., Mosh)
  - https://www.youtube.com/watch?v=SLwpqD8n3d0





- (Bonus) Exercise:
  - You need to define a REST API for characters (create a character, update etc).
  - Your task: following REST principles, define the endpoints for the following actions:
    - List of all characters
    - Details of a specific character
    - Create a new character
    - Update a specific character
    - Delete a specific character
  - Time: 5-10min.





## Codealong: Initial Setup

- Create directory: `mkdir project-management-fullstack`
- Enter inside this directory: `cd project-management-fullstack`
- Ironlauncher: `npx --yes ironlauncher@latest project-management-server --auth --json`


<!-- IMPORTANT  -->
<!-- IMPORTANT  -->
<!-- IMPORTANT  -->
  
IMPORTANT:
- Initialize with `ironlauncher --auth --json` 

<!-- IMPORTANT  -->
<!-- IMPORTANT  -->
<!-- IMPORTANT  -->




## If dependencies missing...

Fix: ironlauncher not installing dependencies
  - see `Express - Ironlauncher.md`



## Part 2:

- run the app: `npm run dev`

- Understand the code we have (created with ironlauncher --auth)


- Explain Express `res.json()`
  res.send()
  res.render()
  res.redirect()
  res.json()


- Explain ironlauncher commands:

`npx ironlauncher projectA --auth`
  the CLI will ask if you want to create "views"
  creates views directory & uses res.render()
`npx ironlauncher projectB --json`
  no views & res.json()
  (note: doesn't generate middleware directory, assumes not needed)
`npx ironlauncher projectC --auth --json`
  functionality for auth, middleware and no views (res.json())
  Project 3: use this option


- Main difference in the Backend from module 2:
  - we send json (we don't need to create views)
  - we will test with Postman
  - also, we will be running our express app in a different port (e.g.5005)


- Explain goals & endpoints
  (see table with endpoints in the Student Portal)


- Plan together
  - models
  - routes



## Part 3: codealong

- Models:
  - Refresh embedded vs. Reference


- Codealong: 
  - option1: share the plan & build together in the main session.
  - option2: advanced students can do that in pairs in breakout rooms.


Routes (implement each one + TEST WITH POSTMAN):
1. POST /projects
2. POST /tasks
3. GET /projects
4. GET /projects/:projectId
5. PUT /projects/:projectId
6. DELETE /projects/:projectId

- Each route: implement + TEST WITH POSTMAN
- 1, 2, 3: 
  - copy code from Student Portal
  - read together + test
- 4, 5, 6: 
  - copy code from Student Portal
  - ask students to read & understand code + test
  - time: 15min.

Bonus: full CRUD on tasks
  - GET /tasks
  - GET /tasks/:taskId
  - PUT /tasks/:taskId
  - DELETE /tasks/:taskId


- Minor improvement: when a project is deleted, remove also the associated tasks.
  - note: make sure to import Task model

  ```js
  Project.findByIdAndRemove(projectId)
    .then( deletedProject => {
      return Task.deleteMany( { _id: { $in: deletedProject.tasks } } );
    })
    .then(() => res.json({ message: `Project with id ${projectId} & all associated tasks were removed successfully.` }))
    .catch(error => res.status(500).json(error));
  ```  



- Enable CORS requests (see below)



# CORS

- Slides: 
  https://docs.google.com/presentation/d/1ccck25g9VXNxWA-GaXquyczZD2VnfD9Zx9lKKgFD2dk/edit?usp=sharing

  <!-- @todo: improve slides -->
  <!-- @todo: improve slides -->
  <!-- @todo: improve slides -->

Note:
- with "ironlauncher --auth --json", CORS is already implemented.


## EXTRA CHALLENGES

Some options for extra challenges (they're not exclusive, can be combined):

- Bonus 1: full CRUD on tasks
  - plan endpoints for tasks, following REST
  - implement the routes for those endpoints

- Bonus 2: plan a React app to interact with this API
  - how would you build it (component structure etc)?

- Bonus 3: build a React app to interact with this API
  - it is the next lesson in the Student Portal but some advanced students may want to start building it.
  - main thing to keep in mind is that you will need to enable CORS requests on the API
we will explain what is CORS and all those details a bit later but the code to do that is in "React | Building the Rest API" > "Enable CORS requests"

- Bonus 3: deploy your API on fly.io + mongoAtlas
  - Next week  we will do deployment for project 3 but, if you want, you can also put this project online. 
  - You would be able to test it with Postman/Compass, just as we're doing on localhost.



<!-- 
@LT
- (if we do React as self-guided) explain how to run 2 projects in dev -->
