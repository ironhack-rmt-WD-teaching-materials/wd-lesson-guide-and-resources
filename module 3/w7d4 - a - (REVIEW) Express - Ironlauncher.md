

# Express - Express Generator


Summary:
- what is a generator
- ironlauncher
  - what it is
  - how to setup
  - understand how it works
- seed file




## Intro

- when building new applications, we repeat a lot of the work (especially for the initial setup)

- IronLauncher
  - npm package (https://www.npmjs.com/package/ironlauncher)




## IronLauncher

Create a project with Ironlauncher;

- Open VS code + a terminal
- Navigate to your module2 directory

- Setup your project (with NPX):

  <!-- OLD `npx --yes ironlauncher library-project` -->
  - `npx ironlauncher@latest library-project`
      <!-- note: students get a message "do you want to install 0.39..." choose yes -->


- Choose: `Views`
- Choose: `No auth`


    <!-- 
      with Auth:
      npx  --yes  ironlauncher@latest  our-cool-project-backend  --auth   --json
    -->


    Note: ironlauncher automatically creates a folder with the name of the app.


- Explain `npx` (vs. npm install)

- Explain...
  - Open `package.json` & explain scripts (start / dev)
  - Opinionated (dependencies + structure)
    - we could use other packages
    - the structure created by the generator is just one of many ways to structure Express apps
  - dependencies
  - dev dependencies
  - run: `npm run dev`
  - `.env` & environment variables
    <!-- IMPORTANT: explain `environment variables` here -->
  - `.gitignore`
  - general folder structure (`/models`, `/routes`, `/views`)
  - general flow of the application (starting from server.js)
    - NOTE: get the "BIG PICTURE"
  - error handling
  - express.Router (create mountable route handlers)
    - https://expressjs.com/en/guide/routing.html#express-router
    - show how we can add more routes



> The app structure created by the generator is just "one of many ways" to structure Express apps.



## Fix: ironlauncher not installing dependencies


### Dependencies "without" auth:

```shell
npm install cookie-parser@1.4.6 cors@2.8.5 dotenv@16.4.5 express@4.19.2 mongoose@8.4.0 morgan@1.10.0

npm install nodemon@3.1.0 --save-dev
```



### Dependencies "with" auth:

```shell
npm install bcrypt@5.1.1 cookie-parser@1.4.6 cors@2.8.5 dotenv@16.4.5 express@4.19.2 express-jwt@8.4.1 jsonwebtoken@9.0.2 mongoose@8.4.0 morgan@1.10.0

npm install nodemon@3.1.0 --save-dev
```






## Flags (options)

- See documentation: https://www.npmjs.com/package/ironlauncher




## Creating our first app

- Goal: we're going to create an app for a Library (we'll have CRUD functionality for books)

- Start VS Code live session

- Git init + commit

<!-- @LT: create initial commit + push -->



### Adding the model

- Add Book model (Student Portal: 'Adding the model')
  `models/Book.model.js`

  - IMPORTANT: follow the same model as Student Portal (so that we can use seed file later)

  - Example: https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong/blob/main/models/Book.model.js


### Seed File

- Create seed file (Student Portal: 'Creating a seed file')
  - Explain: What is a seed file + why it is useful
  - Add the code or codealong (`/bin/seeds.js`)
  - Run seed file (`$ node bin/seeds.js`)
  - Check data is loaded (Compass)

  - Example Seeds File: 
    - https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong/blob/main/bin/seeds.js



    <!--
    @LT: drop DB library-project (from previous cohorts)
    -->



