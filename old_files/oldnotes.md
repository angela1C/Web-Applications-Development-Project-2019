
## Meta data

- define the language and the character encoding
- set the viewport

## Div and span elements

- html elements used with CSS
- these don't change the content in any way, unless css is used.

- div is a block element
- span is an inline element used to set a unique style to a single HTML element.

```css
div {
    border: 1px solid red;
    background-color:yellow;
    width:300px;
}

span {
    color:blue;
    text-decoration:underline;
}
```
- use with classes and ids.
- `.` for use with class
- `#` for use with id

```css
.blue{
    color:blue;
}
```

## Box-sizing
- [css box-sizing](https://www.w3schools.com/css/css3_box-sizing.asp)

With the box-sizing property, the padding and border are included in an elements total width and height.
This is used to keep boxes the same size when padding and borders are used.

When `box-sizing: border-box;` is used on an element, the padding and the border are included in the width and hegiht.




## CSS pseudo classes

- select which elements you want to change, append on the pseudo class.
Some common ones:
- `first-letter` to change what first letter looks like
- `first-line` to change what the first line looks like

Example:
`p:first-letter{
    color:blue;
    font-weight:bold;
    font-size: 16px;


}

## Background Images

- can use a background image that will be the second layer of the webpage.
- the first layer will be the background colour
- the content goes on top of the background image
- can decide if and how the image should repeat
- can repeat vertically, horizontally
- can set the background position such as center, center-top, right-top, left-center etc
- can set a background color

Example:
```html
div{
    height:350px;
    width:100%;
    background-image:url("images/mypic.png");
    backgound-repeat:no-repeat;
}
```

# Responsive Web Design
- see[w3schools](https://www.w3schools.com/html/html_responsive.asp).
Using HTML and CSS to automatically resize, hide, shrink or enlarge a website to make it look good on all devices.

- Add the following `<meta>` tag to all webpages to se the viewport of the pages. Gives the browser instructions on how to control the pages scale and dimensions.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- can make **images** responsive using the `width` or `max-width` properties with a percentage %.
- `width:100%;`
- `max-width`: 100%;`

- can show different images depending on the window size using the `picture` element.

```html
<picture>
  <source srcset="img_smallflower.jpg" media="(max-width: 600px)">
  <source srcset="img_flowers.jpg" media="(max-width: 1500px)">
  <source srcset="flowers.jpg">
  <img src="img_smallflower.jpg" alt="Flowers">
</picture>
```

- **Responsive text size** using `vw` units (Viewport width) to have the text size follow the size of the browser window.

```html
<h1 style="font-size:10vw">Hello World</h1>
```

## Media Queries

Media queries are used to define completely different styles for different browser sizes. Can have elements displayes horizontally on large screens and stacked vertically on small screens.

## Responsive Web Design frameworks

- can use a responsive style sheet like [W3.css](https://www.w3schools.com/w3css/default.asp)
- can use the Bootstrap framework

# Website Layout

[Website Layout](https://www.w3schools.com/css/css_website_layout.asp).
A website is often divided into headers, menus, content and a footer.

- header is usually located at the top of the website or just below the navigation menu
- header often contains a logo or website name
- a Navigation bar contains a list of links to help visitors navigate the website
- Layouts often depend on the target users.

    * 1-column layout often used for mobile phones
    * 2-columns for tablets and laptops
    * 3-columns only used for desktops

- unequal columns often used with main content in the biggest column
- side content often on smaller column often for alternative navigation or to specify information relative to the main content

- footer placed at bottom of page and often contains information like copyright and contact information.

- Responsive layout: used to change the layout between multiple columns and columns that vary depending on screen width

According to w3schools, **CSS Flexbox** is the more modern way of creating column layouts.
For Internet Explorer 10 and below which don't support flexbox, this layout version here using floats is used.
Internet Explorer 11 is commonly used now.


## NAV tags
See [nav tag](https://www.w3schools.com/tags/tag_nav.asp)

The `nav` tag defines a set of navigation links. Intended not for all links but for major block of navigation links. The default display property in CSS is `block` but can change this.

# Flex box

https://www.w3schools.com/css/css3_flexbox.asp

The Flexible Box Layout Module is used to design flexible responsive layout structures without using float or positioning and is supported in all modern browsers.

## Parent Element (Container)
- First need to define a flex container. The flex container becomes flexible by setting the `display` property to `flex`.
The CSS `display` property specifies the type of box used for an HTML element.

```html
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

```css
.flex-container{
    display:flex;
}
```
There are 6 main flex container properties.

- **`flex-direction`** to define the direction in which to stack the flex items. Specifies the direction of the flexible items within the container.
    * `column` value to stack items vertically from top to bottom
    * `column-reverse` value to stack vertically from bottom to top
    * `row` value to stack items horizontally from left to right
    * `row-reverse` to stack horizontally from right to left

-  **`flex-wrap`** to specify if a flex items should `wrap` (default) or not `nowrap`, or `wrap-reverse` when there is not enough room for them on the one flex line.
-  **`flex-flow`** is shorthand for setting both the `flex-direction` and `flex-wrap`
    * example `flex-flow: row-wrap;`

- **`justify-content`** to align the flex items. Horizontally aligns the flex items which the when the items do not use all the available space on the main axis.
    * `center` value to align at centre of the container    
    * `flex-start` aligns at the start od the container (default)
    * `flex-end` at end of the container
    * `space-around` value to display flex items with space before, between and after the lines
    * `space-between` displays flex items with space between the lines

- **`align-items`** property to align items vertically. Vertically aligns the flex items when the items do not use all available space on the cross-axis
    * `center` value to align flex items to centre of the container
    * `flex-start` value to align items at top of the container
    * `flex-end` to align items at the bottom 
    * `stretch` value to stretch the items to fill the container (default value)
    * `baseline` aligns the flex items such as their baselines aligns

- **`align-content`** to align the flex lines. Modifies the behaviour of the `flex-wrap` property.
    * `stretch` value to stretch the flex lines to take up the remaining space (default value)
    * `space-between` value displays flex items with equal space between them
    * `space-around` with space before, between and after them
    * `center` value to display flex lines in the middle of the container
    * `flex-start`  to display flex lines at the start of the container
    * `flex-end` to display at end of the container

**Perfect centering** of a flex item can be acheived by setting the `justify-content` and `align-items` properties to `center`.

## Child elements
The direct **child** elements of a flex container automatically become flex items.

## Flex item properties

- `order` specifies the order of the flex items relative to the rest of the flex items inside the same container.
- `flex-grow` to specify how much a flex item can grow relative to the other flex items
- `flex-shrink` how much a flex item will shrink relative to the other flex items
- `flex-basis` to set initial length of a flex item

The `flex` property is shorthand for `flex-grow`, `flex-shrink` and `flex-basis` properties.
Example `"flex: 0 0 200px"` make item not grow, not shrink and with initial length of 200 pixels.

- `align-self` property specifies the alignment for selected item within the flexible container
- `align-self` overrides default alignment set by the containers `align-items` property.


Can make a responsive image grid using flexbox.
Can make a responsive website using flexbox.


## Flexbox Properties

- `display` specifies the types of box used for an HTML element
- 


`flex:1;` give each item  an equal 

- [flexbox cheatsheet](https://jonibologna.com/content/images/flexboxsheet.pdf)

- [common flexbox patterns](https://tobiasahlin.com/blog/common-flexbox-patterns/)


## colour combinations

https://visme.co/blog/website-color-schemes/

[colour picker](https://www.w3schools.com/colors/colors_picker.asp)


## form input and validation in html5

https://www.the-art-of-web.com/html/html5-form-validation/


## Navigation bar using flexbox

[flexbox-navbar](https://freshman.tech/flexbox-navbar/)

https://freshman.tech/feature-list/

## d3 remove previous chart
//remove the previous chart before a new one is drawn
    d3.select("#myDiv").selectAll("*").remove();

# D3 notes

- [D3-js selections](https://www.tutorialspoint.com/d3js/d3js_selections.htm)
Selections is one of the core concepts in D3.js. Based on CSS selectors (han HTML element tag, Class name or ID of an HTML element), it allows element(s) to be selected on a webpage. It can be used to modify, append or remove elements in relation to the pre-defined dataset and allows data visualisations to be created. 

- `select` only one DOM element matching the given CSS selector (first)
- `selectAll` to select all DOM elements matching the given CSS selector.

The D3 selection allows new elements to be appended into existing HTML documents using the `append()` and `text()` methods.
- The `append()` method appends a new element as the last child of the element in the current selectin and can also modify the style of the elments, their attributes, properties, HTML and text content.
- The `text()` method sets the content of the selected / appended elements.

D3 uses a **chain** syntax. Several actions can be performed in one line of code by chaining methods together with periods `.`.

- The `html()` method sets the html contents of the selected / appended elements.
- The `.attr()` method to add or update the attribute of the selected elements.
- The `.style()` method to set the style properties of the selected elements.
- The `classed()` method to set the `class` attribute of an HTML element. (See tutorial for adding, removing, checking or toggling classes.). Toggle class is used to flip a class to the opposite state, remove it 


## Creating SVGs with D3

- create a container to hold the svg in the html document. ( a div element with an Id.)
- select the SVG container with the `select()` method and insert the SVG element into it using the `append()` method.
- Attributes are added using the `.attr()` method and styles added using `style()` method.

- **Data join** 

- maps elements of an existing document with a data set
- `.enter()` method access the data which is not mapped to an existing element
- `.append()` method to create a new element from the corresponding data
- `.exit()` method processes data items removed dynamically
- `.remove()` method
Data join enables us to inject, modify and remove elements (HTML element as well as embedded SVG elements) based on the data set in the existing HTML document. By default, each data item in the data set corresponds to an element (graphical) in the document.

As the data set changes, the corresponding element can also be manipulated easily. Data join creates a close relationship between our data and graphical elements of the document. Data join makes manipulation of the elements based on the data set a very simple and easy process.


- `.insert` is similar to `.append` but it allows an element to be specified which the new element is attached to.

- `.remove` removes all the elements in a selection

- `.each` allows a function to be called on each element of a selection
- `.call` allows a function to be called on the selection itself.

With ` .each`, D3 passes in the joined data (d) and the index (i). 
As well as enabling eusable components, `.each` also allows computations to be shared across calls to .style, .attr etc.

- `?` and ':` in javascript as the conditional operator.
-`?:` is the ternary operator
- condition ? value-if-true : value-if-false
- `?` is like then, `:` is like else
-       .style('fill', odd ? 'orange' : '#ddd')


- `.filter` to filter a selection. A function is usually passed into `.filter` which returns true if the element should be included. `.filter` returns the filtered selection.

```javascript
d3.selectAll('circle')
  .filter(function(d, i) {
    return i % 2 === 0;
  })
  .style('fill', 'orange');
```

## SVG Transformation

see [tutorialspoint d3](https://www.tutorialspoint.com/d3js/d3js_svg_transformation.htm)

SVG provides options to transform a single SVG shape element or group of SVG elements. The `transform` attribute is used to support transformation and can be one or more of the following values.

- `translate` takes two options. 
        * `tx` for the translation along the x-axis
        * `ty` for the translation along the y-axis.
        * example `translate(20 20)`

- `rotate` takes three options
        * `angle` for rotation angle
        * `cx` and `cy` for the centre of the rotation in the x and y-axis. If not provided, defaults to current origin.

- `scale` with two options, `sx` for scaling along x-axis and `sy` for scaling along the y-axis where `sy` is optional and takes the value of `sx` if not specified.

- `skew` (`skewx `and `skewy`) takes a skew angle along the x or y-axis.

More than one transformation can be applied to a single SVG element. Separated by space.
    - example `transform = "translate(60 60) rotate(45)"




Rotate − It takes three options, angle refers rotation angle, cx and cy refers to the center of the rotation in the x and y axis. If cx and cy are not specified, then it defaults to the current origin of the coordinate system. For Example − rotate(60).

Scale − It takes two options, sx refers to the scaling factor along the x-axis and sy refers to the scaling factor along the y-axis. Here, sy is optional and it takes the value of sx, if it is not specified. For Example − scale(10).

Skew (SkewX and SkewY) − It takes a single option; the skew-angle refers to the angle along the x-axis for SkewX and the angle along the y-axis for SkewY. For Example − skewx(20).


## Transitions

D3 supports animation through transitions which are a limited form of Key frame Animation with only two key frames, `start` and `end` where the starting frame is usually the DOM's current state and the ending key frame depends on the styles, attributes and properties applied.
Transition is the process of changing from one state to another of an item. 
- `transition()` method is available for all selectors and starts the transition process. 
- supports most D3 selection methods such as `.attr()` and `.style()`.
- `.append()` and `.data()` method must be called before the transition.
- `.duration()` and `.ease()` are specific methods for the transition.
- supports animation through transition

- `duration()` method allows property changes to occur smoothly over a specified duration rather than instantaneously. 
- `delay()` method allows a transition to happen after a specified period of time.
- `.ease()` method to control timings

A Transition has 4 phases in it's lifecycle.  
1. The transition is scheduled (ie when it is created)
2. the transition starts (without any delay specified it starts immediately)
3. The transition runs (with values of transition between 0 and 1)
4. the transition ends (ending time is always 1)


## D3 Charts

- Bar chart using `rect` svg elements for the bars and `text` svg elements for the data values.
- can add style to the `rect` elements such as `fill`
- can add styles to `text` element such as `fill` for colour, `font` for font style and size,  `text-anchor` for positioning the text in the bars.

- width of the SVG
- `scaleFactor` to scale to a pixel value  to make it visible on the screen
- `barHeight` for the static height of the bars

Create an SVG element in the document and build the bar chart inside the SVG element. Set the width and height of the SVG



## python web server
python -m http.server