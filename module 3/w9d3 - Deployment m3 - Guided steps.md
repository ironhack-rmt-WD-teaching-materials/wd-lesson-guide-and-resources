
# Module 3 Deployment


Slides (draft): 
<!-- @LT: can just use the first slide with the architecture -->
- https://docs.google.com/presentation/d/19VRo2Bjae3q8b5wNCMKpEG-DrlDN_4Z3-XdHcP4CHZo/edit?usp=sharing


Backend Repo: 
<!-- alternative: fork repo from the Student Portal + check code from prev. cohort -->
- https://github.com/ironhack-demos/demo-deployment-project-3-backend

Frontend Repo: 
<!-- alternative: fork repo from the Student Portal + check code from prev. cohort -->
- https://github.com/ironhack-demos/demo-deployment-project-3-frontend



<!-- 
IH credentials for Vercel: 
- login with "lj+ironhack-class-codealongs@ih.com"
- will send a verification email
-->



---


<!-- @LT: before we start, share this roadmap with the students -->


## Step 0 - Prepare the frontend for deployment

- (optional) git stash
- In the Frontend: make sure to use environment variables for the API URL


## Step 1 - DB
- Deploy the Database in MongoDB Atlas


## Step 2 - Backend

- Deploy the Backend in Vercel

- Important: for the environment variable with the location of the database, avoid the slash at the end of the url (ie. avoid the "trailing slash")

- Notes: 
    - At this point, sometimes you may get an error connecting to the DB (e.g. `users.findOne() buffering timed out after 10000ms`)
    - We'll fix that in the next step


## Step 3 - Fix: make sure the DB connection is ready in serverless environments like Vercel

- Why:
    - Vercel is a "serverless" environment
    - There isn't dedicated machine running 24/7. Instead, each request may start a new process to handle the incoming request.
    - As a result, when our server receives a new request, it may execute the code inside `require("./db")` (which will connect to the DB, but it may take time)... and, immediately, execute the route corresponding to the incoming request -e.g. POST /projects, which would need to do Project.create()
    - Basically, we have a race condition where the connection to the DB may or may not be ready by the time we send a query to the database

- How to solve it:
    - We will implement the connection to the DB as a middleware function
    - Each time we receive a request, we will make sure we're connected to the DB... and only then invoke the next middleware function.

- Example commit: 
    - https://github.com/ironhack-nov2025-theDevBlinders/demo-deployment-m3-backend/commit/567b2eae38cabe18dc1bc5be5bc1dc5c71eda075
    - IMPORTANT: replace `project-management-server` with your DB name 👈
    - Files changed:
        - `db/index.js`: replace all the code in that file
        - `app.js`: import connectDB + add the code to invoke it for each request


## Step 4 - Frontend

- Deploy the Frontend in Vercel
- note: mention the possibility of buying a domain to make it look better in their portfolio.



## Step 5 - Fix: error reloading a page (and/or when you share a link other than the homepage)

- Problem: When you reload a page other than the homepage (e.g. /projects), you get a 404 error
- How to solve it: do some research

<!--  @LT: do Step 5 + Step 6 as a "class activity" -->

- Solution: https://chatgpt.com/share/6970e390-d304-8003-8fdc-9b3dcf124140


## Step 6 - Submit project URLs
- Submit URLs in the Student Portal
- Screenshot: https://drive.google.com/file/d/1un8OZoDSpSr33VmqziNPOJT8qGVpAwch/view?usp=sharing
- Deadline: today, 5pm


## Step 7
- (optional) git stash pop
