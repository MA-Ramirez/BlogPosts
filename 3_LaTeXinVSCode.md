# Guide: LaTeX in VSCode 📝💻

## Introduction
Setting up LaTeX locally can be painful for a beginner. However, it can be quite advantageous in the long run. For example, it will enable you to write documents without an internet connection. It will also allow you to not depend on cloud-based editors, which means that when their servers are down, you don't need to stress if you are approaching a deadline.

_Note: There are many ways of setting up LaTeX locally. Here I explain one way that worked for me._

## Installation

### 1. Install VSCode on your computer
Visual Studio Code (or commonly known as VSCode) is a source-code editor, which you can [download for free](https://code.visualstudio.com) on your computer.

### 2. Install the LaTeX Workshop extension
Go to extensions in VSCode and install LaTeX Workshop.

_Steps 1 and 2 will allow you to use LaTeX in VSCode_

### 3. Install TeX Live
To use LaTeX locally you need to download TeX Live.

Depending on your operating system, there are different download options. For example, if you use Mac OS X, you can [download MacTeX](https://www.tug.org/mactex/), which installs the full TeX Live distribution and additional tools on your computer. (Don't worry if the MacTeX website looks old. Many LaTeX-related things look like this.)

_Warning: if you download the full TeX Live distribution, for example via MacTeX, you will download and install a ~5GB file on your computer._

_If you would like to download a smaller version of TeX Live in Mac OS X, you can [download BasicTex](https://tug.org/mactex/morepackages.html), which is only ~100MB._

Once you have installed TeX Live, it will be located in `/usr/local`.
To access it via finder, go to `locations -> macOS -> usr -> local`

(`cmd + shift + .` to show hidden folders in mac.)

## Useful commands to use LaTeX in VSCode ⌨️

Once you have performed steps 1, 2 and 3 you are ready to go.

Here are some helpful commands to use LaTeX in VSCode more easily:

### Build LaTeX project
**`cmd + alt + B`** or **`cmd + S`**

To compile the project and build the pdf file

###  View the tex and pdf files side-to-side
**`cmd + alt + V`**

### Go to a specific location in the file tex --> pdf
Place the cursor in the specific location of the tex file and press **`cmd + alt + J`**

### Go to a specific location in the file pdf --> tex
**`cmd + click`** in the specific location of the pdf file

### Clean auxiliary files 
**`cmd + click + C`**

Auxiliary files include files with the following extensions: .aux, .log, .synctex.gz, ...

### Wrap text
**`alt + Z`**

## Handling errors ❗️
Typical errors that you will encounter, especially if you downloaded BasicTeX are:

### Missing packages
Error example:
```
! LaTeX Error: File 'needspace.sty' not found
```

To solve this error you need to download the missing package `needspace` via tlmgr (the TeX Live manager):

* Type in the terminal `sudo tlmgr install <package-name>`

Typically, when you use the command `sudo` the computer will ask for its password, because it needs your permission to perform a given operation, in this case to install a package.

_Note: some packages are part of bundles, so to install the package, you need to install the bundle via `sudo tlmgr install <bundle-name>`._

_For example, to install the package `authblk` you need to install the `preprint` bundle._ 

To find information about TeX content, like packages and bundles, go to the [CTAN website](https://www.ctan.org).


#### tlmgr useful commands

* To update a package `sudo tlmgr update <package-name>`
* To update all packages `sudo tlmgr update -all`
* To update tlmgr itself `sudo tlmgr update -self`

[Here](http://tug.ctan.org/info/tlmgrbasics/doc/tlmgr.pdf) you can find a general usage guide for tlmgr.

### Missing fonts
Error example: 
```
! I can't find file 'phvr8t'.
<*> ...ljfour; mag:=1; ; nonstopmode; input phvr8t

```

To solve this error you need to download the missing font `phvr8t` via tlmgr (the TeX Live manager):

To install a font it is easier to install collections of fonts via bundles. The following are useful font bundles:

* `sudo tlmgr install psnfss` and `sudo tlmgr install collection-fontsrecommended`

## Install a word counter 🔢
If you would like for LaTeX to count the amount of words in your tex document in VSCode:

### 1. Install the LaTeX Utilities extension
Go to extensions in VSCode and install LaTeX Utilities.

### 2. Install the TeXcount package
Type in the terminal `sudo tlmgr install texcount`

--------------------------

Feel free to create an issue to share any questions or suggestions :)

Thank you to [Saumil Shah](https://github.com/saumil-sh) for his big brain 👾
