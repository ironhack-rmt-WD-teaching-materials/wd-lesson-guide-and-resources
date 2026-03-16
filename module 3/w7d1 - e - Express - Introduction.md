
# Express - Introduction


<!-- 

update m2-m3 swap:

- there's a few new concepts
  - Request Logging
  - Middleware
  - Working with JSON


@todo: 
- review planning & update Demo (ie. which app we build)
  - for example, for the demo, it may be more interesting to build a spotify-like api (artists, albums). In that case, change the exercises (some of them are already on that topic). Also, notice that this same app is used for the demos in the coming days.

Codealong:
- create "IronRestaurant" (iron-restaurant)
- we will evolve it during the following days

-->





## Part 1: some concepts


- Refresh HTTP Verbs
  - slides (Refresh "How the internet works"): https://docs.google.com/presentation/d/1-EgP1r7duakjZ6DXfReHIu9cYwEheAWEd_vDL7JtYiU/edit?usp=sharing



- What is a Framework and why we use it

  <!-- @todo: create slides -->

  - Framework vs library:
    - https://www.digitaltechmedia.in/wp-content/uploads/2020/11/framework-vs-library-dtm.jpg
    - https://qph.cf2.quoracdn.net/main-qimg-b21ba6c5e7ab388225dfafa0c96075d5-pjlq


- Brief intro to Express.js
  - MERN stack
  - MERN logos: https://miro.medium.com/max/1400/1*FVtCyRdJ6KOr4YswTtwMeA.jpeg




## Part 2: Demo - "IronRestaurant"

<!-- 

Some notes below (not comprehensive)

Follow Student Portal.

-->


- Intro: explain what we will be able to build at the end of the day
  - See demo: https://stackblitz.com/edit/stackblitz-starters-wgmw4y?file=app.js
  - Routes:
    - GET "/"       (html)
    - GET "/contact"  (html)
    - GET "/pizzas" (json response)
  - main difference with module 1: backend code


- We will implement...:
    - home
    - contact
    - one image + css
    - nav menu
    - "endpoint" to get a list of pizzas
    - also:
      - Request Logging (morgan)
      - Middleware
        - JSON Middleware - express.json()



- (skip) ask students: how do we want to call our pizza company



Initial setup:

  ```shell
  mkdir module3
  cd module3
  mkdir iron-restaurant
  cd iron-restaurant
  touch app.js
  code -r .
  npm init --yes
  npm install express
  ```



Code:

  <!--
  @LT: 
    - start with one route, add the other one later
    - explain routes in detail
    - run with "node app.js" + explain how to kill the process (Ctrl+C)
  -->


  ```js
  const express = require("express");

  const app = express();


  // app.get(path, code);
  // app.get(path, function(req, res, next){});


  app.get("/", function(req, res, next){    
      console.log("we received a GET request for the HOME page...");
      res.send("This is the homepage");
  })


  app.get("/contact", function(req, res, next){
      console.log("we received a GET request for the CONTACT page...");
      res.send("This is contact page");
  });


  app.listen(3000, function(){ console.log("Server listening on port 3000...")});

  ```


Refactor:
- Store PORT as a constant




## Practice: creating routes in express

Initial code: https://stackblitz.com/edit/stackblitz-starters-pgmave?file=app.js

Iteration 1 - Create a route for the homepage:
- Request: GET "/"
- Response: in the response, send the message "This is the HOMEPAGE"

Iteration 2 - Create a route for the about page:
- Request: GET "/about"
- Response: in the response, send the message "This is the ABOUT page"

<!-- IMPORTANT: 

- app has nodemon already installed, when you save the code, browser will automatically update

- explain how to test each route (create a route to "/demo" & show how to send request on Stackblitz in the browser)

-->

Bonus:
- research about "req" and "res" in express (what they are, which properties and methods they have)


Solution:
- https://stackblitz.com/edit/stackblitz-starters-6yawrs?file=app.js

Time: 12min.


## Sending html with res.send()

Explain:
- in res.send(), we can send a string or html content



## Watch mode (nodemon & node --watch)

<!-- 

March25:
- Student Portal: now it uses "node --watch"
- Labs and ironlauncher: still have "nodemon" (as a dev dependency)

