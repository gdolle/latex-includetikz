# latex-includetikz
Latex package to include external tikz figures and similarly to \includegraphics command.


# Install

Add `includetikz` in your current directory, or texmf install. 
Then add
```
\usepackage[<options>]{includetikz}
```
in your text source.

##### Package options:

------
Option | Description
--- | ---
[external] | Compute all include tikz as external pdf files with checksum (see tikz external library).
------

# Usage

Create you tikz figures in a separate file then include them in your tex source using
```
\includetikz[<options>]{path/to/image.tikz}
```
NB: .tikz or .tex extension work.

##### Options

------
Option | Description
--- | ---
[scale] | Scale the tikz image
[draw scale] | Scale the image and inverse scale font size
[font scale] |  Scale tikz image font
[font style] | tikz image font style
------

##### Commands:

Command | Description
--- | ---
\includetikzdisable | Disable all pictures (to make compilation faster)

##### Examples:

Minimal example:
```
% Preamble.
\usepackage{includetizk}

% Document.
\includetikz[scale=0.9]{figs/monimage.tikz}
```
Generate monimage.tikz during first compilation, then use auto-generated pdf:
```
% Preamble.
\usepackage[external]{includetizk}

% Document.
\includetikz[font scale=1.3]{figs/monimage.tikz}
`

##### FAQS

*I get an MD5 write error `I can't write on file `figs/.md5'.*

This often happens when you output files in another directory using the
latex option `-output-directory=<workdir>`.
The easier solution is to create a simlink inside the working directory.
See the providen example.
