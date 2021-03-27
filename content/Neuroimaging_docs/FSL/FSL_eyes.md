---
title: FSLeyes
linktitle: FSLeyes
type: book
date: "2019-05-05T00:00:00+01:00"

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 2
---

FSLeyes is a software for viewing for 3D and 4D neuroimaging data. It comes as a standard component of FSL, but can be installed independently.

## Installation and Setup
FSLeyes is automatically installed as part of the [FSL installation](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLeyes). However you may want to update FSLeyes over time. 

To **update** FSLeyes use ```conda``` to run the following command: 
```bash
$FSLDIR/fslpython/bin/conda update -n fslpython -c conda-forge --update-deps fsleyes
```
To **install** FSLeyes in its entirety, it is available for download using ```conda-forge```. This will work if you are using a ```anaconda``` or ```miniconda``` environment.  
```bash
conda install -c conda-forge fsleyes
```
There are more advanced options for [downloading FSLeyes using Python](https://users.fmrib.ox.ac.uk/~paulmc/fsleyes/userdoc/latest/install.html).

## Overlays

The interface includes: 
- **The view**: This is where we view the overlays. The standard view is the **_orthographic view_** (ortho view) and is shown in the example below. However you can view images using using a **_lightbox view_** (series of adjacent slices along a single plane through your overlay), a **_3D view_** or a range of **_plot views_** eg. a time series view, a power spectrum and a histogram of voxel intensity.
	
- **View toolbar**: This toolbar allows you to adjust display settings of the view.
	
- **Overlay List**: Overlays can be 2D, 3D or 4D images or datafiles that can be views in FSLeyes. You can add multiple overlays and change their visibility and display order.

**_Note: multiple overlays must be in the same space eg.anatomical, Standard MNI, diffusion space_**

- **Overlay toolbar**: This toolbar allows you change display setting of each individual overlay in your overlay list. This may be particularly helful when using masks and highlighting areas of interest. 
	
- **Location Panel**: The location panel indicates the display location using space-specific coordinates and a voxel-based location.

{{< figure src="FSLeyes_display.png">}}

## Command Line Interface
The command line interface can be particularly helpful to open up multiple images consitently accross multiple subject scans.
To get a full overview of all the commands available to use with FSLeyes use: 
```bash
# Basic fsleyes options
fsleyes --help
fsleyes -h
# All fsleyes options
fsleyes --fullhelp
fsleyes -fh
```
Every FSLeyes command follows this pattern: 
```bash
fsleyes [options] file [displayOptions] file [displayOptions] ...
```
### My Secret Tip
While some of the many useful arguments are detailed in the [FSLeyes docs](https://users.fmrib.ox.ac.uk/~paulmc/fsleyes/userdoc/latest/command_line.html), it may be dificult to adjust exact settings using the command line alone. 
1. Using the FSL GUI, adjust your overlay displays.
2. Go to ```Settings > *View > Show command line for scene```. 
3. Copy the code from the window. 
> This code can be used to show you the exact settings used in your desired display. It may be easier to edit settings using this working template. You may want to use this methods to replicate views with complex display settgins across a number of subject scans. 

### FSLeyes screenshots using the Command Line Interface
Off-screen rendering in FSLeyes is very helpful for quality checking scans, particularly if you are processing a larger quantity of subject scans. 
For off-screen rendering we use the following command: 
```bash
fsleyes render ...
# Basic fsleyes render options
fsleyes render --help
fsleyes render -h
# All fsleyes render options
fsleyes render --fullhelp
fsleyes render -fh
```
To generate a screenshot you must specify a name for your output file within the command using the flag ```--outfile``` or ```-of```. Furthermore, you may chooose to include the size of our output: 
```bash
fsleyes render [options] --outfile outfile --size 800 600 file [displayOpts] ...
fsleyes render [options]  -of      outfile  -sz   800 600 file [displayOpts] ...
```
Additionally, you may want to specify an exact display view/scene:
```bash
fsleyes render --scene ortho    --outfile outfile file [displayOpts] ...
fsleyes render --scene lightbox --outfile outfile file [displayOpts] ...
fsleyes render --scene 3d       --outfile outfile file [displayOpts] ...
```