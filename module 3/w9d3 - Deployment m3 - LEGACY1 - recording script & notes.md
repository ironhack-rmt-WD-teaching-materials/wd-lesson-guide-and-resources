
# Module 3 Deployment (recording script)




Slides (shown in the video): 
- https://docs.google.com/presentation/d/19VRo2Bjae3q8b5wNCMKpEG-DrlDN_4Z3-XdHcP4CHZo/edit?usp=sharing


Backend Repo: https://github.com/ironhack-demos/demo-deployment-project-3-backend


Frontend Repo: https://github.com/ironhack-demos/demo-deployment-project-3-frontend





### 0. Using env variables for the location of our API


Summary:
- Why we need an environment variable for the location of the API
- How to create and use environment variables in Vite
- Examples: how to modify "all" our http requests so that we use an environment variable instead of a hardcoded URL.
  - The video shows examples with "axios.get()", "axios.post()", etc; but it also mentions that the same can apply if they're using a service.
- Test the functionality in your dev environment + Commit + Push




### 1. Intro + deploy our DB on MongoDB Atlas



Before recording:
- [ ] logout from MongoDB Atlas



Summary of steps:

- Intro:
  - Architecture project 3 (front, back, db) + the services where we'll deploy each
  - How we will work (working in pairs, make sure both follow the recording)
  - Some things to keep in mind (deployment takes time, keep 100% attention etc)
  - Steps that we'll follow:
    1. db
    2. backend
    3. frontend


- Deployment on MongoDB Atlas
  - Create an account
  - Login
  - Create a new project
    - IMPORTANT: create a new project for each app (limit of one free DB per project)
    - NOTE: the UI will probably change over time.
    - choose a name (example: "project-3-deployment-demo")
    - optional: add project partner as collaborator
  - Create a cluster
    - Free tier
    - Choose a region close to your users
  - Configure access (Security > Quickstart)
    - Create a user (avoid uppercase and white spaces)
    - Grant access from all ip addresses: (Pattern for all ip address: `0.0.0.0/0`)
  - Wait for Cluster to be ready
  - Connect to Cluster
    - get url
    - replace password
    - optional: add db name at the end (e.g. `mongodb+srv://luis:ilovepizza@cluster0.9csqh.mongodb.net/project-management`)
  - Test DB connection with Compass




### 2. Deploy our Backend on Render.com + configure UptimeRobot



Before recording:
- [ ] revoke github app (note: do that on Render.com, through the option "Credentials")
- [ ] logout from Render


Summary of steps:

