---
title: Loops
linktitle: Loops
type: book
date: "2019-05-05T00:00:00+01:00"
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 5
---

Bash loops are very useful. Loops allows us to keep re-running a series of steps and commands until it a set criteria has been reached. They are useful for automating repetitive tasks, and ensuring consistency in processing. 

## ```for``` loops
> For each item in the specified list, perform the specified set of commands
```bash
for item in <item_list>; do
	<commands>
done
```
#### Example 1
```bash
#!/bin/bash

for i in {1..50}; do
	subject_number=`echo "sub-$i"`
	echo "$subject_number"
done
```
#### Example 2
In this example we also used a counter (link). 
```bash
#!/bin/bash

# Set Variables
ROOT="/path/to/root"
filename="/path/to/ntag.txt" # load list of subjects
subject_list=`cat ${filename}` # get each line from file

# Set Counter
counter=0

#Create BIDS directory structure for scans
for subject in $subject_list; do
	echo "Processing subject ${subject}"
	mkdir -p "${ROOT}"/sub-"${counter}"/{ses-1,ses-2,ses-3,ses-4}/{anat,dwi}
	((counter++))
done
```
## ```while``` loops
> While an expression is true, continue executing specified commands
```bash
while [[ condition ]]; do
	<commands>
done
```
#### Example 1
```bash
#!/bin/bash

# Set Counter
counter=0

# print integer while counter is less than or equal to 20
while [ $counter -le 20 ]; do
	echo ${counter}
	((counter++))
done
```
## ```if``` loops/statements
> If a particular test is true, then perform a specified set of actions. It it is not ture, do not perform specified set of actions
```bash
if [[ condition ]]; then
	<commands>
fi
```
#### Example 1
In this example we also used `elif` command, short for else if. 
```bash
if [ -d "$ROOT/${subject}/MPRAGE" ] # if this MPRAGE directory exists 
then
    mri_scan='MPRAGE'

elif [ -d "$mrisubj/${subject}/Sag_IR-SPGR" ] # if this Sag_IR-SPGR directory exists
then
	mri_scan='Sag_IR-SPGR'
fi
```

