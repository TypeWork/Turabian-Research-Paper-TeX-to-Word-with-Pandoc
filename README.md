# turabian-researchpaper to Word with Pandoc (pandoc-turabian)

**turabian-researchpaper to Word with Pandoc** uses Pandoc to convert a `.tex` file (with a document class specified as `turabian-researchpaper`) into a new Microsoft Word document (`.docx`) with formatting based on the 9th edition of Kate L. Turabian’s *A Manual for Writers of Research Papers, Theses, and Dissertations: Chicago Style for Students and Researchers*.

In addition to converting a specified `.tex` file into a `.docx`, these scripts also provide the following features:
  - Support for LaTeX closing double-quotations in the `.tex` file;
  - Using a `filecontents` environment to create a `.bib` file;
  - Recognizing and using the BibLaTeX `\addbibresource` command for the bibliography;
  - Modifying 'starred' section headings (`\section*`) to use the "Heading 1 New Page" paragraph style;
  - Support for the `\course{}` and `\submissioninfo{}` commands from the [`turabian-researchpaper`](https://ctan.org/pkg/turabian-formatting) document class;
  - Support for the `\today` and `\jobname` commands;
  - Added styles and formatting using the reference doc `turabian-style-reference.docx` (based on the [Turabian Style Paper.dotm](https://github.com/TypeWork/turabian-style-paper-dotm) template);
  - Creating a title page section with page numbering starting on the next page;
  - Adding a colon at the end of the title, on the title page, if immediately followed by a subtitle;
  - Formatting the separator and continuation separator for footnotes;
  - Endnotes (demonted by the `\endnote{}` command) are preserved by being converted into footnotes;
  - Adjusting the visibility of styles automatically generated by Pandoc.
  
Support for endnotes, while remaining limited and under continued development, includes the following:
  - Activating endnote-related features if the `endnotes` option is passed to the [`turabian-researchpaper`](https://ctan.org/pkg/turabian-formatting) document class in the input `.tex` file;
  - Creating a "Notes" section where indicated by the `\theendnotes` command with endnotes set to "End of section";
  - If endnotes are used, footnotes are instead typeset with symbols and restart count with each page;
  - Endnotes, preserved as footnotes, start with `<Endnote />` tags.


## Get Started

In the command line interface, run *turabian-researchpaper to Word with Pandoc* by calling the perl script `pandoc-turabian.pl` followed by the name of the input `.tex` file:

```
pandoc-turabian.pl [InputLaTeXFile]
```

For best results, change the directory to where the file is located. When running the script, specifying the ".tex" file extension is optional.


## Installing

To install *turabian-researchpaper to Word with Pandoc*, place the files in the following locations.

User's `bin` directory (`$HOME/bin/`):
  - `pandoc-turabian-formatDoc.pl`
  - `pandoc-turabian-prepTeX.pl`
  - `pandoc-turabian.pl`.

Pandoc user data directory (`$HOME/.pandoc/`):
  - `chicago-note-bibliography.csl`
  - `turabian-latex-preamble.tex`
  - `turabian-style-reference.docx`.

The `chicago-note-bibliography.csl` file, provided in this repository, is taken directly from the [Zotero Style Repository](https://www.zotero.org/styles).

[Pandoc](http://pandoc.org) (version 2.2 or above) must be installed to use the `pandoc-turabian.pl` script.

[Perl](https://www.perl.org/get.html), version 5.010 or above, is also required to run the included perl scripts.


## Endnote Macro (VBA Script) for Microsoft Word

With endnote support remaining limited and experimental, an additional Microsoft Word macro (VBA Script) is provided: `PandocFormatEndnote.vb`

To install this script, create a new macro in Microsoft Word. Once a new macro is created, copy the contents of `PandocFormatEndnote.vb` into the macro and save.


## License

Copyright (C) 2018   Omar Abdool

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.
