---
layout: post
title: "Regex Basics"
date: 2016-03-10 15:48
comments: true
categories: [regex, development, note]
keywords: regex development regexone
description: Notes for RegexOne's Interactive Tutorial
---

Here is the notes taken for [RegexOne](http://regexone.com/)'s interactive tutorial which explores the more practical uses of regular expressions so that we can use them as quickly as possible.

## Cheat Sheet

Here is the summary of basic regex usages.

Regex|Meaning
-|-
`abc…`|Letters
`123…`|Digits
`\d`|Any Digit
`\D`|Any Non-digit character
`.`|Any Character
`\.`|Period
`[abc]`|Only a, b, or c
`[^abc]`|Not a, b, nor c
`[a-z]`|Characters a to z
`[0-9]`|Numbers 0 to 9
`\w`|Any Alphanumeric character
`\W`|Any Non-alphanumeric character
`{m}`|m Repetitions
`{m,n}`|m to n Repetitions
`*`|Zero or more repetitions
`+`|One or more repetitions
`?`|Optional character
`\s`|Any Whitespace
`\S`|Any Non-whitespace character
`^…$`|Starts and ends
`(…)`|Capture Group
`(a(bc))`|Capture Sub-group
`(.*)`|Capture all
`(abc|def)`|Matches abc or def

## Lesson 1: An Introduction, and the ABCs

**Everything is essentially a character**. We are writing patterns to match a specific sequence of characters (also known as a string).

**Pattern**: `abc`

``` ruby
Task 	Text 	 
match 	'abcdefg'
match 	'abcde'
match 	'abc'
```

## Lesson 1½: The 123s

**Pattern**: `123`

``` ruby
Task 	Text 	 
match 	'abc123xyz'
match 	'define "123"'
match 	'var g = 123;'
```

## Lesson 2: The Dot

**Pattern**: `...\.`

``` ruby
Task 	Text 	 
match 	'cat.'
match 	'896.'
match 	'?=+.'
skip 	'abc1'
```

## Lesson 3: Matching specific characters

**Pattern**: `[cmf]an`

``` ruby
Task	Text	 
match	'can'
match	'man'
match	'fan'
skip	'dan'
skip	'ran'
skip	'pan'
```

## Lesson 4: Excluding specific characters

**Pattern**: `[^b]og`

``` ruby
Task	Text	 
match	'hog'
match	'dog'
skip	'bog'
```

## Lesson 5: Character ranges

**Pattern**: `[A-C][n-p][a-c]`

``` ruby
Task	Text	 
match	'Ana'
match	'Bob'
match	'Cpc'
skip	'aax'
skip	'bby'
skip	'ccz'
```

## Lesson 6: Catching some zzz's

**Pattern**: `waz{2,4}up`

``` ruby
Task	Text	 
match	'wazzzzup'
match	'wazzzup'
skip	'wazup'
```

## Lesson 7: Mr. Kleene, Mr. Kleene

**Pattern**: `aa+b*c+` or `a{2,4}b{0,4}c{1,2}`

``` ruby
Task	Text	 
match	'aaaabcc'
match	'aabbbbc'
match	'aacc'
skip	'a'
```

## Lesson 8: Characters optional

Pattern: `\d+ files? found\?`

``` ruby
Task	Text	 
match	'1 file found?'
match	'2 files found?'
match	'24 files found?'
skip	'No files found.'
```

## Lesson 9: All this whitespace

**Pattern**: `\d\.\s+abc`

``` ruby
Task	Text	 
match	'1.  abc'
match	'2.	  abc'
match	'3.      abc'
skip	'4.abc'
```

## Lesson 10: Starting and ending

**Pattern**: `^Mission: successful$`

``` ruby
Task	Text	 
match	'Mission: successful'
skip	'Last Mission: unsuccessful'
skip	'Next Mission: successful upon capture of target'
```

## Lesson 11: Capturing groups

Regular expressions allow us to not just **match text** but also to **extract information** for further processing. This is done by defining **groups of characters** and capturing them using the special parentheses `(` and `)` metacharacters.

- `^(IMG\d+\.png)$`: capture and extract the full filename
- `^(IMG\d+)\.png$`: capture the part before the period

**Pattern**: `^(file.+)\.pdf$`

``` ruby
Task     Text                          Capture Groups	 
capture  'file_record_transcript.pdf'  'file_record_transcript'
capture  'file_07241999.pdf'           'file_07241999'
skip     'testfile_fake.pdf.tmp'
```

## Lesson 12: Nested groups

**Pattern**: `(\w+ (\d+))`

``` ruby
Task     Text        Capture Groups
capture  'Jan 1987'  'Jan 1987' '1987'
capture  'May 1969'  'May 1969' '1969'
capture  'Aug 2011'  'Aug 2011' '2011'
```

## Lesson 13: More group work

**Pattern**: `((\d+)x(\d+))`

``` ruby
Task     Text         Capture Groups
Capture  '1280x720'   '1280' '720'
Capture  '1920x1600'  '1920' '1600'
Capture  '1024x768'   '1024' '768'
```

## Lesson 14: It's all conditional

Writing patterns with many conditions can be hard to read, so you should consider making them separate patterns if they get too complex.

**Pattern**: `I love (cats|dogs)`

``` ruby
Task   Text	 
match	 'I love cats'
match	 'I love dogs'
skip	 'I love logs'
skip	 'I love cogs'
```

## Lesson 15: Other special characterss

**Boundary**

- `\b`: boundary between a word and a non-word character
- `\w+\b`: capturing entire words


**Back Referencing**

- `\0`: the full matched text
- `\1`: group 1
- `\2`: group 2

This is useful for example when you are in a text editor and doing a search and replace using regular expressions to swap two numbers, you can search for `(\d+)-(\d+)` and replace it with `\2-\1` to put the second captured number first, and the first captured number second for example.

Pattern: `.*`

``` ruby
Task   Text	 
match  'The quick brown fox jumped over the lazy dog.'
match  'There were 614 instances of students getting 90.0% or above.'
match  'The FCC had to censor the network for saying &$#*@!.'
```

## Problem 1: matching a decimal numbers

**Pattern**: `^-?\d+(,\d+)*(\.\d+(e\d+)?)?$`

Starts with an optional negative sign, one or more digits, optionally followed by a comma and more digits, followed by an optional fractional component which consists of a period, one or more digits, and another optional component, the exponent followed by more digits.

``` ruby
Task   Text 	 
match  '3.14529'
match  '-255.34'
match  '128'
match  '1.9e10'
match  '123,340.00'
skip   '720p'
```

## Problem 2: matching phone numbers

**Pattern**: `1?[\s-]?\(?(\d{3})\)?[\s-]?\d{3}[\s-]?\d{4}`

This breaks down into the country code `1?`, the captured area code `\(?(\d{3})\)?`, and the rest of the digits `\d{3}` and `\d{4}` respectively. We use `[\s-]?` to catch the space or dashes between each component.

``` ruby
Task     Text              Capture Groups
capture  '415-555-1234'    '415'
capture  '650-555-2345'    '650'
capture  '(416)555-3456'   '416'
capture  '202 555 4567'    '202'
capture  '4035555678'      '403'
capture  '1 416 555 9292'  '416'
```

## Problem 3: matching emails

**Pattern**: `^([\w\.]*)(\+\w*)?@\w+\.?\w+.\w+`

To extract the beginning of each email, we can use a simple expression `^([\w\.]*)` which will match emails starting with alphanumeric characters including the period. It will match up to the point in the text where it reaches an `@` or `+`.

``` ruby
Task     Text                                Capture Groups
capture  'tom@hogwarts.com'                  'tom'
capture  'tom.riddle@hogwarts.com'           'tom.riddle'
capture  'tom.riddle+regexone@hogwarts.com'  'tom.riddle'
capture  'tom@hogwarts.eu.com'               'tom'
capture  'potter@hogwarts.com'               'potter'
capture  'harry@hogwarts.com'                'harry'
capture  'hermione+regexone@hogwarts.com'    'hermione'
```

## Problem 4: matching HTML

**Pattern**: `<(\w+)`

- tag name: `<(\w+)`
- tag content: `>([\w\s]*)<`
- attribute values: `='([\w://.]*)`

``` ruby
Task     Text                                      Capture Groups
capture  "<a>This is a link</a>"                   "a"
capture  "<a href='http://regexone.com'>Link</a>"  "a"
capture  "<div class='test_style'>Test</div>"      "div"
capture  "<div>Hello <span>world</span></div>"     "div"
```

## Problem 5: matching specific filenames

Extract the filenames and extension types of **only image files** (not including temporary files for images currently being edited). Image files are defined as `.jpg`, `.png`, and `.gif`.

**Pattern**: `(\w+)\.(jpg|png|gif)$`

``` ruby
Task     Text                   Capture Groups 	 
skip     '.bash_profile'
skip     'workspace.doc'
capture  'img0912.jpg'          'img0912' 'jpg'
capture  'updated_img0912.png'  'updated_img0912' 'png'
skip     'documentation.html'
capture  'favicon.gif'          'favicon' 'gif'
skip     'img0912.jpg.tmp'
skip     'access.lock'
```

## Problem 6: Trimming whitespace from start and end of line

Write a simple regular expression to capture the content of each line, without the extra whitespace.

**Pattern**: `^\s*(.*)\s*$`

We can just skip all the starting and ending whitespace by not capturing it in a line.

``` ruby
Task     Text                            Capture Groups
capture  '  The quick brown fox... '     'The quick brown fox...'
capture  ' jumped over the lazy dog.  '  'jumped over the lazy dog.'
```

## Problem 7: Extracting information from a log file

Extract the **filename**, **method name** and **line number** of line of the stack trace.

Pattern: `(\w+)\(([\w\.]+):(\d+)\)`

The first capture group is the method, followed by an escaped parenthesis, followed by the filename, a colon, and finally the line number.

``` ruby
Task    Text                                                        Capture Groups
skip    'W/dalvikvm( 1553): threadid=1: uncaught exception'
skip    'E/( 1553): FATAL EXCEPTION: main'
skip    'E/( 1553): java.lang.StringIndexOutOfBoundsException'
capture 'E/( 1553):   at widget.List.makeView(ListView.java:1727)'  'makeView' 'ListView.java' '1727'
capture 'E/( 1553):   at widget.List.fillDown(ListView.java:652)'   'fillDown' 'ListView.java' '652'
capture 'E/( 1553):   at widget.List.fillFrom(ListView.java:709)'   'fillFrom' 'ListView.java' '709'
```

## Problem 8: Parsing and extracting data from a URL

**URIs**, or _Uniform Resource Identifiers_, are a representation of a resource that is generally composed of a **scheme**, **host**, **port** (optional), and **resource path**, respectively highlighted below.

`http://regexone.com:80/page`

The scheme describes the protocol to communicate with, the host and port describe the source of the resource, and the full path describes the location at the source for the resource.

In the exercise below, try to extract the **protocol**, **host** and **port** of the all the resources listed.

**Pattern**: `^(\w+)://([\w\-\.]+):?(\d+)?`

- protocols: `(\w+)://`
- hosts: `://([\w\-\.]+)`
- ports: `(:(\d+))`

``` ruby
Task    Text                                                          Capture Groups
capture 'ftp://file_server.com:21/top_secret/life_changing_plans.pdf' 'ftp' 'file_server.com' '21'
capture 'http://regexone.com/lesson/introduction#section'             'http' 'regexone.com'
capture 'file://localhost:4040/zip_file'                              'file' 'localhost' '4040'
capture 'https://s3cur3-server.com:9999/'                             'https' 's3cur3-server.com' '9999'
capture 'market://search/angry%20birds'                               'market' 'search'
```
