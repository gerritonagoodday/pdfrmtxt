# pdfrmtxt

Use this utility to remove any given string of text from a PDF file without having to edit the file with a bespoke PDF editor.

One particular use of this utility is to remove URLs of the websites that providers insert into their downloadable PDF files.
These annotations and watermarks are at best annoying, at worst they obliterate actual contents.

![No like](.images/removethissortofthing.png)

# Prerequisites:

You need to have the PDF Toolkit installed, a.k.a. "pdftk". Depending on your Linux distro, use one of the following installation commands:

    yum install pdftk
    equo install pdftk
    apt-get install pdftk
    emerge pdftk

# Usage:

    pdfrmtxt PDF-file

or

    pdfrmtxt PDF-file "annoying text"

# Example:

To remove the vexatious "http://free-pdf-books.com" URL that appears all over your downloaded PDF book, do this:

    pdfrmtxt ebook.pdf "http://free-pdf-books.com"

Remember to put a multi-word string in quotes

To remove many frequently-encountered strings, don't specify any removal string. The list of annoying strings in the source code will be used instead.
Add any further strings to the code yourself:

    pdfrmtxt ebook.pdf

To apply this on all PDF files in a directory tree, do this to un-taint your collection of PDF books:

    find . -name "*.pdf" -exec pdfrmtxt {} \; -print


# Installation:

Copy these files into your /usr/local/bin directory

    $ sudo cp pdfrmtxt* /usr/local/bin

# Health Warning:

- In rare cases, the text to be removed is encapsulated inside a font in the PDF file, so can't readily be identified in order for it to be removed using this process.
- Take care not to specify a PDF control terms to be removed, as this can potentially corrupt your entire PDF file.

# Author:

Gerrit Hoekstra. You can contact me via https://github.com/gerritonagoodday

Inspired by an idea of Bikramjot Hanzra on https://gist.github.com/bikz05

# Environmental Notice:

This work was created from 100%-recycled electrons. No animals were hurt during the production of this work, except when I forgot to feed my cats that one time. The cats and I are on speaking terms again.
