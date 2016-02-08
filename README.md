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
[origin]   | Compute all pdf picture in a subdirectory "autogen" under the original figure path (Default in the source directory ).
[force]    | Force all tikz figures to be recompiled (Slower build).
[disable]  | Disable all pictures and replace by a black picture (Faster build).
[optimize] | Optimize generated pdf.
------

# Usage

Create you tikz figures in a separate file then include them in your tex source using
```
\includetikz[<options>]{path/to/image.tikz}
```
NB: .tikz or .tex extension work.

##### Options

------
Option         | valuetype | Description
---            | ---       | ---
[scale]        | float     | Scale the tikz image
[keepratio]    | X         | Scale the image and inverse scale font size
[font scale]   | float     | Scale tikz image font
[font style]   | string    | Tikz image font style (beta)
[fill opacity] | float     | Modify image opacity (beta)
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
```

##### Known bug/issues

- Refresh bug: Fail to regenerate files when options are changed on several
figures (Unresolved).

##### FAQS

*I get an MD5 write error `I can't write on file `figs/.md5'.*

This often happens when you output files in another directory using the
latex option `-output-directory=<workdir>`.
The easier solution is to create a simlink inside the working directory.
See the providen example.
