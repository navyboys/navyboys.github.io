---
layout: post
title: "CSS Glossary"
date: 2016-01-26 10:10
comments: true
categories: [css, codecademy, note, web development]
keywords: css codecademy web
description: CSS Glossary from Codecademy
---

The `markdown` version of Codecademy's [CSS Glossary](https://www.codecademy.com/articles/glossary-css).

## Comments

Comments in CSS are signified by a forward-slash and asterisk.

``` css
/* This is a single line comment */
```

``` css
/* This
is a multi-line
comment */
```

## Properties

Properties are defined within selectors by defining a property and a value. They are separated with a colon and delineated with a semi-colon.

``` css
h1 {
  color: blue;
}
```

Each CSS rule can have as many properties as you like. Each of them applies to the elements that the selector applies to.

``` css
h1 {
  font-size: 24px;
  font-weight: bold;
  border: 1px solid black;
  color: pink;
}
```

## Padding

The padding is the spacing between the content and the border (edge of the element.). We can adjust this value with CSS to move the border closer to or farther from the content. Here, the div with id 'box' will get 10px of padding all around it.

``` css
#box {
  padding: 10px;
}
```

## Margin

The margin is the space around the element. The larger the margin, the more space between our element and the elements around it. We can adjust the margin to move our HTML elements closer to or farther from each other. Here, the div with id 'box' will get 10px of margin above and below it, and 5px of margin to the left and right.

``` css
#box {
  margin: 10px 5px 10px 5px;
}
```

## font-family

The `font-family` property sets the font of an HTML element's text.

``` css
p {
  font-family: Arial, Helvetica, sans-serif;
}
```

## Selectors

Selectors are used in CSS to select the parts of the HTML that are being styled. You can use several different methods for selecting an element.

``` css
selector {
  rules;
  rules;
  rules;
}
```

#### Class name selectors

You can also select HTML elements by their Class name. Unlike ID selectors, Class selectors select all elements with a matching class.

``` css
a.link {
  font-size: 12px;
}
```

``` css
.jumbo {
  text-size: 1000px;
}
```

#### Element selectors

You are able to select HTML elements first by simply using the name of the element.

``` css
body {
  background-color: #333;
}
```

``` css
h1 {
  color: blue;
}
```

``` css
a {
  text-underline: none;
}
```

#### ID selectors

ID selectors are used to select only a single item on a page. Like the term ("identification") indicates, ID selectors will ONLY select the first element with a matching ID.

``` css
#thatThingINeededToStyle {
  color: blue;
  font-size: 24px;
}
```

``` css
a#codecademy {
  color: purple;
}
```

#### Attribute selectors

HTML elements are also able to be selected by their attributes.

``` css
a[href="http://codecademy.com"] {
  color: purple;
}
```

``` css
input[type="text"] {
  width: 100px;
}
```

``` css
input[required] {
  border: 1px red solid;
}
```

#### Child selectors

You can also use multiple selectors to get the exact elements you want, by using parental nesting. By using the "greater-than" symbol (>), you can select only the direct children of an element, going down only one level.

Example

``` css
ul > li { /* Child */
  display: inline-block
}

/* Selects only the first-level list items in all unordered lists in the HTML */
```

``` css
ul a { /* Descendant */
  text-underline: none;
}

/* Selects all anchors which have an unordered list in their ancestry */
```

``` css
ul + span { /* Next-sibling */
  display: inline;
}

/* Selects only spans that directly follow an unordered list */
```

``` css
a ~ h1 { /* Following-sibling */
  color: blue;
}

/* Selects all h1 elements that are in the general vicinity of an anchor */
```

[Read more](
https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_selectors)

#### Universal selector

The universal selector `*` may be used to select all the elements in a particular range. Be aware that the universal selector is the most performance taxing selector, and should be used sparingly.

``` css
* { /* Selects ALL HTML elements in the page */
  background-color: blue;
}
```

``` css
body * { /* Selects ALL descendants of the body */
  color: red;
}
```

``` css
div > * { /* Selects ALL first-level children of divs */
  color: red;
}
```

Read more
[[1]](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors)
[[2]](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/)
[[3]](http://dev.opera.com/articles/view/27-css-basics/#universal)

## Pseudo class selectors

Pseudo Selectors can be used to narrow down a selection with certain rules.

``` css
li:first-child {
  color: red;
}

/*
  This selects only <li> elements that have no elements before them
  <ul>
    <li>Selected; will be red</li>
    <li>Not selected</li>
    <li>Not selected</li>
  </ul>
*/
```

``` css
li:last-child {
  color: red;
}

/* This does the opposite; only the last <li> will be red. */
```

``` css
a:hover {
  text-decoration: underline;
}

/* Will underline all links when the user puts their mouse over them */
```

``` css
a:active {
  font-weight: bold;
}

/* Will make all links bold while the user is clicking on them. */
```

Read more
[[1]](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
[[2]](http://dev.opera.com/articles/view/27-css-basics/#pseudoclasses)
