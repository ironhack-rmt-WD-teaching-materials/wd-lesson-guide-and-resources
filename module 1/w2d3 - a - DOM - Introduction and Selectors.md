
# DOM - Introduction and Selectors


<!---

Status: ready

@todo: 
- steps to follow are in a repo (js file). Consider adding them to the readme, so that it can also be used as a cheatsheet / reference.
- move the exercises to separate gists.

--->





## Intro

- We can see an HTML document as a hierarchy of nodes (tree): https://i.imgur.com/m08deQC.png


- Document Object Model (DOM)
  - The DOM is a fully object-oriented representation of the web page, and it can be modified from JavaScript.


- Example: today's lab (IronContacts): 
  - https://camo.githubusercontent.com/8b42d24c2521fbf04e33b6fe4c207e9cc11b53490c7bbe6d266d5aa40fe2e227/68747470733a2f2f656475636174696f6e2d7465616d2d323032302e73332e65752d776573742d312e616d617a6f6e6177732e636f6d2f7765622d6465762f6c6162732f6c61622d646f6d2d69726f6e636f6e74616374732f30302d6c61622d646f6d2d69726f6e636f6e74616374732d696e74726f2e676966



- The Document object
  - Show the Document object in the dev tools:
    - Dev Tools > Console > Type 'document'
  - Documentation: https://developer.mozilla.org/en-US/docs/Web/API/Document
    - see some sample methods (e.g. getElementById)


- Quick Demo:
  - go to ironhack.com + open dev tools
  - add an id to the main title
  - in the console: `document.getElementById()` + `innerText`


- Good & Bad news:
  - Bad news: lots of topics
  - Good news:
    - don't need to memorize all (just be familiar)
    - m2: all this will be done by React




## Initial Setup for DOM Codealong


Initial Code:
- https://github.com/ironhack-rmt-WD-student-materials/dom-manipulation-practice
- Fork + clone + open in VS Code.



## Demo

Follow steps here:
- https://github.com/ironhack-rmt-WD-student-materials/dom-manipulation-practice/blob/codealong-solution/js/main.js
<!-- @LT: or, follow the code from prev cohort -->
<!-- @LT: open a live session on VS Code -->

Note:
- steps to follow are in the branch `codealong-solution`


<!-- 

@LT: 

to select elements of the dom, can do the following, 
- introduce getElementById()
- ask them to do some research (other options to get elements from the dom)
- explain querySelector() and querySelectorAll()
-->



## Cheatsheet (DOM manipulation)


DOM manipulation cheatsheet:
https://stackblitz.com/edit/js-tdylkw?file=index.js
<!-- @todo: convert to a gist -->



