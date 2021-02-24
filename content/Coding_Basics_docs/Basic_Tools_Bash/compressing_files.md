---
title: Compressing Files
linktitle: Compressing Files
toc: true
type: book
date: "2019-05-05T00:00:00+01:00"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 4
---
There are a vast number of ways we can apply ```zip```,```tar``` or ```gzip``` to bundle and/or compress and uncompress files. There are various packages that can be installed to facilliate this,b but here we focus on standard commands available on the command line using zip, tar, gz, bz2 and gz.  

## What are the differences between ```zip``` , ```tar``` and ```gzip```?
- ```tar``` just bundles files together into what is known as a tarball
- ```zip``` bundles up files and adds compression
- ```gzip``` can be used alonside ```tar``` to compress the created tarball. It can be used to compress files tighter than zip

## Zip and unzip
To compress:
```bash
zip -r archive_name.zip /path/to/folder_to_compress
```
To extract:
```bash
unzip archive_name.zip
```
## Tar and untar
To compress:
```bash
tar -zcvf archive_name.tar.gz /path/to/folder_to_compress
```
To extract:
```bash
tar -zxvf archive_name.tar.gz
```
If we want better compression than both ```tar.gz``` and ```zip```, we can use ```tar.bz2```
To compress:
```bash
tar -jcvf archive_name.tar.bz2 /path/to/folder_to_compress
```
To extract:
```bash
tar -jxvf archive_name.tar.bz2
```

### Appplying to Loops
```zip``` and ```tar``` don't always work intuitivly when used in loops. The following methods may be of more use when we are extracting multiple zip or tar files. 
#### unzip
If we want to unzip many ZIP files in a directory, ```unzip *.zip``` doesn’t work. Instead use:
```bash
unzip '*.zip'
```
In a loop:
```bash
for x in /path/to/*.zip; do unzip "$x"; done
```
or
```bash
for x in $(ls /path/to/*.zip 2>/dev/null); do unzip $x; done
```
#### untar
method 1
```bash
for f in *.tar.gz; do tar xf "$f"; done
```
method 2
```bash
cat *.tar.gz | tar xzf - -i 	# Note: this method will only extract the files/directories that exist at the point of execution
```
