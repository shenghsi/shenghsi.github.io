---
title: 'homebrew notes'
date: 2021-01-02
permalink: /posts/2021/01/homebrew-notes/
tags:
  - mac
  - homebrew
  - macos
---

Homebrew notes

Homebrew notes ([Edit](https://github.com/shenghsi/shenghsi.github.io/blob/master/_posts/2021-01-02-homebrew-notes.md))
======

[How to clean unused homebrew dependencies](https://superuser.com/questions/1509212/how-to-clean-unused-homebrew-dependencies)
------
```bash
brew bundle
brew bundle dump
brew bundle --force cleanup 
```
brew now supports Brewfiles. brew bundle dump generates a Brewfile with all the packages installed by user. Dependent packages are not listed here
example:
```bash
brew "python3"
brew "curl"
brew "tmux"
brew "neovim"
```
This file can be used to install the same software automatically. You can call 
```
brew bundle
```
from the command line and all the listed applications get installed.

But also for doing a cleanup of unused packages. Edit the file then keep only the packages you need. Then run 
```
brew bundle --force cleanup
```
It will remove everything not listed or depending on the packages in the file.

WARNING: Also not listed casks will be removed
