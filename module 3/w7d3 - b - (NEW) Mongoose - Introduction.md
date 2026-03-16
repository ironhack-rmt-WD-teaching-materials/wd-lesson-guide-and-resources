

# Mongoose - Introduction


<!-- 

@LT: 

- Students are now quite familiar with Mongoose (did research in mini-project)

-->



## (optional) Ask students what do they know about Mongoose

Mini-project research includes:
- install mongoose
- create Schema + model
- connect to DB
- data types + validators
- Create + Read (integrated in the routes)



## (brief) Intro to Mongoose + ODMs (Object Document Mapper)

Diagram MERN (including Mongoose):
- https://user-images.githubusercontent.com/62245004/98396310-99937000-206e-11eb-9ad1-4799d58e8699.png




## (skip) MVC pattern
  - https://media.geeksforgeeks.org/wp-content/uploads/20210629165722/mvc.png
  - https://seguridad.cicese.mx/uploads/notautic/utic23-5a3c250c42cae.png


- Example (Student Portal: "Example of MVC Pattern"):

  ```js
    router.get('/product-list', (req, res) => {
      // this CONTROLLER is...
      Product.find() // ... asking for data from the Product MODEL and ...
        .then(productsFromDB => {
          const data = { productsFromDB };
          res.render('products/list', data); //  ... sending a VIEW to the client
        })
        .catch(error => console.log(error));
    });
  ```
  


## Intro to what we will build

Summary of functionality we'll implement:
- 2 models
    - Pizza
    - Cook
- CRUD Pizza
    - [ ] C
    - [ ] R
    - [ ] U
    - [ ] D
- Create Cook
- Relations + Populate





## Mongoose setup

`npm install mongoose`



## Create our first model

<!-- @LT: students have already created a schema in mini-project. Keep it brief. -->

### a) Create `/models/Pizza.model.js`
    - example: https://github.com/ironhack-sept2024-devstructors/express-iron-restaurant/blob/main/models/Pizza.model.js


### b) Data Types in Mongoose
  - String
  - Number
  - Boolean
  - Arrays:
    - e.g. array of strings: `ingredients: [String]`
  - ...
  - See Student Portal: "Supported data types in schemas"
  - Full list: https://mongoosejs.com/docs/schematypes.html


### c) Show both syntaxes for types

  ```js
  {
    title: String,

    title: {
        type: String
    }
  }
  ```


### d) Mongoose Validators (see Student Portal)

- `default`
    ```js
    isVeggie: {
        type: Boolean,
        default: false
    },
    ```

- `required`

    ```js
    title: {
        type: String,
        required: true,
    },
    ```

- `unique`

