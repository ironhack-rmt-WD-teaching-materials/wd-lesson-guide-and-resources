

# Creating a Backend API


<!-- 

Status: ready


@LT: do this with the example we have in the Student Portal (projects + tasks )


@todo:
- if we use json-server, create recording

-->






## Discover: REST APIs

Task 1: watch this video 
  - Video: What is a REST API? (explains RESTful) (6 min., Mosh)
  - https://www.youtube.com/watch?v=SLwpqD8n3d0

Task 2:
  - Define the endpoints for a REST API the allows to CRUD "recipes"
  - Example:
    - GET /recipes -- get a list of recipes
    - ...
    - ...

Time: 12min.


---


- (skip for now) Slides: 
  <!-- @LT: skip for now (we will see REST in detail in m3) -->
  - https://docs.google.com/presentation/d/194i1dCV2vpqTN5T3yC5lysvfS-_fnEkok97QpaOtb3w/edit?usp=sharing




## Intro to this unit

- project 2 requirements: 
  - CRUD on an API

- Options:
  - Option 1: research & use an existing external API
    - example: https://github.com/public-apis/public-apis
  - Option 2: create your own mock API with json-server

- Topics we will see in this unit:
  - How to create an API (quick way)
  - How to test it
  - How to deploy

- json-server
  - it's an npm package.
  - allows you to create a mock REST API from a JSON file
  - ideal for prototype and mock APIs (e.g. you're working on the frontend & need to wait for the backend to be ready).



## JSON Server Setup - Quick Start

Follow steps in the Student Portal.

<!-- Remember to fork -->


## (skip) JSON Server Setup - Step by Step guide

Skip 

(it's equivalent to the one in "quick start")




## JSON Data and Endpoints

- JSON Server uses a specific JSON file structure to create REST API endpoints.

- Each key in your db.json file becomes an API endpoint


## Requesting All Records

- GET /projects
- GET /tasks


## Requesting a Single Record by id

- GET /projects/1
- GET /projects/2


## Invalid Requests

- JSON server will return an empty object


## Relationships

- Special key: same name as the related endpoint followed by Id
- Example: `projectId`




## Embedding Related Records

- `?_embed=tasks`
- Example: GET http://localhost:5005/projects/1?_embed=tasks




## Test with Postman


- (brief) Some options to send http requests:
  - Tools:
    - Postman
    - cURL
    - ...
  - JavaScript code:
    - http request (https://stackoverflow.com/a/4033310/11298742)
    - fetch()
    - libraries (e.g. axios)



Install Postman
  - https://www.postman.com/downloads/
  - Don't need to create an account (link at the bottom: "Skip")


How to send a request:
- Example: GET https://dog.ceo/api/breeds/image/random



## Test REST API endpoints

CRUD:

- Create: `POST /projects`

  ```json
  {
    "title": "Create a mock API using json-server",
    "description": "Create an API that we'll consume from  our React App"
  }
  ```

- Read (all): `GET /projects`

- Read (single project): `GET /projects/:id`

- Update: `PUT /projects/:id`

- Delete: `DELETE /projects/:id`


Test second resource: "tasks"
- `POST /tasks`
- `GET /tasks`



<!-- IMPORTANT -->
<!-- IMPORTANT -->

IMPORTANT: explain that json-server does not do any validation (you can put any data)

<!-- IMPORTANT -->
<!-- IMPORTANT -->



## Deployment

- Create repo + commit + upload to GitHub
- Deploy on Adaptable.io
  - template: node
  - db: no
  - waiting for deployment meme: https://i.pinimg.com/736x/63/05/0a/63050ae9df594c789a0710ab02559837.jpg


## (extra) Test in production

- Test with Postman



## (extra) Connect our React app

- Connect our React app to the API in production
  (for now, don't use env variables, just connect directly to production)


## Limitations

1. Data persistence
  - Adaptable provides an "ephemeral" file system: when the app is not in use for some time they discard all changes. Then, when the app needs to run again, it gets the latest version of the code from GitHub.
  - Many other hosting services (Heroku, Render.com, etc) work like that nowadays, specially in the free tier.
  - As a result, data will be restored from your db.json periodically.
  - ie. any data added manually (ie. anything that is not in db.json), will be overwritten after some time.
  - This will happen when you push (adaptable will redeploy) but also periodically (even without pushing code to the remote repo)


2. Data validation

3. No support for users / auth


<!--

Also: confusion 2 repos etc (to avoid this, do not run in localhost)

-->



## Summary / Steps to follow

<!-- @LT: share these steps with students -->

1. Fork this repo: https://github.com/ironhack-labs/json-server-backend.git
2. Clone your fork + Open with VS Code
3. Modify the file db.json  according to your requirements
  - Note: if you want to test locally, you can npm install + npm run dev . If you prefer, you can skip this step and test directly after you deploy,
4. Commit + Push
5. Deploy on Adaptable
  - Template: select "node.js"
  - Database Type:  select "none"



## Other resources

- JSON Server Auth: https://github.com/jeremyben/json-server-auth

- Validation (not supported, can be done with middleware): https://github.com/typicode/json-server/issues/76

