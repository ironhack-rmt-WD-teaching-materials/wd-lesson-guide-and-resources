

# Mongoose and Express - Create - Read documents

<!--

Status: complete.

Slides: "m2w3d3 - Mongoose-and-Express - Basic CRUD"


Methodology:
- do a codealong for all READ + CREATE on books
- before each step, analyze with students what we are trying to do and how to solve it


Codealong Final Result (README.md includes all the steps):
- https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong

-->


## Intro

- CRUD

- Since today we're just applying existing concepts, some students find it relatively easy + some other students very difficult


- Basic slides: 
  - https://docs.google.com/presentation/d/1YRtTti-K2v4_ZigCC60-pvx4XvbpPhoRH1lAjNXbnRg/edit?usp=sharing



## READ: list of books

- Intro: ask students, how we can implement it.


- route: GET `/books`
- DB query: Book.find
- view: `books/books-list.hbs`


  <!--

  @LT:
  - provide code for the view
  - example: https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong/blob/29c1ef3bf7bcadb272c95ba644d4695d2ea68b5a/views/books/books-list.hbs

  -->


- Remember:
  - place the res.render() method inside the .then()

- Explain Error Handling

    ```js
    .catch( (error) => {
          console.log("Error getting list of books from DB", error);
          next(error);
      });
    ```


## READ: book details page

<!--
How: 
  1. think & plan with students
  2. give time to solve individually (15min)
  3. Finally, solve together.
-->


Practice: add functionality to display book details (book details page)


1. Create a new route: GET `/books/:bookId`
2. In that route:
  - get book id from req.params (e.g. `req.params.bookId`)
  - DB query: Book.findById
  - render a view: `books/book-details.hbs`
3. Modify the view were we render the list of books (`books/books-list.hbs`), so that we provide a link to see the details of a book.

Recommendation:
- test in small steps
- example 1: when you create the route, you can start with `res.send("this is my new route")` and test if it works.
- example 2: when you add the query to the DB, you can do console.log() with the book details.


Time: 15min.



(Super Bonus) Functionality to filter books by min rating
- Modify route `/books`
- Use query string + method .filter()
- Provide a form so that users can search




## CREATE: create new book

Render Form:
- route: GET `/books/create`
- view: `books/book-create`


Example view file (with form): https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong/blob/main/views/books/book-create.hbs



Process Form:
- route: POST `/books/create`
- DB query: Book.create()
- view: we will not create a view. Instead, once book is created, Redirect: `res.redirect('/books')`


Example code: https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong/commit/ae585b4caaf252489fb8cf542cc2e3ee392ae868#diff-4ca9a80832fef4cd47b8081486835d02a7e17e0c0cbdbf7c12a3d6933a986466


