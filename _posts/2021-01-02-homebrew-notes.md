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

Homebrew notes
======

[How to clean unused homebrew dependencies](https://superuser.com/questions/1509212/how-to-clean-unused-homebrew-dependencies)
------
Found on linuxbrew issue

brew bundle dump
brew bundle --force cleanup 
brew now supports Brewfiles. brew bundle dump generates a Brewfile with all the packages installed by user. Dependent packages are not listed here

example:

brew "python3"
brew "curl"
brew "tmux"
brew "neovim"
This file can be used to install the same software automatically. But also for doing a cleanup of unused packages. Edit the file then keep only the packages you need. Then run brew bundle --force cleanup. It will remove everything not listed or depending on the packages in the file.

WARNING: Also not listed casks will be removed
