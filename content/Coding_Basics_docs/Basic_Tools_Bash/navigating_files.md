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