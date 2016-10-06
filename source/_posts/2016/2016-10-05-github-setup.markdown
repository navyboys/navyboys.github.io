---
layout: post
title: "Github Account Setup"
date: 2016-10-05 21:02
comments: true
categories: [github, ssh, note]
keywords: github development ssh
description: Notes for Setting up Github Account
---

Account needs to be set up with GitHub credentials so that you can push to your repositories on GitHub. Follow the steps below.

## Configure GitHub email

Make sure that you are using the e-mail address which you used when setting up your Git account.

``` bash
git config --global user.email 'your@email.com'
```

## Configure full name

Again, make sure that this is the full name which you originally used to set up your Git account.

``` bash
git config --global user.name 'Your Name'
```

## Generate Keys

SSH keys are a way to identify trusted computers, without involving passwords. The steps below will walk you through generating an SSH key and then adding the public key to your GitHub account.

Check the directory listing to see if you have files named either `id_rsa.pub` or `id_dsa.pub`. If you don't have either of those files go to **Configuring a New Key**. Otherwise, you can skip to **Add Your Public Key to GitHub** below.

``` bash
cd ~/.ssh
ls -al
```

## Configuring a New Key

To generate a new SSH key, copy and paste the text below, making sure to substitute in your email. The default settings are preferred, so when you're asked to "enter a file in which to save the key" just press enter to continue.

**Gotcha**: The first command (that starts with `eval`) uses **backticks** to quote the text that follows, not single quotes.

``` bash
eval `ssh-agent -s`
ssh-keygen -t rsa -C "your_email@example.com"
```
You should see something like the following:

``` bash
Generating public/private rsa key pair.
Enter file in which to save the key (/home/vagrant/.ssh/id_rsa): [Press enter]
```

Next, you'll be asked to enter a passphrase. Leave it blank (just hit enter without typing any other characters), as demonstrated below.

``` bash
Enter passphrase (empty for no passphrase): [Press enter]
Enter same passphrase again: [Press enter]
```

Which should give you something like this:

``` bash
Your identification has been saved in /Users/you/.ssh/id_rsa.
Your public key has been saved in /Users/you/.ssh/id_rsa.pub.
The key fingerprint is:
01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@example.com
```

Then add your new key to the ssh-agent:

``` bash
ssh-add ~/.ssh/id_rsa
```

## Add Your Public Key to GitHub

From the terminal, type the following:

``` bash
cat ~/.ssh/id_rsa.pub
```

This will give you a big block of characters which you should highlight and copy from your Terminal/PuTTy window.

1. In your browser, visit the [Account Settings](https://github.com/settings/admin) screen on GitHub.
1. Click on **SSH and GPG Keys** on the left sidebar.
1. Click **Add SSH Key**
1. In the Title field, add a descriptive label for the new key.
1. Paste your key into the "Key" field.
1. Click **Add key**.
1. Confirm the action by entering your GitHub password.
