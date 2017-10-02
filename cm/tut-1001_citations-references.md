citations and references basics
================

-   [preparation](#preparation)
-   [creating the bib file](#creating-the-bib-file)
-   [adding a bibliography to the YAML header](#adding-a-bibliography-to-the-yaml-header)
-   [adding citations to your prose](#adding-citations-to-your-prose)
-   [adding a references heading](#adding-a-references-heading)
-   [formatting the citations and references](#formatting-the-citations-and-references)

preparation
-----------

Start by opening your RStudio project:
File → Recent projects → me447\_visualizing-data.Rproj.

> ALWAYS start your work session by launching the .Rproj file you created for this course

Using an R Project sets the working directory to your course folder, making relative file paths easy to use.

creating the bib file
---------------------

We'll use the bib format (from BiBTeX) for bibliographies (other formats are available).

The bib file contains the complete list of references used in your portfolio. It can contain more refences than needed; only those references actually cited will appear.

Create your bib file:

-   Open a new text file in RStudio, *File* &gt; *New File* &gt; *Text File*
-   *Save As* `portfolio.bib` in the `portfolio` directory
-   In the `.bib` file, type your references in BiBTeX format, for example:

<pre class="r"><code>@manual{ansi1995,
    title        = {Process instrumentation terminology},
    edition      = {ANSI/ISA-S51.1-1979, reaffirmed 1995},
    organization = {Instrument Society of America},
    address      = {Research Triangle Park, NC},
    year         = {1995},
    note         = {ISBN 0-87664-390-4},
}</code></pre>
-   `@manual{}` and its enclosing braces denotes the *entry type*, i.e., an article, a book, etc. BiBTeX has numerous predefined entry types; see [entry types](https://nwalsh.com/tex/texhelp/bibtx-7.html) by Norm Walsh and [verbosus](https://verbosus.com/bibtex-style-examples.html) for the most commonly encountered entry types and their arguments.
-   `@ansi1995` is the unique label assigned to this reference. I usually use an `@authorYear` style, for example `@gandrud2015`.

Words in your bibliography are sometimes not capitalized the way you expect. If that happens, return to the `.bib` file and place braces `{}` around letters you want capitalized. For example,

    @book{gandrud2015,
      author    = {Christopher Gandrud}, 
      title     = {Reproducible {R}esearch with {R} and {RS}tudio},
      publisher = {CRC Press},
      year      = {2015},
      address   = {Boca Raton, FL},
      edition   = {2},
    }

### exercise

-   Find the entry style for a book and copy it into your bib file
-   Edit the entry to include all the information for our course text book by Naomi Robbins.

adding a bibliography to the YAML header
----------------------------------------

Add the bibliography argument to the YAML header.

<pre class="r"><code>---
title: "Portfolio"
author: "name"
date: "date"
output: word_document
bibliography: "portfolio.bib"
---</code></pre>
(If the bib file is not in the same directory as your Rmd file, include the path to the bib file as well, for example, `some_path/portfolio.bib`.)

### exercise

-   Add the bibliography argument to the YAML header of your portfolio.

adding citations to your prose
------------------------------

In the Rmd file, add the citation at the appropriate place in your prose, for example,

<pre class="r"><code> The test procedure follows the ANSI/ISA standard [@ansi1995]. 
</code></pre>
The citation syntax has the form `[@label]`, where the `@label` is the unique label we assigned to the reference in the bib file.

### exercise

-   Add a citation for the Robbins text somewhere in one of your critiques.

adding a references heading
---------------------------

At the end of the Rmd script, add a references section heading.

<pre class="r"><code># References
</code></pre>
Knit the document. The citation should appear in the prose and the formatted references are output at the end of the document.

### exercise

From your critique of D1 in your portfolio,

-   write each reference into your .bib file
-   add the `[@namedate]` citation markup in your critique
-   knit the document to check that it all works

formatting the citations and references
---------------------------------------

You don't have to do this step right away, but you might want to later in the term.

Quite often a publisher or organization requires that citations and references be formatted in a specific way, for example, IEEE requires a numbered citation and numbered references while an APA style uses an author-date citation and an alphabetically-ordered bibliography.

We use a CSL file to override the default Rmd citation/reference style.

-   Find a format you like at the [Zotero Style Repository](https://www.zotero.org/styles) or at the official [CSL Repository](https://github.com/citation-style-language/styles) that suits your needs, for example `chicago-author-date.csl` or `ieee.csl`
-   Download the CSL file and save it to the same directory as the portfolio
-   Edit the YAML header to designate the CSL style file you wish to use.

<pre class="r"><code>---
title: "Portfolio"
author: "name"
date: "date"
output: word_document
bibliography: "portfolio.bib"
csl: "chicago-author-date.csl"
---</code></pre>
Knit your document and both the citation formatting and the references formatting will change throughout the document.

### exercise

-   Find and download the CSL file called: `journal-of-peace-research.csl`
-   Save it to your portfolio directory
-   Edit the Rmd YAML header to use this CSL
-   Knit your document; check that the references style has indeed been updated.

For your final portfolio, I prefer an author-date style for ease of reading. Select any author-date CSL file you like.

------------------------------------------------------------------------

[main page](../README.md)<br> [topics page](../README-by-topic.md)