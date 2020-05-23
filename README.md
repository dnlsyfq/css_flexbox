There are two important components to a flexbox layout: 

***flex containers** : 
* flex container is an element on a page that contains flex items.
* to designate an element as a flex container, set the element’s display property to flex or inline-flex 
* Once an item is a flex container, there are several properties we can use to specify how its children behave.
* Child elements of flex containers will change size and location in response to the size and position of their parent container.

Any element can be a flex container. Flex containers are helpful tools for creating websites that respond to changes in screen sizes. Child elements of flex containers will change size and location in response to the size and position of their parent container.




* flex items : All direct child elements of a flex container are flex items. 


**display:flex**
For an element to become a flex container, its display property must be set to flex


```
# e.g.  all divs with the class container are flex containers. If they have children, the children are flex items

div.container {
  display: flex;
}
```

**display:infline-flex**


```
<div class="container" id="flex">
    <div class="box">
      <h2>1</h2>
    </div>
    <div class="box">
      <h2>2</h2>
    </div>
</div>

  .container {
    width: 150px;
    border: 1px solid grey;
    display:inline-flex;
  }
```

**display:justify-content**
specify how flex items spread out from left to right, along the main axis.

* flex-start — all items will be positioned in order starting, from the left of the parent container, with no extra space between or before them.
* flex-end — all items will be positioned in order, with the last item starting on the right side of the parent container, with no extra space between or after them.
* center — all items will be positioned in order, in the center of the parent container with no extra space before, between, or after them.
* space-around — items will be positioned with equal space before and after each item, resulting in double the space between elements.
* space-between — items will be positioned with equal space between them, but no extra space before the first or after the last elements.


```
.container {
  display: flex;
  justify-content: flex-end;
}

```

**align-items**
to align flex items vertically within the container.
to behave along the cross axis of the parent container.

* flex-start — all elements will be positioned at the top of the parent container.
* flex-end — all elements will be positioned at the bottom of the parent container.
* center — the center of all elements will be positioned halfway between the top and bottom of the parent container.
* baseline — the bottom of the content of all items will be aligned with each other.
* stretch — if possible, the items will stretch from top to bottom of the container (this is the default value; elements with a specified height will not stretch; elements with a minimum height or no height specified will stretch).

```
.container {
  align-items: baseline;
}
```

**flex-grow**
to specify if items should grow to fill a container and also which items should grow proportionally more or less than others.
```
<div class="container">
  <div class="side">
    <h1>I’m on the side of the flex container!</h1>
  </div>
  <div class="center">
    <h1>I'm in the center of the flex container!</h1>
  </div>
  <div class=”side”>
    <h1>I'm on the other side of the flex container!</h1>
  </div>
</div>


.container {
  display: flex;
}

.side {
  width: 100px;
  flex-grow: 1;
}

.center {
  width: 100px;
  flex-grow: 2;
}
```

**flex-shrink**
used to specify which elements will shrink and in what proportions
```
<div class="container">
  <div class="side">
    <h1>I'm on the side of the flex container!</h1>
  </div>
  <div class="center">
    <h1>I'm in the center of the flex container!</h1>
  </div>
  <div class="side">
    <h1>I'm on the other side of the flex container!</h1>
  </div>
</div>

.container {
  display: flex;
}

.side {
  width: 100px;
  flex-shrink: 1;
}

.center {
  width: 100px;
  flex-shrink: 2;
}
```

**flex-basis**
Another way of specifying the width of a flex item is with the flex-basis property. flex-basis allows us to specify the width of an item before it stretches or shrinks

```
<div class="container">
  <div class=”side”>
    <h1>Left side!</h1>
  </div>
  <div class="center">
    <h1>Center!</h1>
  </div>
  <div class="side">
    <h1>Right side!</h1>
  </div>
</div>

.container {
  display: flex;
}

.side {
  flex-grow: 1;
  flex-basis: 100px;
}

.center {
  flex-grow: 2;
  flex-basis: 150px;
}
```

**flex**
flex property allows you to declare flex-grow, flex-shrink, and flex-basis all in one line.

> Note: The flex property is different from the flex value used for the display property.

```.big {
  flex-grow: 2;
  flex-shrink: 1;
  flex-basis: 150px;
}

.small {
  flex-grow: 1;
  flex-shrink: 2;
  flex-basis: 100px;
}

// to 

.big {
  flex: 2 1 150px;
}

.small {
  flex: 1 2 100px;
}
```

**flex-wrap**
 flex items to move to the next line when necessary. This can be declared with the flex-wrap property.

* wrap — child elements of a flex container that don’t fit into a row will move down to the next line
* wrap-reverse — the same functionality as wrap, but the order of rows within a flex container is reversed (for example, in a 2-row flexbox, the first row from a wrap container will become the second in wrap-reverse and the second row from the wrap container will become the first in wrap-reverse)
* nowrap — prevents items from wrapping; this is the default value and is only necessary to override a wrap value set by a different CSS rule.

