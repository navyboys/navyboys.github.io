---
layout: "post"
title: "Atom as Markdown Editor"
date: "2016-01-20 12:34"
comments: true
categories: [tool, writing]
keywords: editor atom markdown
description:
---

**Markdown** is an easy-to-use markup language in a plain text format and it became my favorite writing format several years ago because it makes me stay focused on recording thoughts and ideas efficiently.

Up to now I’ve used dedicated Markdown editors like **MOU** and **Haroopad** as a tool of writing while they all have pros and cons individually. When Atom replaced Sublime Text as my code editor for web development, I tried to use it as a Markdown editor either and the result is amazing. Atom proves itself as a fantastic solution for writing in markdown and it can be customized to whatever you want to match your writing style.

Atom comes with full Markdown support including a robust previewer. It supports GitHub flavored Markdown and includes spell check along with predefined Markdown snippets.

Further more, we can easily extend Atom using the built-in package manager. Atom has a bunch of packages that can be installed to provide additional productivity. Here are some ones I am using:

### language-gfm

**language-gfm** is an Atom built-in package which adds syntax highlighting and snippets to GitHub flavored Markdown files in Atom. I use it instead of **language-markdown** because the latter seems not working well with **markdown-preview-plus**.

### Markdown Preview Plus

**Markdown Preview Plus** is a package that provides a real-time preview of markdown documents with `ctrl-shift-m`. I choose this instead of Atom built-in **Markdown Preview** because it also provide Math (LaTeX) support to the markdown preview with `ctrl-shift-x`.

![markdown-preview-plus](https://i.github-camo.com/11195c1f0294de243f68409abd79a91452323cb6/68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f47616c616469726974682f6d61726b646f776e2d707265766965772d706c75732f6d61737465722f696d67732f6d70702d66756c6c2d7265732d696e766572742e706e67)

### markdown-scroll-sync

This package is used to synchronize scrolling between markdown file and its preview.

![markdown-scroll-sync](https://i.github-camo.com/a0f171c5c0f3ca4403ae288ca45ee2035906c184/68747470733a2f2f636c6f75642e67697468756275736572636f6e74656e742e636f6d2f6173736574732f3831313435352f31313331373235392f63356239623063322d386664632d313165352d386638352d6237646565666235323563352e676966)

### Markdown-Writer

**Markdown Writer** adds tons of features to make Atom an even better Markdown editor and works great with static blogging engines such as Octopress as well.

![Markdown-Writer](https://i.github-camo.com/216ebba971ab38d17d6eabdaf236d042a55b35b8/687474703a2f2f692e696d6775722e636f6d2f7339656b4d6e732e676966)

Here are some shortcuts I use often during writing with Markdown-Writer in Atom.

Task | Keystrokes
--|--
`code` | `cmd-'`
**bold** | `cmd-b`
_italic_ | `cmd-i`
~~strike through~~ | `cmd-h`
`'''code block'''` | `shift-cmd-"`
`<kbd>key</kbd>` | `cmd-k`
Unordered List | `shift-cmd-u`
Ordered List | `shift-cmd-O`
Task List | `markdown-writer:toggle-task`
Blockquote | `shift-cmd->`
Insert link | `shift-cmd-k`
Insert image | `shift-cmd-i`
Insert table | `markdown-writer:insert-table`
Toggle headings | `ctrl-alt-1`

### References

- [Best Markdown Editors for OS X](https://www.raywenderlich.com/119949/top-five-markdown-editors)
- [Make Your Perfect Markdown Editor with Atom Editor Plugins](http://tedcurran.net/2015/05/12/make-your-perfect-markdown-editor-with-atom-editor-plugins/)
- [Atom.io for Markdown editing](https://blogs.msdn.microsoft.com/silverlining/2015/05/18/atom-io-for-markdown-editing/)
