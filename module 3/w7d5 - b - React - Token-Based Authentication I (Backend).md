

# React - Token-Based Authentication I (Backend)


<!-- status: ready -->


<!--

PR JWT middleware simplified:

- https://github.com/ironhack-labs/lesson-code-h-react-authentication-backend/pull/14

- https://github.com/jorgeberrizbeitia/lesson-code-h-react-authentication-backend/blob/938643359c4a7edf6b28f7169a93d3b7a216df37/middleware/jwt.middleware.js


Update (May 2024):
- PR already applied to Student Portal + repo with the final code
- Ironlauncher: not yet

-->





## Intro


- Quick refresh "the concern on users' security"
  - We will not store passwords
  - We store a representation: `HASH`

<!-- @LT: explain JWT's once we reach that code in /login (not before)  -->


Roadmap: 
- [ ] Initial setup
- [ ] Functionality to create an account
- [ ] Functionality to login
- [ ] Protected routes with middleware
- [ ] Implement an endpoint to verify jwt
<!-- @LT: note, this titles doesn't match exactly the sections in this document (it's a simplification) -->


## Initial setup ("Getting Started")

Follow steps in the Student Portal but remember to fork:
- fork + rename (`!!`)
  <!-- 
    @LT: REMEMBER TO FORK!! ⚠️
    ... specially if you have permission on the original repo ⚠️⚠️  
  -->
- clone 
- npm install

Run the app
- npm run dev


Read & understand the code
- It's the same app from yesterday (project-management-server), so students should be familiar with it.

Quick test with Postman
- e.g. test 1 route



## Create User model ("User Model")

<!-- @LT: use code as it is  (do not change anything) -->

Follow code from the Student Portal.



## Functionality to create an account ("Sign Up Route")

- Discuss with students, what we may need.
- Implement (`POST /auth/signup`)
- Test with Postman
- Commit


Code summary:

  ```js
    // POST	/auth/signup
    router.post("/auth/signup", (req, res, next) => {
        /*
        - get info from req.body
        - validation
        - check if user already exists
          - if user exists: send error message   
          - if user doesn't exist....
            - generate salt + generate hash
            - User.create()
            - send response
        */
    })
  ```


## Functionality to login ("Login Route")

<!-- @LT: to speed up, can copy the whole code for this route, except of the part where we sign a jwt -->

- Discuss with students, what we may need.
- Implement (`POST  /auth/login`)
  - Start implementing the first steps (`User.findOne()`, compare password with the hash from db...)
  - If password is correct, we will sign a jwt.
  - Explain:
    - http is stateless
    - token auth / jwt (see notes below: `## Token auth / jwt`)
- Test with Postman
- Commit


Code summary:

  ```js
    // POST  /auth/login 
    router.post("/auth/login ", (req, res, next) => {
        /*
        - get info from req.body
        - validation
        - User.findOne({email: req.body.email})
        - if user doesn't exist: send error
        - if user exists...
            - bcrypt.compareSync(req.body.password, hash);
                - if credentials are correct: sign jwt + send it in the response
        */
    })

  ```



## Token auth / jwt

  <!-- LT: create diagrams (e.g. on excalidraw) -->

- JWT Diagram: https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-authentication-flow-1.png

- Token-based authentication is stateless, which means no information is stored on the server.

- Token == "a document that is signed" (anyone in possession )

- `jwt.sign` (payload + secret + header):
  - https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-signature.png

- (skip) Session auth vs Token auth
  - Each have advantages and disadvantages
  - Advantages & Disadvantages: https://stackoverflow.com/a/71552858/11298742
  - In depth comparison: https://stackoverflow.com/a/35059874/11298742

  <!--
  @LT:

  Explain also environment variables + how to configure dotenv
  (they will need that for mini-project)
  
  -->


## Create middleware for auth ("JWT Validation Middleware")

Follow code from the Student Portal (file: `middleware/jwt.middleware.js`)

- ![diagram middleware](../media/images/express-middleware.png)


<!-- @students: we don't need to remember all the details, we will use a generator to create this for us -->


## Implement protected routes ("Establish Protected Routes")

- Explain:
  - how to protect all routes for a resource (e.g. in `app.js`)
  - how to protect specific routes (e.g. in `project.routes.js`)

- Protect C + U + D
- Test with Postman
- Commit


How to send auth header in Postman: 
- https://education-team-2020.s3.eu-west-1.amazonaws.com/web-dev/m3/token-auth/jwt-auth-postman-post-auth-verify.png




## Implement an endpoint to verify jwt ("Token Verification Route")

- Implement (`GET  /auth/verify`)
- Test with Postman
- Commit







## (extra) Improve error handling

Protected routes: if we use ironlauncher, in `error-handling\index.js`, we can add the following:

  ```js
      if (err.name === "UnauthorizedError") {
        res.status(401).json({message: "invalid token..."});
      }
  ```

  Example: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server/commit/d6bea33a492aeffa16408575d136324ed72abc21



## Extra resources

Video - Session vs Token Authentication in 100 Seconds (FireShip, 2min)
https://www.youtube.com/watch?v=UBUNrFtufWo