```
<div class="container">
  <div class="item">
    <h1>We're going to wrap!</h1>
  </div>
  <div class="item">
    <h1>We're going to wrap!</h1>
  </div>
  <div class="item">
    <h1>We're going to wrap!</h1>
  </div>
</div>

.container {
  display: inline-flex;
  flex-wrap: wrap;
  width: 250px;
}

.item {
  width: 100px;
  height: 100px;
}
```

**align-content**
use align-content to space the rows from top to bottom

*   flex-start — all rows of elements will be positioned at the top of the parent container with no extra space between.
*   flex-end — all rows of elements will be positioned at the bottom of the parent container with no extra space between.
*   center — all rows of elements will be positioned at the center of the parent element with no extra space between.
*   space-between — all rows of elements will be spaced evenly from the top to the bottom of the container with no space above the first or below the last.
*   space-around — all rows of elements will be spaced evenly from the top to the bottom of the container with the same amount of space at the top and bottom and between each element.
*   stretch — if a minimum height or no height is specified, the rows of elements will stretch to fill the parent container from top to bottom (default value).

```
<div class="container">
  <div class=”child”>
    <h1>1</h1>
  </div>
  <div class="child">
    <h1>2</h1>
  </div>
  <div class="child">
    <h1>3</h1>
  </div>
  <div class="child">
    <h1>4</h1>
  </div>
</div>

.container {
  display: flex;
  width: 400px;
  height: 400px;
  flex-wrap: wrap;
  align-content: space-around;
}

.child {
  width: 150px;
  height: 150px;
}
```

**flex-direction**
flex containers have two axes: a major axis and a cross axis. By default, the major axis is horizontal and the cross axis is vertical.

The major axis is used to position flex items with the following properties:

* justify-content
* flex-wrap
* flex-grow
* flex-shrink

The cross axis is used to position flex items with the following properties:

* align-items
* align-content

The major axis and cross axis are interchangeable. We can switch them using the flex-direction property. If we add the flex-direction property and give it a value of column, the flex items will be ordered vertically, not horizontally.


```
<div class="container">
  <div class="item">
    <h1>1</h1>
  </div>
  <div class="item">
    <h1>2</h1>
  </div>
  <div class="item">
    <h1>3</h1>
  </div>
  <div class="item">
    <h1>4</h1>
  </div>
  <div class="item">
    <h1>5</h1>
  </div>
</div>

.container {
  display: flex;
  flex-direction: column;
  width: 1000px;
}
.item {
  height: 100px;
  width: 100px;
}
```

The flex-direction property can accept four values:

*   row — elements will be positioned from left to right across the parent element starting from the top left corner (default).
*   row-reverse — elements will be positioned from right to left across the parent element starting from the top right corner.
*   column — elements will be positioned from top to bottom of the parent element starting from the top left corner.
*   column-reverse — elements will be positioned from the bottom to the top of the parent element starting from the bottom left corner.


**flex-flow**
used to declare both the flex-wrap and flex-direction properties in one line

> Note: The flex-flow property is declared on flex containers.
```
.container {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
}

//to 

.container {
  display: flex;
  flex-flow: column wrap;
}
```

**Nested Flexboxes**
It is also possible to position flex containers inside of one another
```
<div class="container">
  <div class="left">
    <img class="small" src="#"/>
    <img class="small" src="#"/>
    <img class="small" src="#" />
  </div>
  <div class="right">
    <img class="big" src="#" />
  </div>
</div>

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.left {
  display: inline-flex;
  flex: 2 1 200px;
  flex-direction: column;
}

.right {
  display: inline-flex;
  flex: 1 2 400px;
  align-items: center;
}

.small {
  height: 200px;
  width: auto;
}

.large {
  height: 600px; 
  width: auto;
}

```

```
display: flex changes an element to a block-level container with flex items inside of it.
display: inline-flex allows multiple flex containers to appear inline with each other.
justify-content is used to space items along the major axis.
align-items is used to space items along the cross axis.
flex-grow is used to specify how much space (and in what proportions) flex items absorb along the major axis.
flex-shrink is used to specify how much flex items shrink and in what proportions along the major axis.
flex-basis is used to specify the initial size of an element styled with flex-grow and/or flex-shrink.
flex is used to specify flex-grow, flex-shrink, and flex-basis in one declaration.
flex-wrap specifies that elements should shift along the cross axis if the flex container is not large enough.
align-content is used to space rows along the cross axis.
flex-direction is used to specify the major and cross axes.
flex-flow is used to specify flex-wrap and flex-direction in one declaration.
Flex containers can be nested inside of each other by declaring display: flex or display: inline-flex for children of flex containers.
```