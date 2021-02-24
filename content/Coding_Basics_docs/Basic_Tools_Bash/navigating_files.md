---
title: Navigating the file system
linktitle: Navigating the file system
toc: true
type: book
date: "2019-05-05T00:00:00+01:00"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---
Modern file systems are made up of trees of directories (folders) and files. 
## Console and Terminal
Instead of navigating files and directories using OS GUIs (Figure 1), we can navigate teh system using the terminal/console. The console is technically the devise, and the terminal is the softare nested inside the console, but the two terms are used synonymously.

There are a number of terminal applications that are popular on different operating systems. I have listed a few popular examples:

| Operating System  | Terminal Emulators      | Notes          								|
| ------------------| ------------------------| --------------------------------------------|
| macOS             | - Terminal              | default macOS terminal                      |
| 	                | - iTerm2                | open-source terminal specifically for macOS	|
|                   | - xterm                 | default terminal when X11.app starts        |
| Microsoft Windows | - Windows Terminal      |	free in Microsoft Store						|
|    			    | - Windows Console       |												|
|    			    | - PuTTY                 |												|
| Linux 		    | - Gnome                 | default Ubuntu Terminal                     |
|        		    | - Terminator            | first non-default Terminal                  |
|    			    | - Terminology           |												|

## Shell
Although the terminal is good a displaying text output, it doesn't process input. We send input from the terminal to a shell program, which generates output and returns the output to the terminal so that it can be displayed. There are a number of shell programs that we can use. Here are a few popular choices: 
- bash
- zsh
- ksh
- sh
- Powershell
- cmd

## File Structure
Directories and files in an operating system can be navigated using the terminal. At the base of the file tree we have the root directory. Most operating systems have one root directory called ```\```. Some operating systems like Windows, have multiple root directories which are are named ```C:\```, ```A:\```, etc.
We can navigate into the root (home) directory using ```~``` or using ```cd``` alone.
```bash
cd ~
#or
cd
```
### Print working directory (```pwd```)
To show which directory we are currently in, we type ```pwd``` in the terminal. This can be particularly useful if we want to see the underlying file structure of a directory or file of interest.
### Change directory (```cd```)
To change directory we use: ```cd```; followed by the path to the new directory. In this example we are navigating directly to the directory titled Coding_Basics_docs
```bash
cd /Users/Isabella/Documents/brain_code_blog/content/Coding_Basics_docs
```
If we use ```..``` after ```cd```, this traverses backwards one step through the file tree.
```bash
cd ..
```
We can traverse backwards multiple steps through the file tree: 
```bash
cd ../..
```
We can go back to the most recent directory using:
```bash
cd -
```
### List contents of a directory (```ls```)
To list the contents of a directory we use: ```ls```.
```bash
ls
```
```bash
myDocuments myPictures myDesktop myDownloads BIN test.txt 
```
To list the contents of a directory, including details such as permissions, users, date/time modified and size, we use the addition of a flag: 
```bash
ls -l
```
To list the contents of a directory, including hidden dot files, we use the addition of a flag:
```bash
ls -a
```
We can also combine multiple flags:
```bash
ls -l -a
#or
ls -la
```