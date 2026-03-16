
# Node - Form validation


<!--

Status: draft


Notes:
  - All these 4 validation examples are implemented in ironlauncher (`ironlauncher --auth`)
  - Show and explain the code on there 
    - (as long as students understand it, we don't need to type all that code, for project2 they can use ironlauncher)


Time: 1h max.

-->

## Intro (client vs. server validation etc)


Slides: 
- https://docs.google.com/presentation/d/1JIdfc4TjXbdK6gtUTFrjgZ24gQyTSSHy1YJsa-6k2us/edit?usp=sharing


<!--
@todo:
- improve slides
- make a table with the different options (client x2 + server)
-->


## 1. Make sure that users fill all the mandatory fields.

Intro:
- Add "required" to form fields
- Show how we can bypass client validation (e.g. dev tools)


```js
  if (!username || !email || !password) {
    res.render('auth/signup', { errorMessage: 'All fields are mandatory. Please provide your username, email and password.' });
    return;
  }
```

```js
  {{#if errorMessage}}
    <p class="error">{{errorMessage}}</p>
  {{/if}}
```



## 2. Make sure users fill in data in the valid format.

See Student Portal (very briefly)

<!--

Regex are sometimes not the best solution...

Ex. Search on google / stackoverflow:
- "get the current domain name with javascript"

-->


To catch errors:

  ```js
  if (error instanceof mongoose.Error.ValidationError) {
      res.status(500).render('auth/signup', { errorMessage: error.message });
  } else {
      next(error);
  }
  ```

<!-- IMPORTANT: remember to require mongoose  -->
<!-- IMPORTANT: remember to require mongoose  -->


## 3. Make sure data in the database is clean - no duplicates please!

See Student Portal (very briefly)


## 4. Make sure users use strong passwords.

See Student Portal (very briefly)


