# Week 2
## Day 1

#### Intro to the web
- Internet vs Web
#### Intro to html
#### Intro to css
- display mode
  - inline
  - block
  - inline-block

## Day 2
#### Two blocks aside
- #### Vertical align
  - inline-block
    - vertical-align: top
    - so that the second blocks align the top of the first blocks
  - float
    - float: left
    - but we need to clear the float layout afterwards
    - container:
      - overflow: hidden
  - center the container
    - text-align: center or
    - margin: 0 auto;

#### Grid
```html
  <div class="span-3">span 3</div>
  <div class="span-2">span 2</div>
  <div class="span-1">span 1</div>
  <div class="span-1">span 1</div>
  <div class="span-1">span 1</div>
  <div class="span-1">span 1</div>
```

```css
.span-1, .span-2, .span-3 {
  margin-bottom: 5px;
  float: left;
  min-height: 100px;
  width: 100%
}

.span-1 {
  background-color: mistyrose;
  /*   width: 30%; 180 / 600 = 0.3
*/}
.span-2 {
  background-color: linen;
  /*   width: 63.333333333%;
  */
}

.span-3 {
  background-color: plum;
  /*   width: 96.666666666%; 500/600 = 0.96666
*/}

body {
  padding: 0;
}

img {
  width: 100%;
}

ul {
  list-style-type: none;
  padding-left: 0;

}


/***************************************/

/* if screen size is bigger than something */
@media (min-width: 50em) {
  body {
    width: 80%;
    margin: 0 auto;

  }

  .span-1, .span-2, .span-3 {
    width: 96.66666666%;
    margin-right: 3.3333333%


  }

  .span-1 {
    width: 30%;
  }
```

#### center text in the middle of the box

```css
  text-align: center;
  display: flex;
  justify-content: center;
  align-content: center;
  flex-direction: column;
```

## Day 3
#### regular expression
 - `/[^\w]|/g`  `^\w` -> not a word
- regexr.com

#### html & javascript
- advance positioning
- document object model (dom)
- finding/ searching/ quering objects
  - `document.getElementsByTagName("h1")`
- query selector
  - using css selector
  - `document.querySelector('h1')`
  - `document.querySelector(".ttile").textConetnt` gives you the text of the content
  - style
    - `document.querySelector(".title").style.backgroundColor = "blue"`
- query selector for objects
  - `document.querySelectorAll(".title")[0].style.backgroundColor = "blue"`
  - `document.querySelectorAll("input")[0].value` is the value of the text field
- event listener
```javascript
var btn = document.querySelector('button');
btn.addEventListener("click", function() {
  console.log('win')
})
```
