
# Mongoose and Express - Documents Relationships


<!--


- STUDENTS PORTAL: this doc. is ready and marks the steps to follow (code in Student Portal)

- ALTERNATIVE: books-authors. See "./w5d2 - a - ALTERNATIVE Codealong.md"

 -->



## Intro

- (Optional) refresh lesson "Data Models"
  -- embedded documents 
  -- storing a reference
  

- CRUD app similar to a Blog (users can post comments)

- Goal of this lesson: learn and practice Document Relationships

- Example of a blog: https://joemcnally.com/blog/
  -- list of posts
  -- each post can have comments
  -- author page


- Users - Posts - Comments
  -- a user can publish multiple posts
  -- a post can have multiple comments




## Setup

    ```
    $ git clone https://github.com/ironhack-labs/lesson-crud-with-populate
    $ cd lesson-crud-with-populate
    $ npm install
    ```

    @Lead-Teacher: 
    - before cloning, FORK on class github account.
    - (students can fork as well)


## Understanding the Models & Relationships that we have

- Open Models & explain

  - User → Post (1-to-many)
  - Post → User (1-to-1)
  - Post → Comment (1-to-many)
  - Comment → User (1-to-1)

- Diagram: https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_06d18f6b2498cc26b04997f45666842e.png

- Other alternatives to this structure ?
  - sure (e.g. comments embedded inside the Post model)
  - we have this setup so that we can practice model relationships


## Seed the database

```
$ node bin/seeds.js
```

- See result in Compass
- Note: db name is defined in the variable MONGO_URI, when we do the connection (see db\index.js)


## Understanding the functionality already implemented

- Run the app: `nodemon server.js` 

- Functionality provided:
  - Users model:
    - it is possible to create user accounts
    - we can see the list of users in "/users"
  - Posts:
    - We can click on "Create a new post" (a form will be loaded)
    - (the functionality to process this form is not provided)

- Explain Routes already created


- Note: functionality to register etc. is not really functional (we will learn how to do it properly)



## Implement: functionality to create new post

- Route to process POST request
  - Post.create()
  - We also need to update the User model (add the new post to the array)
    -- (see Student Portal)


## Implement: functionality to display list of posts

- Route GET '/posts'
  - Post.find()

- View (posts/list.hbs)
  - Iteration 1: display only the title of each post
  - Iteration 2: we want to display also the user
    - console.log the variable we get from Mongoose (For the Author, we just have the ID)
    - Solution: .populate()



## Implement: single post (details page)

- (Optional) Ask students to implement it:
  - Route with populate
  - View (`details.hbs` already created, need to add the content)

- Route
  - we also need to `.populate('author')`


## (Check for understanding): functionality to display all posts of a user

- Add link at the end of `posts/details.hbs`

  ```
  <a href="/users/{{author._id}}/posts">See all {{author.username}}'s posts </a>
  ```

- Route:

    ```
    router.get('/users/:userId/posts', (req, res, next) => {
    // ... your code here
    });
    ```

- View




## (break)

- Next: we will implement functionality for comments
- They're also stored as an array of references



## Implement: functionality to Publish a New Comment

- Analyze with students: 
  -- how will the new comment be stored
  -- what we need to do ?


- Implement:
  - Update the View with the post details: `posts/details.hbs `
    -- add list of comments
    -- add form to create new comment

  - Route (POST `/posts/:postId/comment`)


- Code (slightly different than in Student Portal):
  https://github.com/Ironhack-Team-Triangle-July2021/lesson-crud-with-populate/commits/master
  (see commit 3ed7640 + fix in the next commit)



## Implement: functionality to display list of Comments for each post

- Code:
  https://github.com/Ironhack-Team-Triangle-July2021/lesson-crud-with-populate/commits/master
  (commit 72f5a33)

