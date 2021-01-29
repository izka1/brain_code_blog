---
title: Zero Padding
linktitle: Zero Padding
toc: true
type: book
date: "2019-05-05T00:00:00+01:00"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 5
---
## What is zero padding?
Zero padding a number or a variable means putting leading zeros to a number, of a desired length.
Zero padding can be useful if you are labelling subjects, scan numbers or visit numbers etc.
### Example
With a datset of 50 subjects, your subject directories may look as follows:
```bash
sub-1
sub-2
sub-3
...
sub-10
sub-11
...
sub-49
sub-50
```
This will be problematic when analysing data iterativly. Data in this format will not process sequentially from ```sub-1``` to ```sub-50```.

#### ```Printf``` command
Using the print format command, you can decide the length of your zero-padding. In this this example we are padding our number to a length of 4 (```%04d```). The ```\n``` prints a new line after variable ```x```. 
```bash
x=23
printf "%04d\n" $x
```
```bash
0023
```
If we employ this technique in a loop, we can create the following output: 
```bash
for i in {1..50}; do
	subject_number=`printf "sub-%05d\n" $i`
	echo "$subject_number"
done
```
```bash
sub-00001
sub-00002
sub-00003
...
sub-00010
sub-00011
...
sub-00049
sub-00050
```
This technique is particularly helpful when reformatting neuroimaging data to follow the standardised BIDS format.