- Note: 
    - "The unique Option is Not a Validator. It's a convenient helper for building MongoDB unique indexes"
    - If you modify your model and add/remove `unique`, Mongoose will not take it into account.
    - Solution: drop your DB or re-index (https://github.com/Automattic/mongoose/issues/7396#issuecomment-452905218)


- `enum`

    ```js
        dough: {
            type: String,
            enum: ["classic", "extra thin", "with cheese", "with garlic"]
        }
    ```

    Example: "with chocolate"


- `min`, `max`


- Others (see Student Portal)
- minlength
- maxlength
- trim
- lowercase
- match
- validate (Custom validation)
- set (Custom setter)



## (skip) Create a file to practice Mongoose

- `mongoose-playground.js`

<!--

- Advantage: allows to test quickly through the CLI
- Disadvantage: students are now used to have mongoose methods in the routes.

One option is to create it but only with:
- mongoose.connect
- Model.create

-->




## Connect to DB

In App.js:

    ```js
    const mongoose = require('mongoose');

    // ...

    mongoose
        .connect("mongodb://127.0.0.1:27017/myDataBaseName")
        .then((response) => {
        console.log(`Connected! Database Name: "${response.connections[0].name}"`);
        })
        .catch((err) => console.error("Error connecting to Mongo", err));
    ```


## Implement an endpoint to CREATE

<!-- 

@LT: start with a simple hardcoded object:

    const newPizza = {
        title: "margarita",
        price: 12
    }

-->

- POST `/pizzas`
    - `Pizza.create()`
    - handle promises with `.then().catch()`
    - test with Postman
    - status: 201


Note: for error handling, use this pattern (and explain why):

    ```js
    .catch(error => {
        console.log("\n\n Error creating a new pizza in the DB... \n", error);
        res.status(500).json({ error: "Failed to create a new pizza" });
    })
    ```


## Practice: mongoose methods

Instructions: https://github.com/ironhack-rmt-WD-student-materials/exercise-mongoose-methods

Time: 20min.

<!--

Summary:
- iteration 1: implement GET /pizzas
- iteration 2: implement GET /pizzas/:pizzaId


@LT - IMPORTANT:

- This exercise uses a DB on MongoDB Atlas, so that students get some initial data.
- To test if the DB is up, connect on Compass ("mongodb+srv://bob:supersecretpassword@cluster0.tiknp.mongodb.net/ih-exercise-mongoose-methods")
- If the DB is down, students can connect to a local DB (e.g. "mongodb://127.0.0.1:27017/ih-exercise-mongoose-methods"), but they'll need to create some initial data.

@todo:
- create a cron job / monitor to keep the DB alive.

Note:

- Stackblitz currently doesn't support connections to MongoDB.

> Are MongoDB, Mongoose, Postgres or MySQL supported?
> Currently, direct TCP database connections are not supported. However, an API based database provider like Neon (a serverless Postgres DB, accessible via API calls) may provide an alternative approach.

- More info and alternatives:
  - https://github.com/stackblitz/webcontainer-core/issues/1106
  - https://github.com/stackblitz/webcontainer-core/issues/749

-->




## Implement the endpoints to READ


- GET `/pizzas`
    - Pizza.find()

- GET `/pizzas/:pizzaId`
    - get the id from "req.params"
    - Pizza.findById(pizzaId)



## Implement the endpoint to UPDATE

- PUT `/pizzas/:pizzaId`
    - Pizza.findByIdAndUpdate(pizzaId, newDetails, { new: true })

- (optional) Explain PUT vs. PATCH
    - PUT: Updates or replaces the entire resource.
    - PATCH: Partially updates a resource.



## Implement the endpoint to DELETE

- DELETE `/pizzas/:pizzaId`
    - Pizza.findByIdAndDelete(pizzaId)




## 2nd Model

- Add 2nd model: `Cook.model.js`
    - name
    - location
    - bio
    <!-- Example: https://github.com/ironhack-sept2024-devstructors/express-iron-restaurant/blob/main/models/Cook.model.js -->

- Implement the endpoint to Create (2nd model):
    - `POST /cooks`

- Creating Relationships Between Collections
    - Change pizza schema:
        ```js
            cook: {
                type: mongoose.Schema.Types.ObjectId,
                ref: "Cook"
            }
        ```
    - Test with postman: POST /pizzas

- Populate:
    - Test with postman: `GET /pizzas/:id`
    - Change endpoint:
        ```js
            Pizza.findById(pizzaId)
            .populate("cook")
        ```
    - Do the same for `GET /pizzas/`




## (skip) FAQs

Some things to mention / common questions:

- Default name for  collections:
  - "When we use the Cat model to interact with the database, it will only be interacting with a collection that shares a name with it. That collection is the cats collection."

  - Mongoose will add an "s" at the end of the 
    - Why does mongoose always add an s to the end of my collection name & how to choose different name:
      https://stackoverflow.com/a/10559895/11298742


- Mongoose 'static' methods vs. 'instance' methods
  - https://stackoverflow.com/questions/29664499/mongoose-static-methods-vs-instance-methods

  - "statics" are the methods defined on the Model. e.g. `Pizza.find()`
  - "instance" methods are defined on the document (instance). e.g. `myPizza.save()`




## Bonus

- Explore the concept of a "seed file"

  - Research: what is a database seed file, why is it useful?

  - Example of a seed file WITHOUT relationships (`then+catch`): https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/blob/main/bin/seeds-without-relationships.js

  - Example of a seed file WITH relationships (`async/await`): https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/blob/main/bin/seeds-with-relationships.js