- Deploy on Render.com
  - Create an account
  - Login
  - Create a new workspace
    - IMPORTANT: create a new workspace for each app (limit of one free app per workspace)
    - Choose a name for your workspace (e.g. "project3" / "project3-deployment-demo")
    - Choose "hobby" plan
  - Create a new "Web Service"
    - IMPORTANT: select `Git Provider` (from "Public Git Repo", it may not do automatic deploys)
    - You may need to grant permission to your organization
    - Search or Paste url of your repo
    - Choose name
      - Note: this name will be public
      - Example: our-cool-project-management-app
      - Url would be: https://our-cool-project-management-app.onrender.com
    - Branch (e.g. "main")
    - Root directory
      - example of when you may need it: https://github.com/ironhack-rmt-WD-student-materials/library-project-deployment-demo-2
      - example where you don't need it (code and package.json in the root of your repo): https://github.com/ironhack-demos/demo-deployment-project-3-backend
    - Start command: "npm run start" (in our case, since we're using npm)
    - Instance Type: "Free"
    - Environment variables
      - In your backend code, search "process.env"
      - Example:
        - `TOKEN_SECRET`
        - `ORIGIN`
        - `MONGODB_URI`
    - Click "Deploy web service" + wait a few moments
    - (( pause recording & force build error ))
    - Explain build vs. runtime errors
    - Show example of a build error
      - Example: `const something = require("./does/not/exist");`
      - Example: `const Task = require("./models/Task.model");`
        - see logs on Render
        - see that the app is already breaking in my dev environment
        - commit + push
        - an automatic deploy will be triggered
    - (( pause recording & force runtime error ))
    - Show example of a runtime error
      - Example: "Error: amount is not defined"
      - Note: depending on the backend code, we may need to add a traces for debugging:
        - add console.log()
        - commit + push
        - wait for automatic deploy
        - test again & see the logs

- Test API
  - Test all endpoints with Postman
  - Show examples: 
    - POST  `/auth/signup`
    - POST  `/auth/login`
    - POST  `/projects`
    - GET   `/projects`

- Explain limitations of the free tier
  - slide 11
  - Render:
    - If we don’t receive any request in 15 min., the next one will take a while to process
    - ![screenshot-render-free-plan](../media/images/render%20-%20limitations%20of%20the%20free%20plan.png)
  - MongoDB Atlas: 
    - If the app is not used for 60 days, it would stop working

- Create health endpoint
  - code: https://github.com/ironhack-class-codealongs/test-render-c/commit/fe24863533d5cd1d442071fcc881daf9ac1cdcec
  - commit + push
  - wait for automatic deploy
  - test with Postman

- Configure UptimeRobot
    - Create an account
    - Login
    - Create a "New Monitor"
    - Paste URL
    - Choose Monitor Interval: 12 minutes
    - Click "Create Monitor"


- Recap + some things to keep in mind:
  - Architecture (slide 19):
    - DB 
    - Backend Code
    - UptimeRobot
  - Automatic deployment
    - whenever you push on the main branch, it will trigger a deploy
  - Databases (slide 17)
    - keep in mind that now we'll have different databases (3)
    - each of your databases will have different data
    - if you want to see the data in production, you can use Compass
  - Errors / debugging
    - check logs on Render.com






### 3. Frontend + Summary:




Before recording:
- [ ] have frontend repo ready
- [ ] revoke app en Netlify ?


Summary of steps:


- Deploy on Netlify
  - Create an account
  - Login
  - "Add new site" > "Import an existing project"
  - Connect to Github 
    - may need to give permissions (show the option "add another organization")
    - select the repo you want to deploy
  - Choose site name (example: "our-cool-app" / "project-management-app")
    - note: click "check availability" to see the final URL
  - Build command: "npm run build" (Vite)
  - Environment variables:
    - In your frontend code, search "import.meta.env"
    - Example:
      - VITE_API_URL 
        - Important: for the api url, pay attention to the trailing slash (`!!`) (check .env/code in dev environment)
  - Click "Deploy" + wait a few moments
  - (( break ))
  - Build errors & runtime errors in the Frontend:
    - Build errors: will appear on Netlify
      - Mention an example: `import Navbar from "../../../components/Navbar";` (wrong path)
      - You'd need to: Fix + test locally + commit + push
    - Runtime errors: will appear in the console in the browser
  - Test our Frontend:
    - Open the URL
    - Explain: 
      - In my case, I can see the homepage
      - That may not happen to all of you. Some of you may get an error when you open the homepage
        - If that happens, check if there's any error in the console.
      - It may happen that you have an error already in the homepage and, if not, you will probably have one when you create an account
      - Show error when we try to create an account (CORS error)
        - See backend code & check that we have cors configured
        - Create environment variable in Render.com + wait for Auto-Deploy
          - IMPORTANT: for "ORIGIN", do not include white-spaces or a slash at the end (`!!`)

  - Test all the functionality of your React app
    - Note: if there's any error in localhost, you will probably have it in production


  - Fix: error when the user reloads a page ("Page Not Found")
    - info: https://answers.netlify.com/t/support-guide-direct-links-to-my-single-page-app-spa-dont-work/126
    - Create the file `/public/_redirects`
      - Important: notice that it's inside public (not inside src)
    - /*    /index.html   200
    - Commit + push + test


- Recap + some things to keep in mind:
  - Architecture (slide 19):
    - DB 
    - Backend Code
    - UptimeRobot
  - In case you have errors:
    - In case you have an error in the frontend: check the console in the browser
    - In case you have an error in the backend: test with postman + check the logs in Render.com 
    - In both cases: try to debug understand what is happening
  - Automatic deployment
    - whenever you push on the main branch, it will trigger a deploy


- (not in the video) Remember to submit project urls in the Student Portal (3 urls)
  - Show: week 9


Bonus (skip):
- git branches 

Notes:
- CI = false ? not needed really





---
---
---






## How to fix "Not Found" error

Problem: If the user reloads a page on netlify, they get a "Not Found" error

Answer: https://answers.netlify.com/t/support-guide-direct-links-to-my-single-page-app-spa-dont-work/126

note: `/public/_redirects` needs to go in /public directory

```
/*  /index.html  200
```






## (skip) Seed file (seed data on production DB)

<!-- @LT: share instructions on Slack (no need to demo) -->
<!-- @todo: create a gist -->


To seed data on production, you can do the following:

  1. Modify your seeds file so that it points to the production DB (see screenshot)
    - Note: save the changes on this file but do NOT make a commit.

  2. Execute your seeds file in your computer: `node bin/seeds.js`

  3. Confirm that data was created on production (you can do that on MongoDB Compass, connecting to your production DB)

  4. Undo the changes we made in "step 1" (so that they are not added to the repo)
  - Note: this step is important, otherwise you may be pushing your DB credentials to github.

  
![Seed on production](../media/images/seed-adaptable.png)


