---
title: Basic Commands
linktitle: Basic Commands
type: book
date: "2019-05-05T00:00:00+01:00"
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 2
---
## Basic Navigation
Directories and files in an operating system can be navigated using the terminal. At the base of the file tree we have the root directory. Most operating systems have one root directory called ```\```. Some operating systems like Windows, have multiple root directories which are are named ```C:\```, ```A:\```, etc.
### Print working directory (```pwd```)
To show which directory we are currently in, we type ```pwd``` in the terminal. This can be particularly useful if we want to see the underlying file structure of a directory or file of interest.
```bash
pwd
```
### Change directory (```cd```)
To change directory we use: ```cd```; followed by the path to the new directory. In this example we are navigating directly to the directory titled Coding_Basics_docs
```bash
cd ~ 		# navigate into the root (home) directory
cd 			# navigate into the root (home) directory
cd /Users/Isabella/Documents/brain_code_blog/content/Coding_Basics_docs # change working directory to specified directory (folder), in this case the Coding_Basics_docs folder
cd .. 		# traverses backwards one step through the file tree
cd ../.. 	# traverses backwards two steps through the file tree
cd - 		# go back to the most recent directory
```
Good Habit #1 : Use descriptive directory names and files names, where possible. Hoarding a bunch of 'untiltled_8.txt' files or vague directory names can make it less intuitive to navigate your system.
Good Habit #2 : Bash is whitespace sensitive meaning each argument is separated by a space. When naming files and directories enure that you don't use spaces. Often ```-``` or ```_``` are used to join a string of words in filenames or directory names. 
### List contents of a directory (```ls```)
To list the contents of a directory we use: ```ls```.
```bash
ls 		# list files in directory
ls -a 	# list files including those that may be hidden (dot files). Hidden files that will become particularly important in most cases are bash profile scripts eg. _bashrc, .bash_profile, .profile_
ls -l 	# list (long option) list of files and what kind of files they are, what size they are, date created, owners and permissions
ls -la  # combines funtions of both -l and -a flags
ls -lrt # list files in reverse time order
```
## Basic Editing
### Move, rename and copy
The same command is used to copy and rename files and directories
```bash
mv file_1.txt /path/to/new/directory 	# moves file_1.txt into a new directory
mv file_1.txt data.txt 	# renames file_1.txt to data.txt, but keeps it in the same location
mv file_1.txt /path/to/new/directory/data.txt # renames file_1.txt to data.txt, and moves the renamed file into a new directory
cp file_1.txt file_1_copy.txt 	# copies file_1.txt and saves it in the same directory as file_1_copy.txt
cp file_1.txt /path/to/new/directory/file_1.txt # copies file_1.txt and saves it in a new directory as file_1.txt
cp -r directory_1 directory_1_copy # copies directory_1 (recursively) and saves it in the same directory as directory_1_copy
```
### Removing files and directories
```bash
rm file_1.txt	# remove (file) Note: use this command with caution
rmdir directory_1	# remove (directories)
rm -r directory_1	# remove (recursivly) removes all files and directories downstream of removed directory. It can be used instead of rmdir
```
### Creating, writing and editing new files and directories
```bash
mkdir new_directory	# create directory called new_directory
touch new_file.sh # create a script (.sh) document entitled new_file
```
To quickly view the inside of a file (no editing ability) we can use:
```bash
cat 	#concatenate and print file contents
```
If you want to view, write or edit the contents of a text file, you can use a number of text editors. Note that each text editor uses differnt syntax and offers tools of a varying complexity.

`nano` and `vim` are amongst the most popular ones.
- `nano` is a very basic plain text editor
- `vim` is a powerful text editor (steeper learning curve)

### Other commands
```bash
echo $variable 	# prints arguments (variable in this case) followed by an end of line character
echo "Hello, world" # prints the string "Hello, world" followed by an end of line character
printf 	# prints arguments allowing for definintion of a formatting string
less filename	# smaller version output
man any_command	# displays information/ user manual for that specific command
```

### Permissions

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
