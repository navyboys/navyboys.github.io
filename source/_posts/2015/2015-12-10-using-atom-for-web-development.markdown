---
layout: post
title: Using Atom for Web Development
date: 2015-12-10 12:00
comments: true
categories: [tool, development]
keywords: editor atom
description:
---

As a programmer, I have tried a variety of different editors. Back to the days when I got my first job as a developer in NEC, I used **Hitemaru**, which once was a popular editor among Japanese programmers, to  write PL/SQL programs. That was the first time I met with text editors other than advanced but 'heavy' IDEs. In the following days, I tried **Notepad++**, **Vim** and settled down with **Sublime Text** when I began coding in Ruby a few years ago. But recently, I shifted to **Atom** without missing one single feature of the previous so far. I really love Atom for its zero-compromise combination of hackability and usability. Also, it's free and is in continuous development by the core team from Github.

Since Atom comes with a great set of defaults, *Following the Default is King* philosophy works very well with Atom. For example, support for multiple languages, linters, integration with the terminal, tree-view, and Git, etc. Furthermore, Atom provides an extensive level of customization via themes and packages. Just like Sublime Text, for a long time, text editors have been able to be tuned and tweaked, but Atom has taken it to a new level.

## Packages

For the purposes of web development, you will definitely need other packages. Here are some packages I have installed for Ruby on Rails development. (Some screenshots below are taken from the respective package pages and articles in the reference list.)

#### Linter

Linter is a base linter provider that allows consumers to visualize errors and other kind of messages easily.

![Linter](https://i.github-camo.com/70b6e697c9d793642414b4ea6d08dbb9678877b3/687474703a2f2f672e7265636f726469742e636f2f313352666d6972507a322e676966)

Here are some specific linters I used for Ruby on Rails development.

- linter-ruby
- linter-scss-lint
- linter-haml
- linter-rubocop
- linter-rails-best-practices

#### atom-beautify

This package makes messy code neater and more readable.

![Beautify](http://media02.hongkiat.com/useful-atom-packages/beautify.gif)

#### Emmet

Emmet is an essential tool for web developers which expand abbreviations by `Tab` key to allow you to work quickly when writing HTML, CSS, Sass / SCSS and LESS syntaxes.

![Emmet](http://media02.hongkiat.com/useful-atom-packages/emmet.gif)

#### Merge Conflicts

This package detects the conflict markers left by `git merge` and overlays a set of controls for resolving each and navigating among them. It makes handling conflicts much easier.

![Merge Conflicts](https://i.github-camo.com/44ff44f156f274b8799022e44bcacb804fadc08a/68747470733a2f2f7261772e6769746875622e636f6d2f736d61736877696c736f6e2f6d657267652d636f6e666c696374732f6d61737465722f646f63732f636f6e666c6963742d7265736f6c7574696f6e2e676966)

#### ruby-test

Using this package, you can run Ruby tests, Rspec examples and Cucumber features from Atom quickly and easily.

![ruby-test](https://i.github-camo.com/64f6412302e14f7a155a13eeb6ff315a07fe0360/687474703a2f2f636c2e6c792f696d6167652f3330306e32673130317a30792f727562792d74657374362e676966)

#### Color Picker

A neat color-related package which lets you pick colorsas easy as navigating a color picker. It can be done by pressing `CMD`+`SHIFT`+`C`.

![Color Picker](https://i.github-camo.com/467c72e686f00893c3d36bf46499e76c10f31787/68747470733a2f2f6769746875622e636f6d2f74686f6d61736c696e647374726f6d2f636f6c6f722d7069636b65722f7261772f6d61737465722f707265766965772e676966)

#### File Icons

File Icons assigns file extension icons and colours for improved visual grepping.

![File Icons](http://media02.hongkiat.com/useful-atom-packages/fileicons.jpg)

## Shortcuts

Keyboard shortcuts are the essential way to do things faster for a develeper working with Atom. Here are some shortcuts I use often during my development.

#### Key to the Keys

- `⌘` : Command key
- `⌃` : Control key
- `⌫` : Delete key
- `←` : Left arrow key
- `→` : Right arrow key
- `↑` : Up arrow key
- `↓` : Down arrow key
- `⌥` : Option or Alt key
- `↩` : Return or Enter key
- ``⇧`` : Shift key

#### General

Task | Keystrokes
------------ | -------------
Fuzzy Find Files | `⌘`-`t`
Open Command Palette | `⌘`-`⇧`-`p`
Open Configuration Editor | `⌘`-`,`
Toggle Full Screen | `⌃`-`⌘`-`f`
Toggle Tree View | `⌘`-`\`
Toggle Line Comments | `⌘`-`/`
Select Grammar | `⌃`-`⇧`-`L`
Increase Font Size | `⌘`-`+`
Decrease Font Size | `⌘`-`-`
Convert to Upper Case | `⌘`-`k`-`u`
Convert to Lower Case | `⌘`-`k`-`L`
Switch Tabs | `⌃`-`tab`

Switching tabs with `⌃`-`tab` is not a feature provided by Atom. You can get this Sublime Text-like behavior by adding the following to keymap:

```
'body':
  'ctrl-tab': 'pane:show-next-item'
```

#### Code Navigation & Management

Task | Keystrokes
------------ | -------------
Select Entire Word | `⌃`-`⇧`-`w`
Go to Line | `⌃`-`g`
Delete Line | `⌃`-`⇧`-`k`
Duplicate Line | `⌘`-`⇧`-`d`
Indent Selected Text | `⌘`-`]`
Outdent Selected Text | `⌘`-`[`
Move to Top of File | `⌘`-`↑`
Move to Bottom of File | `⌘`-`↓`
Move to First Character of Line | `⌘`-`←`
Move to Last Character of Line | `⌘`-`→`

#### Editor View Tasks

Task | Keystrokes
------------ | -------------
Split Panes Vertically | `⌘`-`k`-`↓`
Split Panes Horizontally | `⌘`-`k`-`→`
Vertical Navigation Panes | `⌘`-`k` `⌘`-`↓`
Horizontal Navigation Panes | `⌘`-`k` `⌘`-`→`

#### File Tasks

Task | Keystrokes
------------ | -------------
Open Tree View | `⌃`-`0`
Add a File | `a`
Move a File | `m`
Delete a File | `⌫`

#### Find & Replace

Task | Keystrokes
------------ | -------------
Find String in Current File | `⌘`-`f`
Find String in All Project Files | `⇧`-`⌘`-`f`
Find Next Matching String | `⌘`-`g`
Find Previous Matching String | `⇧`-`⌘`-`g`
Select Next Matching String | `⌘`-`d`
Select All Matching Strings | `⌃`-`⌘`-`g`
Replace String in Current File | `⌥`-`⌘`-`f`

### References

* [Atom: My New Favorite Code Editor](http://www.jonobacon.org/2015/11/16/atom-my-new-favorite-code-editor/)
* [10 Most Useful Atom Packages for Web Developers](http://www.hongkiat.com/blog/useful-atom-packages/)
* [Setting up Atom for Rails Development](http://www.developingandrails.com/2015/04/setting-up-atom-for-rails-development.html)
* [Atom Editor Keyboard Shortcut Cheat Sheet](http://sweetme.at/2014/03/10/atom-editor-cheat-sheet/)
* [Atom Editor Cheat Sheet](http://d2wy8f7a9ursnm.cloudfront.net/atom-editor-cheat-sheet.pdf)
