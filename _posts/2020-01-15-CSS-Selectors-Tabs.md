---
layout: post
title: CSS, selectors, example with tabs
---

## CSS selectors

https://flukeout.github.io/?utm_source=lewagon.com


- `*` stands for everything
- by tag (`div`)
- by id (`#red`),
- by class (`.btn`)  or psuedo-class (`a:hover`)
- with both class `(".class1.class2")`
- mixed: `li` with `.class1` and `#red` with `("li.class1#red")`
- descendants: all `a`  inside `p` with 'space': `("p a")`
- everything inside an element, `(p *)`
- AND: with the comma ',' : all `p`   with class1 is `("p,.class 1")`,
- every adjacent sibling (first direct descendant of the type) with '+':  `(p + li)` 
- all direct childs with `("ul > li")`  returns all the `li`
- for nth child `("ul:nth-child(2)")` returns the second `li` child
- by attribute: `("p[color=blue]")` for  <p style="color:blue;">
- attribute ends with:  `a[href$=".pdf"]`
- attribute starts with: `a[href^="https"]`
- attribute contains `a[href*="oogle"]`

## Tabs


```css
/* the logic */
/* to not display all of the radio buttons = input */
input {display: none;} 


/* group the inputs: use the same name = 'radiobutton' */
/* select all the 'label' immediately after 'input' with 'input+label'
and create a row of labels with "display:inline-block" so that all
the labels will be aligned  */
input + label { display: inline-block;} 

/* select every element with class '.textbox' preceded by tag 'label'
and do not display it */
label ~.textbox {display: none; } 

/* #tab-1:check ~.tab.content-1  means select the elt with .content-1
/* immediately after #tab-1 with property checked */

/* display any class 'textbox' preceded by a label that is checked */

#tab-1:checked ~ .content-1,
#tab-2:checked ~ .content-2,
#tab-3:checked ~ .content-3 {
    display: block;
}

/* some styling */

/* select all labels immediately following an input with property checked */
input:checked + label { background-color: white;}

/* select all labels immediately following an input with property NOT checked */
input:not(:checked) + label { background-color: lightgrey; }

body {
    background: #eee;
    min-height: 100vh;
    box-sizing: border-box; /* pour que le padding et bordure n'augmentent plus la largeur */
    padding-top: 10vh;
    font-family: "HelveticaNeue-Light", "Helvetica Neue Light", "Helvetica Neue", Helvetica, Arial, "Lucida Grande",
    sans-serif;
    margin: 0 auto;
}

.container {
    display:flex;
    justify-content:center;
    min-width: 300px;
 }

label { 
    padding: 10px;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
    font-weight: bold;
    position:relative;
    top: -5px; /*   just for fun */
}

.textbox { 
    background-color: white;
    padding: 1rem;
    width: 60vw;
    min-width: 300px ;
}

```
    

```
<!-- create a container to center the .bar div -->
<div class="container">

    <!-- create a second div to isolate from the centering of a .container -->
    <div class="bar">
    
        <!-- start by default with label 1 -->
        <!-- group the checkoxes with same name -->
        <input type="radio" name="radiobutton" id="tab-1" checked />
        <label for="tab-1">Tab one</label>

        <input type="radio" name="radiobutton" id="tab-2" />
        <label for="tab-2">Tab two</label>

        <input type="radio" name="radiobutton" id="tab-3" />
        <label for="tab-3">Tab three</label>


        <!-- give all divs a .textbox to select them after a label -->
        <!--  give every div a unique .content-i for indivual display the matching textbox
        with   the checked input-i -->
        
        <div class="textbox content-1">
            1: Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptas, provident?
        </div>
        <div class="textbox content-2">
            2: Lorem ipsum dolor sit amet consectetur adipisicing elit. In, minus.
        </div>
        <div class="textbox content-3">
            3: Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium, cupiditate!
        </div>
        
    </div>
</div>

```
    
    
