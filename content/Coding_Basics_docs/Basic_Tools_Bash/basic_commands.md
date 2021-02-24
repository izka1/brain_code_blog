---
title: Basic Commands
linktitle: Basic Commands
type: book
date: "2019-05-05T00:00:00+01:00"
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 2
---
# BASH Cheatsheet

## Fundamental commands to navigate the terminal

`ls`= list files
`cd`= change directory
`pwd`= present working directory
`mkdir`= make directory
`mv`= move (or rename)
`rm`= remove (file)
(**Use this command with caution: effects are irreversible**)
`rmdir`= remove (directories) safe way to remove directories
`rm -r` = remove (recursivly) removes all files and directories downstream of removed directory
`cp`= copy (file)
`cp -r`= recursive copy (directory)
(**This means you are copying a directory**)
`man (followed by a command)`= displays information about comands
`ls -a`= list files including those that may be hidden (dot files). Hidden files that will become particularly important in most cases are bash profile scripts eg. **_bashrc, .bash_profile, .profile_**
`ls -l`= list (long option) list of files and what kind of files they are, what size they are, date created, owners and permissions
`ls -lrt`= list (reverse time order)
`cat`= concatenate and print file to screen
`echo`= prints arguments followed by an end of line character
`printf` = prints arguments allowing for definintion of a formatting string
`less`= smaller version output

## Creating, writing and editing new files
```bash
touch new_file.sh # Create a script (.sh) document entitled new_file
```
If you want to view, write or edit the contents of a text file, you can use a number of text editors. Note that each text editor uses differnt syntax and offers tools of a varying complexity. 

`nano` and `vim` are amongst the most popular ones.
- `nano` is a very basic plain text editor
- `vim` is a powerful text editor (steeper learning curve)

### Permissions:

`r` =read
`w` =write
`x` =execute

* First 3 for owner (u=user)
* Second 3 for group (g)
* Third for everyone (o)

`chmod`=change permissions

When creating a new files, particularly a new script, you will have to ensure it is executable by typing the following command:
```bash
chmod a+x new_file.sh # Make new script executable
```
You will only need to do this once after you create your script. If you make edits to the content of the script you will not need to repeat this command to run the script.
Now you can run your script using:
```bash
./new_file.sh # Create a script (.sh) document entitled new_file
```
