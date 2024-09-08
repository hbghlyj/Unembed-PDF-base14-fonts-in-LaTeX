# Unembed PDF base14 fonts in LaTeX
Benefit:
1. Reduce file size.
2. Make the text editable in PDF editors (Adobe Acrobat can recognize base14 fonts, so can edit most of texts without switching to a different font).

⚠️Danger: `\sum` in Symbola font only works in Mozilla PDF.js and does not work in other viewer

# `pdffonts` output
As you can see from the table, PDF base14 fonts (including Times, Courier, Symbol) are not embedded.
```
name                                 type              encoding         emb sub uni object ID
------------------------------------ ----------------- ---------------- --- --- --- ---------
Times-Roman                          Type 1            Custom           no  no  yes      4  0
Times-Italic                         Type 1            Custom           no  no  yes      5  0
Courier                              Type 1            Custom           no  no  yes      6  0
Times-Bold                           Type 1            Custom           no  no  yes      7  0
Symbol                               Type 1            Custom           no  no  yes      8  0
YEELVS+CMSY10                        Type 1C           Builtin          yes yes yes      9  0
SEBDKK+CMMI10                        Type 1C           Builtin          yes yes yes     10  0
OKFTUL+rsfs10                        Type 1C           Builtin          yes yes yes     11  0
WWNUGL+MSBM10                        Type 1C           Builtin          yes yes yes     12  0
ATPFCN+CMEX10                        Type 1C           Builtin          yes yes no      13  0
```

# How it works
1. load the project into Overleaf
2. select `latex` engine
3. compile
## Note
Latexmk is used by Overleaf to control the compilation of your source LaTeX document into the final typeset PDF file. By using a customized configuration file called Latexmk you can override the default compilation commands to allow Overleaf to compile your document in a special way: In this project, first `latex` produces a `dvi` file, then `dvipdfmx` runs with the file `fontmap` as font map.

# File size comparison

| | size |
|--|--|
| original | 102 KB|
| processed | 13.4 KB|

Note: The original PDF is compiled by pdflatex (with default font map) and without `mathastext` package.
