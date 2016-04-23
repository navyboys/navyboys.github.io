---
layout: post
title: "HTML Glossary"
date: 2016-01-25 15:51
comments: true
categories: [html, codecademy, note, web development]
keywords: html codecademy web
description: HTML Glossary from Codecademy
---

[HTML Glossary](https://www.codecademy.com/articles/glossary-html) is a perfect introduction to HTML basics written by Codecademy team. Here is the version for `markdown` fans.

## Attributes

Introduce attributes like class, id and href.

##### `class`

HTML elements can have one or more classes, separated by spaces. You can style elements using CSS by selecting them with their classes.

``` html
<div class="big-box yellow-box">This is a big yellow box.</div>
```

##### `id`

An HTML element can have an `id` attribute to identify it. `id` elements should always be unique to that single element, and each element should never have more than one id.

``` html
<div id="my-box">This is my box! Put your text in some other box.</div>
```

##### `href`

Links tell the browser where to go using an `href` attribute, which stores a URL.

``` html
<a href="http://google.com">Google it!</a>
```

## Basic Formatting

You can easily format text to be bold, italic, or underlined using simple formatting tags.

``` html
This text is <b>bold</b>, <i>italicized</i>, and <u>underlined</u>.
```
- This text is <b>bold</b>, <i>italicized</i>, and <u>underlined</u>.

## Body

The `body` is the container for all of a page's content. Comes after the `<head>` tag, within the overall `<html>` tag.

``` html
<html>
  <head>
    <title>An example of the body tag</title>
  </head>
  <body>
    This is inside the body!
  </body>
</html>
```

Almost all content belongs inside the `body` tag. The main exceptions are `script` and `style` tags, as well as the page `title` tag. As you can see in this example, there is a heading, an image, and a link all inside the body tag. The `head` tag contains only external files and the page title.

``` html
<html>
  <head>
    <title>My homepage</title>
    <link rel="stylesheet" type="text/css" href="homepage.css" />
    <script type="text/javascript" src="homepage.js"></script>
  </head>
  <body>
    <h1>Hello, this is a picture of my cat!</h1>
    <img src="cat.jpg" />
    <a href="mailto:cat@codecademy.com">Email my cat</a>
  </body>
</html>
```

## Children

An element that is an immediate descendent of another element or nested within another element is called a child. These become useful when using CSS child selectors and psuedo-elements.

``` html
<ul id="parent">
  <li id="child">I'm a child of parent!</li>
</ul>
```

## Comments

HTML comments are sometimes used in code to explain parts of the markup. They are similar to comments in other languages. Users do not see comments in their browser.

``` html
<!-- This is an HTML comment! -->
```

## Div

A block level container (or 'division' of the web page) for content with no semantic meaning.

``` html
<div>This is a div element.</div>
```

## Head

Tag that surrounds important content that is invisible to the user, but is important to the browser. Elements within this tag contain metadata about the page and links to stylesheets, scripts, etc.

``` html
<html>
  <head>
  </head>
  <body>
  </body>
</html>
```

## Headings

Heading elements like `<h1>`, `<h2>`, `<h3>`, ... allow you to use six levels of document headings, ranging from largest to smallest, breaking up the document into logical sections. For example, the word 'Headings' above is wrapped in a `<h2>` tag.

``` html
<h1> This is a header! </h1>
```

## Horizontal rules

This tag creates a black line one pixel thick that runs the all the way across its container. It can be styled to look differently with CSS.

``` html
<hr>
```

## HTML

HTML stands for **Hyper Text Markup Language**. It is the language used to create all websites.

All HTML files live within an over-arching `html` tag. This is the basic tag that defines an html document.

``` html
<html>
  The rest of your web page goes in here!
</html>
```

## Hyperlinks

Hyperlinks (or just links) take the user to another webpage when they click on it. The most common attribute used with links is `href`, which tells the browser where the link goes.

``` html
The following text is <a href="http://google.com">goes to Google</a>
```
- The following text is <a href="http://google.com">goes to Google</a>.

## Images

The `img` tag embeds an image into your HTML. Always found with the `src` attribute, which tells the browser where to find the image. Note that the `<img/>` tag is self-closing, and you can reference either local

``` html
<img src='mylocalimage.jpg'/>
```

## Line breaks

This tag is used in a block of text to force a line break. This is to be used for things which are a single paragraph, but where this formatting is necessary such as _poems_ or _addresses_. To separate paragraphs, separate each paragraph into a separate element instead. The resulting element on a web page will look like:

``` html
<p> Add: Fleetwood, Surrey, BC <br/> Tel: (778) 219-2111 </p>
```
Add: Fleetwood, Surrey, BC <br/> Tel: (778) 219-2111

## Links

Link elements are used to connect your document to a related resource (very different from hyperlinks, which take you to another webpage when you click on them). Links appear only in the head section of a document so they do not alter the content, but only the presentation. Links are most commonly used to connect to a stylesheet, script, favicon, or alternate format of the page such as an RSS feed or PDF.

``` html
<link type="text/css" rel="stylesheet" href="styles.css" />
```

## Lists

HTML supports two kinds of lists: ordered lists and unordered lists. Within lists each individual list item has its own tag.

#### Unordered Lists

Unordered lists are just lists whose items are denoted with bullet points.

``` html
<h3>Shopping list</h3>
<ul>
  <li>Dish soap</li>
  <li>Kitty litter</li>
  <li>Tomato sauce</li>
</ul>
```

#### Ordered Lists

Ordered lists' items are denoted with numbers.

``` html
<ol>
  <h3>My numbered list</h3>
  <li>First item!</li>
  <li>Second item!</li>
  <li>Last item!</li>
</ol>
```

## Paragraphs

One of the most common tags in HTML - it denotes a paragraph of text. It often has other elements nested inside of it, such as `<img/>`, `<a>`, `<strong>` and `<em>`.

``` html
<p>This is paragraph text!</p>
```

## Semantic formatting

These tags are similar to the previously mentioned formatting tags which have fallen out of favor. The difference is that these tags have semantic value (meaning). `<em>` is used for something that you wish to emphasize and `<strong>` is used for something that is important. With both of these elements, you can convey the level of emphasis or importance with nesting. The more times that you nest the element within itself, the higher the magnitude of the text it contains.

``` html
<p><strong><strong>Warning:</strong>Acid can cause severe burns</strong></p>
```

- <p><strong><strong>Warning: </strong>Acid can cause severe burns</strong></p>

## Tables

An element for displaying information in rows and columns. Supports headers and footers for labeling columns. Divides information into rows (denoted by the `tr` tag) which contain cells (denoted by the `td` tag).

``` html
<table>
  <thead>
    <tr>
      <th>Item</th>
      <th>Price</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Banana</td>
      <td>$56.75</td>
    </tr>
    <tr>
      <td>Yogurt</td>
      <td>$12.99</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>Total</td>
      <td>$69.74</td>
    </tr>
  </tfoot>
</table>
```

<table>
  <thead>
    <tr>
      <th>Item</th>
      <th>Price</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Banana</td>
      <td>$56.75</td>
    </tr>
    <tr>
      <td>Yogurt</td>
      <td>$12.99</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>Total</td>
      <td>$69.74</td>
    </tr>
  </tfoot>
</table>

## Tags & Elements

Tags are basic labels that define and separate parts of your markup into elements. They are comprised of a keyword surrounded by angle brackets `<>`. Content goes between two tags and the closing one is prefixed with a slash (Note: there are some self-closing HTML tags, like image tags). Tags also have attributes, which are

``` html
<tag attribute='value'>content</tag>
```

## Title

This tag tells the browser what to display as the page title at the top and tells search engines what the title of your site is. It goes inside `<head>` tags. Try and make your page titles descriptive, but not overly verbose.

``` html
<title> HTML Glossary </title>
```
