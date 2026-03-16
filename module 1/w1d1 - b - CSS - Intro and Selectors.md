

# CSS - Intro & Selectors

<!--- 


Codealong (continue):
- demo / final result: https://ironhack-rmt-WD-teaching-materials.github.io/html-css-intro-codealong/
- repo: https://github.com/ironhack-rmt-WD-teaching-materials/html-css-intro-codealong





Note, this selectors can be covered in w1d2:
- "selector list" (h1, h2)
- "descendant" (div p)
- "and" (h3.highlight)
- examples: https://github.com/ByteWarriors-Ironhack-Feb-23/feb23-html-intro/blob/main/css/main.css



-->


<!--

Feedback from students:
- Too much information for only one lesson (specially for those who didn't cover this in the prework).
- Make sure to start explaining why CSS + why selectors are useful +  clear examples

-->



## how to add css
  - inline: `style=""`
  - in the head tag: `<style>`
  - external file: `<link rel="stylesheet" href="style.css" />`


## Linking to resources

  <!-- @todo: create cheatsheet -->

    - External url:
      - href="https://mykittens.com/main.css"

    - Absolute path: 
      - href="C:\Luis\Ironhack\module1\html-intro\css\main.css" (avoid !!)
      - href="/css/main.css"

    - Relative path: 
      - href="./css/main.css" (current directory)
      - href="../css/main.css" (one directory above in the hierarchy)


- Example Filesystem diagram: 
  - https://tree.nathanfriend.io/?s=(%27options!(%27fancy!true~fullPath3~trailingSlash3~rootDot3)~4(%274%27Root0cs8reset.cs5css0image8background.jpg*player.png0j8data.j5js0index.html%27)~version!%271%27)*6270672%20%203!false4source!58main.6%5Cn27-%208s*%0187654320*



## Intro CSS Selectors (2 min.)
- what are they

- why they're useful + how typical CSS looks like +++
  - example of CSS project: https://codepen.io/celincky/pen/zdqso
  - why keeping CSS tidy is important

- selector & declaration block



## Selectors:

- type selector: div, p, h1...

- id: `id=""`
  - CONVENTION: underscore-with-dashes
  - Each page can have only one element with that ID
  - Each element can have only one ID

- class: `class=""`
    - CONVENTION: underscore-with-dashes (kebab-case)
    - Can assign more than one class to an element (but do not add multiple times the class attribute: class="" class="") 

- (skip) Universal selector
  - Warning: Be very careful when using the universal selector

- Combine selectors (only mention it, we will go in detail later)
  - example, descendant selector: `.course-summary img`



## Cascade, Specificity, Inheritance


<!--

Alternative: watch video together

- CSS Specificity explained - Kevin Powell (13min) (Cascade + Specificity)
https://www.youtube.com/watch?v=c0kfcP_nD9E

-->



• Cascade 
  • "the order of CSS rules matters; when two rules apply that have equal specificity, the one that comes last in the CSS is the one that will be used."


• Specificity (Selector precedence)
  • What it is: "some selectors have higher precedence"
  • How it is calculated: https://cms-assets.tutsplus.com/uploads/users/30/posts/34141/image/spec-02.svg
  • Cheatsheet: http://www.standardista.com/wp-content/uploads/2012/01/specificity3.pdf
  • Tip: VS Code displays specificity when you hover a css selector.


• (brief) Inheritance
  • Some CSS property values set on parent elements are inherited by their child elements (e.g. `font-family`)
  • Some aren't (e.g. `width`)
  • full list: https://stackoverflow.com/a/5612360/11298742


• (skip) Further reading:
  • https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance




Backup (Specifishity):
- ![specifishity cheatsheet](../media/images/specifishity.png)



<!-- @todo: create cheatsheet / gist -->



## (skip) Colors

  - GREAT VIDEO (4 minutes, explains color names, hex, rgb, rgba): https://www.youtube.com/watch?v=HxztHgRN8I4

  - Some options:
    - color: `color: orange;` (downside: we can not have words for every color in the world...)
    - RGB: `color: rgb(255, 0, 0);`
    - RGBA: `color: rgba(0, 255, 0, 0.5);`
    - RGB in Hexadecimal: `color: #ff0000;`




## (extra) CSS dinner Game

CSS dinner (https://flukeout.github.io/)
- do until level 14th.


