

# Mongoose and Express - Update - Delete documents

<!--

Codealong Final Result (README.md includes all the steps):
- https://github.com/ironhack-rmt-WD-student-materials/library-project-crud-codealong



How: SELF_GUIDED


@LT: 
- IMPORTANT (for tomorrow): implement U+D on our existing repo (15min.)

-->


## UPDATE: update book details

- What do we need? (discuss with students)

- We will need (discussion):
  - Link to "edit"
  - Display a form
    -- this form will need the current information for each book
  - Process form


Steps we will follow:

[ ] Step 1: add link to "Edit"

    /books/:bookId/edit

[ ] Step 2: display form to Edit
    - route (GET  /books/:bookId/edit)
      --> get the details of the book & pass them to the view
    - view

[ ] Step 3: process form
  -- route (POST  /books/:bookId/edit)
  -- redirect




Render Form to Edit:
- route: GET `/books/:bookId/edit`
- DB query: Book.findById
- view: `books/book-edit`
- add links to edit (e.g. in `books-list.hbs`)

Process Form:
- route: POST `/books/:bookId/edit`
- DB query: Book.findByIdAndUpdate
  `Book.findByIdAndUpdate(bookId, { title, description, author, rating }, { new: true }).then().catch()`
- view: we will not create a view. Instead, once book is created, Redirect:
  - res.redirect(`/books/${bookId}`); 
  - res.redirect(`/books/${updatedBook.id}`))




## DELETE: delete a book

Add button to delete:
- in books-list.hbs:

  ```
  <form action="/books/{{_id}}/delete" method="POST">
    <button>Delete</button>
  </form>
  ```

Process Form to DELETE:
- route: POST `/books/:bookId/delete`
- DB query: Book.findByIdAndRemove
- redirect: `res.redirect('/books')`

