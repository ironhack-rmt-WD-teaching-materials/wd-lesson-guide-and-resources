
# CSS - Bootstrap Docs

<!--
Status: ready

@todo:
- codealong design screenshots: make it generic (e.g. plain buttons) 
- record video + QA


-->


## Intro

- CSS frameworks
  - What they are (create UI)
  - Why they're useful +++++
    - Speed up develpment
  - Examples (Bootstrap, Bulma, TailwindCSS, Materialize CSS...)


- Examples: https://getbootstrap.com/docs/5.1/examples/
  - Album: https://getbootstrap.com/docs/5.1/examples/album/
  - Carousel: https://getbootstrap.com/docs/5.1/examples/carousel/
  - e-commerce checkout form: https://getbootstrap.com/docs/5.0/examples/checkout/
  - Dashboard: https://getbootstrap.com/docs/4.0/examples/dashboard/


- Bootstrap versions



## Initial Setup

<!--
@LT: 
- do this before we go through the documentation (so that we can do quick demos)
-->

- `mkdir bootstrap-demo`
- `cd bootstrap-demo`
- `touch index.html`
- `code .`
- create html structure: `!`



## Topics

<!-- aug. 2023: v.5.3.1  -->

Documentation

Initial setup (getting started / introduction)
- add link to css
- add link to js (but leave it commented)
- understand the source code:
  - open the files & see the code (classes + css)
  - shall we download the files ?
  - explain: CDN



Buttons
Layout
- Grid +++
  - Explain the concept of a grid system & why is important
    - Consistent design
    - Harmony
    - Efficiency (easier to design, easier to implement)
Content
- Tables
Forms
- Overview
Components
- Accordion
- Buttons +
- Card +
- Dropdown button +
- Spinner +



## Codealong / Demo

Create a basic layout (e.g. portfolio site / e-commerce / ...).


Mobile Design:
![mobile design](../media/images/bootstrap-sample-1-mobile.png)

Desktop:
![desktop design](../media/images/bootstrap-sample-2-desktop.png)



Repo: 
- Code: https://github.com/ironhack-rmt-WD-teaching-materials/bootstrap-codealong
- Demo: https://ironhack-rmt-WD-teaching-materials.github.io/bootstrap-codealong/

  <!-- @LT: deploy on another account -->


Initial setup:
<!-- @LT: follow this so that they have a .html file -->
- mkdir bootstrap-demo
- cd bootstrap-demo
- touch index.html
- code -r .
- right click on  "index.html" and choose open with live server
- create html structure with `!`



Steps:

- installation
- grid
- 3 cards
  - on each card: image, text, button
- header & title



(Bonus) Responsive nav/hamburger menu (will be helpful for your projects)
- https://getbootstrap.com/docs/5.0/components/navbar/
- (v.5.3) https://getbootstrap.com/docs/5.3/components/navbar/#nav


(Bonus) Quick demo on codealong project (library project)
- e.g. some css for list of books

  ```hbs
  <div class="container">
      <div class="row">
          {{#each books}}
          <div class="col-12 col-lg-4 text-center mt-4 mb-4">
              <section class="book-summary">

              </section>
          </div>
          {{/each}}
      </div>
  </div>
  ```


  ```css
  .book-summary {
      border: 1px solid #aaa;
      box-shadow: 2px 2px 2px #999;
      padding: 2rem;
  }
  ```


(Bonus) Emmet abbreviations:
- Emmet cheatsheet: https://docs.emmet.io/cheat-sheet/
- Emmet quickref: https://quickref.me/emmet


## (Bonus) How to customize Bootstrap 5

How to customize Bootstrap 5 (16min.):
https://www.youtube.com/watch?v=nCX3QVl_PiI

Topics covered:
- install bootstrap as an npm package
- scss
- compile scss (vs code extension `Live Sass Compiler`)
- override variables
- add custom variables


## (Bonus) Bootstrap vs. Tailwind CSS
- Bootstrap vs. Tailwind CSS (1min.)
  - https://www.youtube.com/shorts/CcWIj3oiX80

- Tailwind CSS is the worst… (Fireship, 4min.)
  - https://www.youtube.com/watch?v=lHZwlzOUOZ4
  - topics: why tailwind, challenges and some tips


## Final notes

- How CSS work:
  - we basically write html + add class names
  - the framework will do the css for us :)

- Advantages: 
  - UI Development speed

- Limitations:
  - Default components

- Disadvantages:
  - html code bloated with class names

- great option for project2 + project3
- do not change bootstrap code (override rules)

- Grid System
- CSS Reset & normalizing

