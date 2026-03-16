
# React - Routing Introduction


<!-- 

React Router Version History (dates on the left):
- https://github.com/remix-run/react-router/releases

Latest cohorts:
- Dec. 2025: v.7.10 (all working well) 
- Mar. 2026: v.7.13.1 

-->



# Intro

- show examples on some react apps
  - https://brews-and-bites.netlify.app/
  - airbnb


# Cheatsheet

https://gist.github.com/luisjunco/cbd1fe157c7f2f2b6b4983adbea9ae1e



## (Demo/codealong) Initial Setup + Basic Routing


Notes: 
  - work on "popcorn-time"

Steps:
- install `react-router-dom`
- Render `<BrowserRouter>` in main.jsx
- Add routes

  ```jsx
    <Routes>
      <Route path="/" element={<h1>this is the HOME page</h1>} />
      <Route path="/about" element={<h1>this is the ABOUT page</h1>} />
      <Route path="/contact" element={<h1>this is the CONTACT page</h1>} />
    </Routes>
  ```

- Add nav menu

  ```jsx
    <nav>
      <NavLink to="/">Home</NavLink> |
      <NavLink to="/contact">Contact</NavLink> |
      <NavLink to="/about">About</NavLink> |
    </nav>
  ```



Notes: 
- Show how we can display the nav menu in all pages or only in the homepage




## Practice: React Router

Initial code: https://stackblitz.com/edit/vitejs-vite-zrnmm4?file=src%2FApp.jsx

Your task: 
- implement routing (the navbar should always be visible)

<!-- @LT: explain how to do npm install on Stackblitz -->

Bonus: add some nice CSS.

Solution: https://stackblitz.com/edit/vitejs-vite-blx7svux?file=src%2FApp.jsx

Time: 15min.

