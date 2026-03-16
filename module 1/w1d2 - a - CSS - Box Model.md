

# CSS - Box Model



ALTERNATIVE: watch this video together

- Box Model In 8 Minutes (Web Dev Simplified) [8min.]
  https://www.youtube.com/watch?v=rIO5326FgPE



<!--- 

Status: complete

Notes:
- box model is also covered in the prework (some things like "box-sizing" are not)

-->


## Intro 


- Every HTML element is a rectangular box

- Box-Model: https://i.imgur.com/LF204FU.gif

- Dev Tools: show box model



## Codealong

Initial code: 
- https://codepen.io/luisjunco/pen/yLppaYV
  <!-- @LT: remember to fork -->

Possible final result:
- https://codepen.io/luisjunco/pen/wvRbLmx



## Border:


- Width, style, color:

    ```
    border-color: #17212e;
    border-style: solid;
    border-width: 1px;
    ```

- Shorthand:
    ```
    border: 1px solid #17212e;
    ```

- Spacing behavior: after adding the border, the element "uses" more space.

- Single borders

    ```
    border-bottom: 1px solid #17212e;
    ```


## Border-Radius

```
border-radius: 12px;
```


- Circle:

    ```
    .circular-div {
        background-color: #ccc;
        border-radius: 50%;
        height: 100px;
        width: 100px;
    }
    ```


- Circle for images that are not squares

    ```css
    .img-wrapper {
        width: 200px;
        height: 200px;
        border-radius: 50%;
        overflow: hidden;
        margin: 0 auto;
    }


    img {
        max-height: 100%;

        /* examples of relative units */
        /* max-width: 10%; */
        /* max-width: 5rem; */
        /* max-width: 100vw; */
    }
    ```



## Padding

> Padding creates extra space within an element.

- Padding = space between the content and the border of an element

    ```
    padding: 10px;
    ```

- Other examples:

    ```
    padding: 10px 20px 30px 40px;
    ```

- Cheatsheet for shorthand: https://archive.smashing.media/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/0eb754a6-893b-4a48-b8d4-b9b2db0ee650/figurea.gif

- Spacing behavior: after adding padding, the element "uses" more space.


- Units:
  - Absolute (px)
  - Relative (%, em, vw....)
    - %: Relative to the parent element
    - em: Relative to the font-size of the element (2em means 2 times the size of the current font)
    - rem: Relative to font-size of the root element
    - vw/vh: Relative to 1% of the width/height of the viewport


- Possible values (4, 3, 2, 1):
  - https://learnwebcode.com/images/lessons/css-shorthand-1.gif
  - https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/0eb754a6-893b-4a48-b8d4-b9b2db0ee650/figurea.gif



## Box-sizing Property

- By default: when we add border/padding, the element "uses" more space.

- Sometimes, we have to fit the elements in a design.

- example:

    ```
    box-sizing: border-box;
    ```

- possible values:

  - content-box: default value. Width and height are calculated taking into account only the content (but not the padding and border).
  - border-box: width and height include the content, the padding and the border.




## Margin

- space between the border of an element and the other elements around it.

    ```
    margin: 10px 10px 10px 10px;
    ```


## Exercise

Student Portal > Time to practice:
> Lorem Ipsum is a website where you can generate random content [...]




## Extra

Peter griffin:
- https://c.tenor.com/QWdPngpHxZ8AAAAd/family-guy-css.gif