-->


Option 1:

- Install nodemon as a global dependency: `npm install -g nodemon`

- Some students have problems installing `nodemon`.
  - Just use `sudo`.
  - Alternative: `npx nodemon my-file.js`

- (skip) show example when nodemon crashes (e.g. syntax error)


Option 2:
- Run with `node --watch app.js`



## package.json scripts

Add scripts to package.json:

```json
"scripts": {
  "dev": "nodemon app.js"
},
```



## Static Files

- Explain what are static files (see Student Portal)



Image for the homepage:
- Create the directory "public"

- Create the directory "public/images"

- Download an image file: 
  - https://raw.githubusercontent.com/ironhack-demos/demo-express-iron-restaurant-w7d1/refs/heads/main/public/images/home.jpg

- Configure express:

  ```js
  // ...
  const app = express();

  // Make the static files inside of the `public/` folder publicly accessible
  app.use(express.static('public'));
  ```

- Change the route for the homepage
  - Important: use an ABSOLUTE path

- Example:
  ```js
  app.get("/", function(req, res, next){    
      res.send(`<h1>This is the homepage</h1><img src="/images/home.jpg" />`);
  })
  ```



CSS:
- Create the directory "public/css"
- Create the file "public/css/main.css"
- Add some content
  - https://raw.githubusercontent.com/ironhack-demos/demo-express-iron-restaurant-w7d1/refs/heads/main/public/css/main.css
- Include it in our routes


Important:
- For images & css, use an `ABSOLUTE PATH` (we will save time tomorrow)


## Separate HTML

Intro (why is important):
- Code readability & syntax highlight
- Separation of concerns

Steps:
- Create the directory `/views`
- Create `home.html` and `contact.html`
- Modify the routes:

  ```js
  app.get("/", function (req, res, next) {
    res.sendFile(__dirname + "/views/home.html");
  })
  ```


## (extra) Add nav menu [10m]

note: css already includes some rules for our nav menu

```html
  <nav>
      <a href="/">Home</a>
      <a href="/contact">Contact</a>
  </nav>
```



## res.json

Intro:
- res.send()
- res.sendFile()
- res.json()


  ```js
    const pizzasArr = [
        {
          id: 1,
          title: 'Pizza Margarita',
          price: 12,
          imageFile: 'pizza-margarita.jpg',
        },
        {
          id: 2,
          title: "Veggie Pizza",
          price: 15,
          imageFile: "pizza-veggie.jpg"
        }, 
        {
          id: 3,
          title: "Seafood Pizza",
          price: 25,
          imageFile: "pizza-seafood.jpg"
        },
        {
          id: 4,
          title: "Hawaian",
          price: 20,
          imageFile: "pizza-hawaian.jpg"
        },
    ];
  ```

<!--
@LT: extract this to `data/pizzas.js`

Why:
- Same pattern as lab
- It will also help us when we explain req.params and query

-->




## Request Logging 

- npm install morgan

- Import morgan:
  ```js
  const logger = require('morgan');
  ```

- Configure express:
  ```js
  //...
  const app = express();

  // Setup the request logger to run on each request
  app.use(logger("dev"));
  ```


- See a demo (e.g. send a GET request for the homepage)
  - Explain: we send 1 initial request but the browser is sending more requests (css, images)

  <!-- @LT: can create a diagram on https://excalidraw.com -->



## Intro to Express Middleware 

see `Node - Custom Middleware.md`

<!-- @LT: for now, just do an intro to middleware + create a couple of custom middleware functions
-->



## JSON Middleware - express.json() [10m]

<!-- Important: instructions in lab "lab-express-basic-server" ask to configure json middleware -->

Configure Express to be able to read incoming HTTP request that contain JSON data in the body.


```js
  // JSON middleware to parse incoming HTTP requests that contain JSON
  app.use(express.json()); 
```

<!-- 
Express < 4.16: body-parser: 
https://medium.com/@mmajdanski/express-body-parser-and-why-may-not-need-it-335803cd048c
-->



## Create repo + upload to Github [10m]
  - Add `.gitignore`
  - Note: mention that if they clone, they'll need to do `npm install`

