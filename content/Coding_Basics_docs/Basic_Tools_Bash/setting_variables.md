---
title: Assigning Variables
linktitle: Assigning Variables
toc: true
type: book
date: "2019-05-05T00:00:00+01:00"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 8
---
## Why should you assign variables?
We can assign variable names to values within scripts (strings, integers, etc.).
## Basics: How to assign variables?
- We can create variables easily in bash using ```=```.
- We can use ```$``` to call variables.

#### 1. Variables for file paths and files
```bash
ROOT="/Users/bob/Documents/mri/data" #path to data directory
file="ntag.txt" #filename
```
It may be useful to intergrate variables when assigning file paths.
```bash
mrisubj="${ROOT}/mri" #path to structural MRI data directory
mrisubj="${ROOT}/fmri" #path to funtional MRI data directory
dtisubj="${ROOT}/dti" #path to DTI data directory
```
It may be useful to assign variables in more complex ways by using the results of an executes command within ``` ` ```

#### 2. Variables in ```for``` loops
Using the example from earlier, we can assign variables within a for loop. We do not need to assign using ```=```. 
##### Example 1
```bash
for subject in ${subject_list}; do
	echo "Processing subject ${subject}"
done
```
In this case, the first line of the $subject_list will be used as a variable $subject, in the first iteration of the loop. The second line of the ```$subject_list``` will be used as a variable ```$subject```, in the second iteration of the loop and so on. 
###### Example 2
```bash
for i in {1000..1500} ; do
	mkdir -p ${ROOT}/sub-${i}/ses-1/dwi
done
```
#### 3. Exporting variables in scripts
When we use variables with scripts they can only be seen within the process of the script. However if we want to use these variables outside of the scripts, for example, within another script, we must first export the variable using the ```export``` command. 
```bash
#!/bin/bash
subs_dir="/shared/probtrackx_processing"
error_dir="${subs_dir}/error_checking"
echo "$0: subs_dir=$subs_dir, error_dir=$error_dir" # check their values

export first_var
export second_var

./export_variables_script.sh

echo "$0: subs_dir=$subs_dir, error_dir=$error_dir" # check their values
```
In this example, ```i``` is used as the variable name, whcih is common for numerical (integer) loops. It iterated from loops with the assigned a value of 1000 to 1500. In this way we are able to create a BIDS data structure of 500 subjects. 
## Special Variables
```bash
$0 			# Filename of the script
$# 			# Number of command line parameters that are passed to the script
$@ 			# All command line parameters passed to the script
$? 			# Exit status of the last process to run
$$ 			# Process ID (PID) of the current script (PID=number used by most operating system to uniquely identify an active process)
$USER 		# Username of the user executing the script
$HOSTNAME 	# Hostname of the computer running the script (Hostname=what a device is called on a network. Also known as computer name or site name)
$SECONDS 	# The number of seconds the script has been running for
$RANDOM 	# Returns a random number
$LINENO 	# Returns the current line number of the script
```