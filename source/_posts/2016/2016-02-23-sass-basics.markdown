---
layout: post
title: "Sass Basics"
date: 2016-02-23 13:20
comments: true
categories: [css, sass, note, web development]
keywords: css sass web
description: Notes for Sass Guide
---

Sass (stands for **S**yntactically **A**wesome **S**tyle **S**heets) is a powerful CSS extension language as well as preprocessor that can be a useful tool to make web developers efficient for writing CSS. Here is the note I was taking while reading a concise [guide](http://sass-lang.com/guide) to Sass from its official site.

## Syntax

There are two syntaxes available for Sass.

**SCSS** (Sassy CSS) is an extension of the syntax of CSS.

- Using `.scss` extension.
- Every valid CSS stylesheet is a valid SCSS file
- Enhanced with the Sass features
- Understands most CSS hacks and vendor-specific syntax

``` scss
$primary-color: #333;

body {
  color: $primary-color;
}
```

**Sass**, The older syntax, provides a more concise way of writing CSS.

- Using `.scss` extension.
- **Indentation** rather than `{}` to indicate nesting of selectors
- **Newlines** rather than `;` to separate properties

``` sass
$primary-color: #333

body
  color: $primary-color
```

Either syntax can **import** files written in the other.

Files can be automatically converted from one syntax to the other using the `sass-convert` command line tool:

``` bash
# Convert Sass to SCSS
$ sass-convert style.sass style.scss

# Convert SCSS to Sass
$ sass-convert style.scss style.sass
```

## Preprocessing

Sass take your preprocessed Sass file and save it as a normal CSS file that you can use in your web site.

``` bash
# run Sass from the command line
sass input.scss output.css

# watch the file, update the CSS every time the Sass file changes
sass --watch input.scss:output.css

# watch the entire directory with many Sass files
sass --watch app/sass:public/stylesheets
```

## Variables

You can store things like colors, font stacks, or any CSS value you think you'll want to reuse. Sass uses the `$` symbol to make something a variable.

`SCSS`

``` scss
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

`CSS`

``` css
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
```

## Nesting

Sass will let you nest your CSS selectors in a way that follows the same visual hierarchy of your HTML.

`SCSS`

``` scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }
}
```

`CSS`

``` css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}
```

## Partials & Import

Using partials is a great way to modularize your CSS and help keep things easier to maintain.

- Name partials with a leading underscore, like `_partial.scss`
- Sass partials are used with the `@import` directive.

`SCSS`

``` scss
// _reset.scss

html,
body,
ul,
ol {
   margin: 0;
  padding: 0;
}
```

``` scss
// base.scss

@import 'reset';

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
```

`CSS`

``` css
html, body, ul, ol {
  margin: 0;
  padding: 0;
}

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
```

## Mixins

A mixin lets you make groups of CSS declarations that you want to reuse throughout your site.

- Pass in values to make your mixin more flexible
- A good use of a mixin is for vendor prefixes

`SCSS`

``` scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

`CSS`

``` css
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

## Extend/Inheritance

Using `@extend` lets you share a set of CSS properties from one selector to another. It helps keep your Sass very **DRY**.

`SCSS`

``` scss
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}

.warning {
  @extend .message;
  border-color: yellow;
}
```

`CSS`

``` css
.message, .success, .error, .warning {
  border: 1px solid #cccccc;
  padding: 10px;
  color: #333;
}

.success {
  border-color: green;
}

.error {
  border-color: red;
}

.warning {
  border-color: yellow;
}
```

## Operators

Doing math in your CSS is very helpful. Sass has a handful of standard math operators like `+`, `-`, `*`, `/`, and `%`.

`SCSS`

``` scss
.container { width: 100%; }

article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
```

`CSS`

``` css
.container {
  width: 100%;
}

article[role="main"] {
  float: left;
  width: 62.5%;
}

aside[role="complementary"] {
  float: right;
  width: 31.25%;
}
```
