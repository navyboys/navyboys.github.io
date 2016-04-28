---
layout: post
title: "HTML Basics"
date: 2016-02-02 14:33
comments: true
categories: [html, codecademy, note, web development]
keywords: html codecademy web
description: Notes for Codecademy's course - HTML & CSS
---

I have got a habit of taking notes while reading technical stuff - books, blogs or even online courses. It really helps me to recall the concepts and points through notes written in `Markdown`, providing a deeper understanding of the topic.

`Codecademy` uses a step by step learning methodology to help beginners learn web fundamentals through coding practice. Here is the notes of the HTML part of its courses: HTML & CSS, which I'd like to treat it as a cheat sheet and help me recall the basics of HTML within minutes.

## Concepts

Some concepts and terminologies about HTML.

- **HTML** stands for **HyperText Markup Language**
- **Hypertext** means "text with links in it."
- A **markup language** is a programming language used to make text do more than just sit on a page: it can turn text into images, links, tables, lists, and much more.
- Things inside `<>`s are called **Tags**. Tags nearly always come in pairs: an opening tag and a closing tag.

## Skeleton of the page

Basic structure(skeleton) of a web page.

- Always put `<!DOCTYPE html>` on the first line. This tells the browser what language it's reading (in this case, HTML).
- Always put `<html>` on the next line. This starts the HTML document.
- Always put `</html>` on the last line. This ends the HTML document.
- There are always two parts to an HTML file: the **head** and the **body**.
- The **head** contains information about your HTML file, like its title. The title is what we see in the browser's title bar or page tab.
- The **body** is where you put your content, such as text, images, and links.

## Heading

HTML defines six levels of headings.

``` html
<h1>The CEO</h1>
<h2>VP</h2>
<h3>Director</h3>
<h4>Middle management</h4>
<h5>Lowly assistant</h5>
<h6>Gets coffee for everyone</h6>
```

## Image & Link

`HTML`

``` html
<a href="http://www.codecademy.com/">
  <img src="https://www.google.ca/images/nav_logo242.png"/>
</a>
```

`Result`

<a href="http://www.codecademy.com/">
  <img src="http://webstir.org/icons/code-cademy-icon.png"/>
</a>

## Ordered List

`HTML`

``` html
<ol>
  <li>Raindrops on roses</li>
  <li>Whiskers on kittens</li>
</ol>
```

`Result`

<ol>
  <li>Raindrops on roses</li>
  <li>Whiskers on kittens</li>
</ol>

## Unordered List

`HTML`

``` html
<ul>
  <li>Cheese</li>
  <li>Sour Cream</li>
</ul>
```

`Result`

<ul>
  <li>Cheese</li>
  <li>Sour Cream</li>
</ul>

## Comment

`HTML`

``` html
<!-- This is an example of a comment! -->
```

## Font Size

`HTML`

``` html
<p style="font-size: 0.5em">font-size</p>
```

`Result`

<p style="font-size: 0.5em">font-size</p>

## Font Color

`HTML`

``` html
<p style="color: green; font-size: 16px">Green</p>
```

`Result`

<p style="color: green; font-size: 16px">Green</p>

## Font Family

`HTML`

``` html
<h6 style="font-family: Arial">Title</h6>
```

`Result`

<h6 style="font-family: Arial">Title</h6>

## Background Color

`HTML`

``` html
<p style="background-color: red">Hello!</p>
```

`Result`

<p style="background-color: red">Hello!</p>

## Align

`HTML`

``` html
<h6 style="text-align: center">Center Heading</h6>
```

`Result`

<h6 style="text-align: center">Center Heading</h6>

## Strong Word

`HTML`

``` html
<strong>BOLD</strong>
```

`Results`

<strong>BOLD</strong>

## Emphasize Word

`HTML`

``` html
<em>Italicize</em>
```

`Result`

<em>Italicize</em>

## Table

`HTML`

``` html
<table>
  <thead>
    <tr>
      <th colspan="2">Famous Monsters</th>
    </tr>
    <tr>
      <th>Famous Monster</th>
      <th>Birth Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>King Kong</td>
      <td>1933</td>     
    </tr>
    <tr>
      <td>Dracula</td>
      <td>1897</td>     
    </tr>
  </tbody>
</table>
```

`Result`

<table>
  <thead>
    <tr>
      <th colspan="2">Famous Monsters</th>
    </tr>
    <tr>
      <th>Famous Monster</th>
      <th>Birth Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>King Kong</td>
      <td>1933</td>     
    </tr>
    <tr>
      <td>Dracula</td>
      <td>1897</td>     
    </tr>
  </tbody>
</table>

## Div

`HTML`

``` html
<div style="width:50px; height:50px; background-color:red"></div>
```

`Result`

<p></p>
<div style="width:50px; height:50px; background-color:red"></div>

## Span

`HTML`

``` html
<p>Black, except for the word <span style="color: red">red</span>!</p>
```

`Result`

<p>Black, except for the word <span style="color: red">red</span>!</p>
