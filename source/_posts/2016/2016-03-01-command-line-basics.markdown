---
layout: post
title: "Command Line Basics"
date: 2016-03-01 06:15
comments: true
categories: [command, codecademy, system, note]
keywords: command system codecademy
description: Notes for Codecademy's Command Line course
---

Here is the notes I've taken while reading Codecademy's course: [Learn the Command Line](https://codecademy.com/learn/learn-the-command-line) and Launch School's open book: [Introduction to the Command Line](https://launchschool.com/books/command_line).

The command line is a text interface for your computer. It's a program that takes in commands, which it passes on to the computer's operating system to run.

From the command line, you can navigate through files and folders on your computer, just as you would with Windows Explorer on Windows or Finder on Mac OS. The difference is that the command line is fully text-based.

<br>

# Lists

## Common Commands

The following is a list of some of the most common commands used on the command line.

Command	| Description
- | -
`cd` | Change directory.
`ls` | List files and directories in current directory.
`pwd` | Display the path of the current directory.
`touch` | Create a file.
`mkdir` | Create a directory.
`rm` | Remove a file or directory. Warning: deleting a file or directory with this command is permanent!
`cp` | Copy a file or directory.
`mv` | Move or rename a file or directory.
`echo` | Print text to STDOUT.
`cat` | Display contents of a file.
`more` | Display contents of a file, starting at the top and letting the user scroll down.
`less` | Display contents of a file in an even more interactive way.
`head` | Display the first part of a file.
`tail` | Display the last part of a file.
`man` | Display documentation about a command.

## Symbols

Some of the symbols that will help us navigate the command line:

Symbol | Meaning
- | -
`/` | The root directory or a separator when listing directories
`.` | The current directory (also `./`) or the same level
`..` | The directory one level up (also `../`)
`../..` | Two levels up
`~` | Your home directory, or the directory you are placed in when you log in.
`*` | The splat or glob operator. This is the wildcard of the command line and represents "any characters."

<br>

# Concepts

**Executables**

- A command is just a file. `ls`, `mkdir`, and `cd` are all files.
- Files that can be used as commands are called **executables**.

**What makes an executable different from other files?**

- They have **special characters** at the **beginning** to tell the computer how to execute them.
- They have **scripts** or **machine language** as their content.
- They have the executable **permission**.

  To run an executable, you just type its path as the first part of your input, then type in your arguments, and hit enter, like this:

  ``` bash
  $ /bin/echo "Hello World"
  Hello World
  ```

<br>

# Navigation

Get up and running with the command line by navigating directories and files.

## `pwd`

`pwd`: **print working directory**

``` bash
$ pwd
/home/ccuser/workspace/blog
```

## `ls`

`ls` **lists** all files and directories in the working directory

``` bash
$ ls
2014  2015  hardware.txt
```

`ls -a` lists **all** contents in the working directory, including _hidden files_ and _directories_

``` bash
$ ls -a
.  ..  .preferences  action  drama comedy  genres.xt
```

`ls -l` lists all contents of a directory in **long** format. [Here](https://www.codecademy.com/en/courses/learn-the-command-line/lessons/manipulation/exercises/ls-revisited) is what each column means.

1. Access rights. These are actions that are permitted on a file or directory.
1. Number of hard links. This number counts the number of child directories and files. This number includes the parent directory link (..) and current directory link (.).
1. The username of the file's owner. Here the username is `cc`.
1. The name of the group that owns the file. Here the group name is `eng`.
1. The size of the file in bytes.
1. The date & time that the file was last modified.
1. The name of the file or directory.

``` bash
$ ls -l
drwxr-xr-x 5  cc  eng  4096 Jun 24 16:51  action
drwxr-xr-x 4  cc  eng  4096 Jun 24 16:51  comedy
drwxr-xr-x 6  cc  eng  4096 Jun 24 16:51  drama
-rw-r--r-- 1  cc  eng     0 Jun 24 16:51  genres.txt
```

`ls -t` orders files and directories by the time they were last modified.

``` bash
$ ls -t
```

Multiple options can be used together.

``` bash
$ ls -alt
```

## `cd`

`cd`: **change directory**, takes a directory name as an argument, and switches into that directory.

``` bash
$ cd Desktop/
```

To navigate directly to a directory, use `cd` with the directory's path as an argument. Here, `cd jan/memory/` command navigates directly to the `jan/memory` directory.

``` bash
$ cd jan/memory
```

To move up one directory, use `cd ..`. Here, `cd ..` navigates up from `jan/memory/` to `jan/`.

``` bash
$ cd ..
```

## `mkdir`

`mkdir`: **make directory**, takes in a directory name as an argument, and then creates a new directory in the current working directory. Here we used `mkdir` to create a new directory named `media/`.

``` bash
$ mkdir media
```

## `touch`

`touch` **creates a new file** inside the working directory. It takes in a file name as an argument, and then creates a new empty file in the current working directory. Here we used `touch` to create a new file named `keyboard.txt` inside the current working directory.

If the file exists, `touch` is used to update the modification time of the file

``` bash
$ touch data.txt
```

<br>

# Manipulation

We can also use the command line to **copy**, **move**, and **remove** files and directories.

## `cp`

`cp` **copies** files or directories. Here, we copy the file `lincoln.txt` and place it in the `historical/` directory.

``` bash
$ cp lincoln.txt historical/
```

The wildcard `*` selects in the working directory, so here we use `cp` to copy all files into the `satire/` directory.

``` bash
$ cp * satire/
```

`m*.txt` selects all files in the working directory starting with **m** and ending with **.txt**, and copies them to `scifi/`.

``` bash
$ cp m*.txt scifi/
```

## `mv`

To **move** a file into a directory, use `mv` with the source file as the first argument and the destination directory as the second argument. Here we move `superman.txt` into `superhero/`.

``` bash
$ mv superman.txt superhero/
```

Move **multiple** files into a directory.

``` bash
$ mv wonderwoman.txt batman.txt superhero/
```

**Rename** the file `batman.txt` to `spiderman.txt`.

``` bash
$ mv batman.txt spiderman.txt
```

## `rm`

`rm` deletes files. Here we **remove** the file `waterboy.txt` from the file system.

``` bash
$ rm waterboy.txt
```

`rm -r` deletes a **directory** and all of its child directories.

``` bash
$ rm -r comedy
```
<br>

# Redirection

Learn to redirect input and output to and from files and programs.

- **Standard Input**, abbreviated as `stdin`, is information inputted into the terminal through the keyboard or input device.
- **Standard Output**, abbreviated as `stdout`, is the information outputted after a process is run.
- **Standard Error**, abbreviated as `stderr`, is an error message outputted by a failed process.

## `echo`

The `echo` command accepts the string "Hello" as standard input, and **echoes** the string "Hello" back to the terminal as standard output.

``` bash
$ echo "Hello"
Hello
```


## `cat`

The `cat` command outputs the contents of a file to the terminal. When you type `cat hello.txt`, the contents of `hello.txt` are displayed.

**Catenate** is an obscure word meaning "to connect in a series", which is what the `cat` command does to one or more files.

``` bash
$ cat hello.txt
Hello
```

## `>`

The `>` command redirects the standard output to a file.

``` bash
$ echo "Hello" > hello.txt
```

`>` takes the standard output of the command on the left, and redirects it to the file on the right. Note that `>` **overwrites** all original content in `continents.txt`.

``` bash
$ cat oceans.txt > continents.txt
```

## `>>`

`>>` takes the standard output of the command on the left and **appends** (adds) it to the file on the right.

``` bash
$ cat glaciers.txt >> rivers.txt
```

## `<`

`<` takes the standard input from the file on the right and **inputs** it into the program on the left. Here, `lakes.txt` is the standard input for the `cat` command. The standard output appears in the terminal.

``` bash
$ cat < lakes.txt
```

## `|`

`|` is a **pipe**. The `|` takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as "command to command" redirection.

Here the output of `cat volcanoes.txt` is the standard input of `wc`. In turn, the `wc` command outputs the **number of lines, words, and characters** in `volcanoes.txt`, respectively.

``` bash
$ cat volcanoes.txt | wc
```

Multiple `|`s can be chained together. Here the standard output of `cat volcanoes.txt` is "piped" to the `wc` command. The standard output of `wc` is then "piped" to `cat`. Finally, the standard output of `cat` is redirected to `islands.txt`.

``` bash
$ cat volcanoes.txt | wc | cat > islands.txt
```

## `sort`

`sort` takes the standard input and orders it alphabetically for the standard output. Here, the lakes in `sort lakes.txt` are listed in alphabetical order.

``` bash
$ sort lakes.txt
```

Here, the command takes the standard output from `cat lakes.txt` and "pipes" it to `sort`. The standard output of `sort` is redirected to `sorted-lakes.txt`.

``` bash
$ cat lakes.txt | sort > sorted-lakes.txt
```

## `uniq`

`uniq` stands for **unique** and filters out adjacent, duplicate lines in a file. Here `uniq deserts.txt` filters out duplicates of "Sahara Desert", because the duplicate of 'Sahara Desert' directly follows the previous instance. The "Kalahari Desert" duplicates are not adjacent, and thus remain.

``` bash
$ uniq deserts.txt
```

A more effective way to call `uniq` is to call `sort` to alphabetize a file, and "pipe" the standard output to `uniq`. Here by piping `sort deserts.txt` to `uniq`, all duplicate lines are alphabetized (and thereby made adjacent) and filtered out.

``` bash
$ sort deserts.txt | uniq
```

Send filtered contents to `uniq-deserts.txt`.

``` bash
sort deserts.txt | uniq > uniq-deserts.txt
```

## `grep`

`grep` stands for **global regular expression print**. It searches files for lines that match a pattern and returns the results. It is case _sensitive_.

You can use **regular expressions** to search for patterns in files.

``` bash
$ grep Mount mountains.txt
```

`grep -i` enables the command to be case _insensitive_.

``` bash
$ grep -i Mount mountains.txt
```

`grep -R` searches all files in a **directory** and outputs filenames and lines containing matched results. `-R` stands for **recursive**.

``` bash
$ grep -R Arctic /home/ccuser/workspace/geography
/home/ccuser/workspace/geography/deserts.txt:Arctic Desert
/home/ccuser/workspace/geography/oceans.txt:Arctic Ocean
/home/ccuser/workspace/geography/uniq-deserts.txt:Arctic Desert
/home/ccuser/workspace/geography/continents.txt:Arctic Ocean
```

`grep -Rl` searches all files in a directory and outputs only filenames with matched results. `-R` stands for **recursive** and `l` stands for **files with matches**.

``` bash
$ grep -Rl Arctic /home/ccuser/workspace/geography
/home/ccuser/workspace/geography/deserts.txt
/home/ccuser/workspace/geography/oceans.txt
/home/ccuser/workspace/geography/uniq-deserts.txt
/home/ccuser/workspace/geography/continents.txt
```

## `sed`

`sed` stands for **stream editor**. It accepts standard input and modifies it based on an expression, before displaying it as output data.

``` bash
$ sed 's/snow/rain/' forests.txt
```

In the expression `'s/snow/rain/'`:

- `s`: stands for **substitution**.
- `snow`: the search string, the text to find.
- `rain`: the replacement string, the text to add in place.

In this case, `sed` searches `forests.txt` for the word "snow" and replaces it with "rain." Importantly, the above command will only replace the **first instance** of "snow" on a line.

``` bash
$ sed 's/snow/rain/g' forests.txt
```

The above command uses the `g` expression, meaning **global**. Here `sed` searches `forests.txt` for the word "snow" and replaces it with "rain", globally. All instances of "snow" on a line will be turned to "rain".

<br>

# Environment

Each time we launch the terminal application, it creates a new session. The session immediately loads _settings_ and _preferences_ that make up the command line environment.

We can configure the environment to support the commands and programs we create. This enables us to customize greetings and command **aliases**, and create **variables** to share across commands and programs.

## `clear`

**Clear** the terminal window. The command prompt should now be at the top of the window.

``` bash
$ clear
```

## `nano`

`nano` is a command line text editor. It works just like a desktop text editor like TextEdit or Notepad, except that it is accessible from the the command line and only accepts keyboard input.

- `Ctrl + O` saves a file. 'O' stands for **output**.
- `Ctrl + X` exits the nano program. 'X' stands for **exit**.
- `Ctrl + G` opens a **help** menu.

``` bash
$ nano hello.txt
```

## `~/.bash_profile`

`~/.bash_profile` or `.bashrc` is the name of file used to **store environment settings**. It is commonly called the _bash profile_. When a session starts, it will load the contents of the bash profile before executing commands.

- The `~` represents the user's **home directory**.
- The `.` indicates a **hidden** file.
- The name `~/.bash_profile` is important, since this is how the command line recognizes the bash profile.

``` bash
$ nano ~/.bash_profile
```

## `source`

`source` **activates the changes** in `~/.bash_profile` for the current session. Instead of closing the terminal and needing to start a new session, `source` makes the changes available right away in the session we are in.

``` bash
$ source ~/.bash_profile
```

## `alias`

The `alias` command allows you to create keyboard shortcuts, or **aliases**, for commonly used commands.

``` bash
$ alias pd="pwd"
```

## `history`

Show command histories.

``` bash
$ history
1 nano hello.txt
2 clear
3 nano ~/.bash_profile
4 clear
```

<br>

# Environment Variables

**Environment Variables** are variables that can be used across commands and programs and hold information about the environment.

## `export`

The line `USER="Jane Doe"` sets the environment variable `USER` to a name "Jane Doe". Usually the `USER` variable is set to the name of the computer's owner.

The line `export` makes the variable to be **available** to all child sessions initiated from the session you are in. This is a way to make the variable persist across programs.

``` bash
export USER="Jane Doe"
```

`$` is always used when returning a variable's value. Here, the command `echo $USER` returns the name set for the variable.

``` bash
$ echo $USER
Jane Doe
```

## `PS1`

`PS1` is a variable that defines the makeup and style of the **command prompt**. Here we change the default command prompt from $ to >>.

``` bash
$ export PS1=">> "
$ source ~/.bash_profile
>>
```

## `HOME`

The `HOME` variable is an environment variable that displays the path of the **home directory**.

``` bash
$ echo $HOME
/home/ccuser
```

## `PATH`

`PATH` is an environment variable that stores a list of directories separated by a colon. Each directory contains scripts for the command line to execute. `PATH` lists which **directories contain scripts**.

``` bash
$ echo $PATH
/home/ccuser/.gem/ruby/2.0.0/bin:/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/sbin:/sbin:/bin
```

## `env`

The `env` command stands for **environment**, and returns a list of the environment variables for the current user.

``` bash
$ env
```

`env | grep PATH` is a command that displays the value of a single environment variable (=PATH).

``` bash
$ env | grep PATH
```

<br>

# Permissions

**Overview**

- 3 levels of _ownership_: **user**, **group**, and **other**
- 3 _access types_: **r**ead, **w**rite, and e**x**ecute.

```
# +-------- Directory or not
# |  +------- User Read, Write, Execute
# |  |   +------- Group Read, Execute
# |  |   |   +----- Other Read, Execute
# |  |   |   |   +--- The name of the user
# |  |   |   |   |     +--- The name of the group
# |  |   |   |   |     |
# d|rwx|r-x|r-x user group
```

**Setting Permissions**

``` bash
$ ls -lah test.txt
-rwxr--r--  1 bob  staff  1GB Jul 14 15:24 test.txt

$ # Remove write access for user
$ chmod u-w test.txt
$ ls -lah test.txt
-r-xr--r--  1 bob  staff  1GB Jul 14 15:24 test.txt

$ # Add execute access for group
$ chmod g+x test.txt
$ ls -lah test.txt
-r-xr-xr--  1 bob  staff  1GB Jul 14 15:24 test.txt
```

**Number & Access level**

Number | Permission
- | -
0 | No permission granted.
1 | Can execute.
2 | Can write.
3 | Can write and execute (2 + 1 = 3).
4 | Can read.
5 | Can read and execute (4 +1 = 5).
6 | Can read and write (4 + 2 = 6).
7 | Can read and write and execute (4 + 2 + 1 = 7).

``` bash
$ chmod 777 test.sh
$ ls -l test.sh
-rwxrwxrwx  1 bob admin 0B Jul 15 15:24 test.sh

$ chmod 000 test.sh
$ ls -l test.sh
----------  1 bob admin 0B Jul 15 15:24 test.sh

$ chmod 754 test.sh
$ ls -l test.sh
-rwxr-xr--  1 bob admin 0B Jul 15 15:24 test.sh
```

**Users and Groups**

Users can belong to multiple groups, and groups can have multiple users. If a user belongs to a group, it will have the access types granted to the assigned group of any file or directory.

To determine if your user is part of a certain group, use the `groups` command:

``` bash
$ groups
ubuntu adm dialout cdrom floppy sudo audio dip video plugdev
```

**Root user**

The root user is the super user—it can read, write, and delete any file, but cannot execute just any file.

If you are logged in as a non-root user and know the root user's password, you can switch to the root user account at any time with the following command:

``` bash
$ su -
Password:
```

**`sudo`**

The `sudo` command allows you to "do" something as a "super user." When you use this command, you will usually be required to input a password; but instead of the root user's password, you'll be putting in **your own password**.

Why `sudo`

- The server administrator wants you to have root access for some commands and/or directories, but not for everything. In this case the administrator will set up sudo to have restrictions or whitelisted commands.
- Running commands while logged in as root can be dangerous. Using a non-root user makes it obvious when you are running a command that requires root privileges because you have to prefix your command with sudo.
- The sudo command provides a detailed audit trail so that system administrators can track what commands individuals used on system files.
- Sudo uses a ticketing system where you put in your password once, then you don't have to until you haven't run any sudo commands for five minutes or longer. This adds security to your command line session, preventing others from gaining root access if you leave your Terminal open on accident.
