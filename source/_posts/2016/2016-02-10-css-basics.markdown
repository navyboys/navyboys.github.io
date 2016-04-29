---
layout: post
title: "CSS Basics"
date: 2016-02-10 06:28
comments: true
categories: [css, codecademy, note, web development]
keywords: css codecademy web
description: Notes for Codecademy course - HTML & CSS
---

Here is the notes I've taken while reading CSS part of Codecademy's web fundamentals course: HTML & CSS. It is not clear enough compared with _CSS Glossary_, that is also summarized by Codecademy and can be treated as a fantastic CSS cheat sheet.

## Concepts

CSS, which stands for **Cascading Style Sheets**, is a language used to describe the appearance and formatting of your HTML.

- A **style sheet** is a file that describes how an HTML file should look.
- We say these style sheets are **cascading** because the sheets can apply formatting when more than one style applies.

## Why separate form from function?

You can apply the same formatting **to several HTML elements** without rewriting code over and over.
You can apply similar appearance and formatting **to several HTML pages** from a single CSS file

## Three Ways to Insert CSS

inline styling

``` html
<p style="color:red">Red font!</p>
```

in the `<head>`

``` html
<html>
  <head>
    <style>
      p {
        color: purple;
        }
	  </style>
  </head>
  <body>
  </body>
</html>
```

in separate file

``` html
<html>
  <head>
    <link type="text/css" rel="stylesheet" href="stylesheet.css"/>
  </head>
  <body>
  </body>
</html>
```

## One selector, many properties

You can set many properties for one selector.

``` css
p {
  font-family: Arial;
  color: blue;
  font-size: 24px;
}
```

## Comments

The stuff inside the `/*` `*/` marks are CSS comments.

``` css
/* I'm a comment! */
```

## Color

CSS understand millions of colors in the form of **hexadecimal values**.

``` css
h1 {
  color: #8B1C69;
}
```

- Hexadecimal counting is **base-16**. Each digit can be the numbers 0 through 9 or the letters **a** through **f**!
- Hex values are **case-insensitive**: that is, they don't care about capitalization. `#FFC125` and `#ffc125` are the same color.

## Pixels and ems

A **pixel** is a dot on your computer screen. Specifying font sizes in pixels is great when you want the user to see exactly on their screen what you designed on yours, though it assumes your screens are of similar size.
The font-size unit **em** is a relative measure: one `em` is equal to the default font size on whatever screen the user is using. That makes it great for smartphone screens, since it doesn't try to tell the smartphone exactly how big to make a font: it just says, "Hey, `1em` is the font size that you normally use, so `2em` is twice as big and `0.5em` is half that size!"

``` css
p {
  font-size: 0.5em;
}
```

## Font

Most computers will understand popular fonts like `Verdana`, `Courier`, and `Garamond`, but each individual computer has different fonts installed on it. CSS has some **built-in** defaults meant to ensure your users see what you intend. They are:

- **serif**: A font with little decorative bits on the ends of the strokes that make up letters.
- **sans-serif**: A plain-looking font, like this one. It doesn't have the little doohickies on the ends of letters like a serif font does.
- **cursive**: A scripty font! It looks like cursive writing.

## Backup values

You can tell CSS to try several fonts, going from one to the next if the one you want isn't available.

``` css
p {
  font-family: Tahoma, Verdana, sans-serif;
}
```

## Bordering

The border property supports several values.

``` css
selector {
  border: 2px solid red;
}
```

## Links and text decoration

Links have a property, text-decoration, that you can change to give your links a little more custom flair.

``` css
a {
  color: #cc0000;
  text-decoration: none;
}
```

## Multiple Selectors

Select only the h3 header nested inside three `<div>`s

``` css
div div div h3 {
    color: red;
}
```

## Universal selector

One selector to rule them all

``` css
* {
    border: 2px solid black;
}
```

## Children

Grab direct children

``` css
div > p { /* Some CSS */ }
```

## Override

Certain selectors will _override_ others if they have a greater specificity value.

- `ul li p {` is more specific CSS than just `p {`, so when CSS sees tags that are both `<p>` tags and happen to be inside unordered lists, it will apply the more specific styling (`ul li p {`) to the text inside the lists.
- There are two selectors that are even more specific than nested selectors like the ones above: **classes** and **IDs**.

## Class

Classes are useful when you have a bunch of elements that should all receive the same styling

``` html
<!-- html -->
<div class="square"></div>
<img class="square"/>
<td class="square"></td>
```

``` css
/* css */
.square {
  height: 100px;
  width: 100px;
}
```

## ID

IDs are great for when you have exactly one element that should receive a certain kind of styling.

``` html
<!-- html -->
<div id="first"></div>
<div id="second"></div>
```

``` css
/* css */

#first {
  height: 50px;
}

#second {
  height: 100px;
}
```

## Pseudo-class

A **pseudo-class selector** is a way of accessing HTML items that aren't part of the document tree

Pseudo-class selectors let us style **changes** in our HTML document.

``` css
a:hover {
	color: #cc0000;
	text-decoration: none;
}
```

There are a number of useful pseudo-class selectors for links, including:

- `a:link`: An unvisited link.
- `a:visited`: A visited link.
- `a:hover`: A link you're hovering your mouse over.

`first-child` is used to apply styling to only the elements that are the first children of their parents.

``` css
p:first-child {
  color: red;
}
```

`Nth child` would turn every paragraph that is the second child of its parent element red.

``` css
p:nth-child(2) {
  color: red;
}

```

## Taking up space

4 possible values of **display** property:

1. **block**: This makes the element a block box. It won't let anything sit next to it on the page! It takes up the full width.
1. **inline-block**: This makes the element a block box, but will allow other elements to sit next to it on the same line.
1. **inline**: This makes the element sit on the same line as another element, but without formatting it like a block. It only takes up as much width as it needs.
1. **none**: This makes the element and its content disappear from the page entirely!

## Margins, Borders, and Padding

<img src="http://s3.amazonaws.com/codecademy-blog/assets/ae09140c.png"/>

#### Margin

``` css
div {
	margin: auto; /* centering it on the page */
}
```

``` css
div {
	margin: 1px 2px 3px 4px; /* top right bottom left */
}
```

#### Padding

``` css
div {
	padding: 10px; /* 10 pixels of padding on all sides */
}
```

#### Negative values

`margin-left: -20px` will move the element twenty pixels to the _left_.

## Floating

When you **float** an element on the page, you're telling the webpage: "I'm about to tell you where to put this element, but you have to _put it into the flow of other elements_."

#### Clearing elements

If you tell an element to `clear: left`, it will immediately move below any floating elements on the left side of the page; it can also clear elements on the `right`. If you tell it to `clear: both`, it will get out of the way of elements floating on the left and right!

## Absolute, Relative, and Fixed Positioning

If you don't specify an element's positioning type, it defaults to `static` and just plunks itself down in the document.

#### Absolute positioning

When an element is set to `position: absolute`, it's then positioned in relation to the first parent element it has that doesn't have `position: static`. If there's no such element, the element with `position: absolute` gets positioned relative to `<html>`.

#### Relative positioning

Relative tells the element to move relative to where it would have landed if it just had the default `static` positioning.

#### Fixed positioning

- `fixed` positioning anchors an element to the browser window—you can think of it as gluing the element to the screen. If you scroll up and down, the fixed element stays put even as other elements scroll past.
- You can think of the `z-index` as a measure of importance: the higher an element's `z-index`, the higher it will be "stacked" on the page. Giving your header a `z-index` of 1 while not giving any of the other elements a `z-index` ensures that your header will sit "on top of" your other elements and won't get stuck behind them.
