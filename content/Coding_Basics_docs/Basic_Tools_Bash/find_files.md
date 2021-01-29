---
title: Find Files and Directories
linktitle: Find Files and Directories
toc: true
type: book
date: "2019-05-05T00:00:00+01:00"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 6
---

##Find files with a specified string: 
### Method 1
Use find funtion (with a wildcard)
This method operated recurrivly in current folder and subfolders.
```toml
find . -name 'mystring*'
```
If you want to restrict you seach only to file use -type f:
```toml
find . -name 'mystring*' -type f
```
If you want to use a case-insensitive search use -iname instead of -name:
```toml
find . -iname 'mystring*'
```
If you want to search in a specific directory, replace the . , which indicates you are searching in your current directory with your path to specified directory
```toml
find /path -name 'mystring*'
```
If you want to search for a file or directory and show theur size in MB:
```toml
find /path -name 'mystring*' -exec du -sm {} \
```
### Method 2
Use grep (with a wildcard)
This method operates only in the current directory. It will list the files with the specified string.
```toml
ls | grep "mystring*"
```