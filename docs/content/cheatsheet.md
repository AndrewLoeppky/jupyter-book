---
jupytext:
  formats: ipynb,md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: '0.8'
    jupytext_version: 1.4.1+dev
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

(myst_cheatsheet)=
# MyST Cheat Sheet

## Header

``````{list-table}
:header-rows: 1
:widths: 20 20 10

* - Text
  - Example
  - Note
* - ```md
    # Heading level 1
    ## Heading level 2
    ### Heading level 3
    #### Heading level 4
    ##### Heading level 5
    ###### Heading level 6
    ```
  - ```md
  	# MyST Cheat Sheet
    ```
  - Level 1-6 headings, denoted by number of `#`
``````

## Target Headers

``````{list-table}
:header-rows: 1
:widths: 20 20 10

* - Text
  - Example
  - Note
* - ```md
    (target_header)=
    ```
  - ```md
    (myst_cheatsheet)=
    # MyST Cheat Sheet
    ```
  - See {ref}`below <ref/target_headers>` how to reference target headers.
``````

(ref/target_headers)=
### Referencing Target Headers

Targets can be referenced with the [ref inline role](https://www.sphinx-doc.org/en/master/usage/restructuredtext/roles.html#role-ref) which by default uses the section title:
```md
{ref}`myst_cheatsheet`
```
You can specify the text of the target:
```md
{ref}`MyST syntax lecture <myst_cheatsheet>`
```
Another alternative is to use markdown syntax:
```md
[MyST syntax lecture](myst_cheatsheet)
```

## Quote

``````{list-table}
:header-rows: 1
:widths: 20 20 10

* - Text
  - Example
  - Note
* - ```md
    > text
    ```
  - ```md
    > this is a quote
    ```
  - quoted text
``````

## Thematic Break

``````{list-table}
:header-rows: 1
:widths: 20 20 10

* - Text
  - Example
  - Note
* - ```md
    ---
    ```
  - ```md
  	This is the end of some text.

    ---

    ## New Header
    ```
  - Creates a horizontal line in the output
``````

## Line Comment

``````{list-table}
:header-rows: 1
:widths: 20 20 10

* - Text
  - Example
  - Note
* - ```md
    % text
    ```
  - ```md
    a line
	% a comment
	another line
    ```
  - See [Comments](https://myst-parser.readthedocs.io/en/latest/using/syntax.html#syntax-comments) for more information.
``````

## Footnotes

``````{margin}
<br/><br/><br/><br/>
```{note}
Footnotes are displayed at the very bottom of the page.
```
``````

``````{list-table}
:header-rows: 1
:widths: 20 20 10

* - Text
  - Example
  - Result
* - ```md
    [^ref]

    [^ref]: Footnote text
    ```
  - ```md
    This is an example of a footnote.[^footnote1]

    [^footnote1]: The definition for referencing
     footnotes is generally placed at the bottom
     of the document.
    ```
  - This is a footnote reference.[^myref]
``````

[^myref]: This **is** the footnote definition.

See [Footnotes](https://myst-parser.readthedocs.io/en/latest/using/syntax.html#syntax-footnotes) for more information.

## Citations

```{note}
Make sure you have a reference bibtex file. You can create one by running `touch references.bib`.
```

``````{list-table}
:header-rows: 1
:widths: 20 20 20

* - Text
  - Example
  - Result
* - ```md
    {cite}`mybibtexcitation`
    ```
  - ```md
    This example generates the following
    citation {cite}`perez2011python`.
    ```
  - This example generates the following
    citation {cite}`perez2011python`.
``````

To include a list of citations mentioned in the document, introduce the `bibliography` directive
``````md
```{bibliography} ../references.bib
:filter: docname in docnames
```
``````
which is displayed below

```{bibliography} ../references.bib
:filter: docname in docnames
```

See [Citations](https://jupyterbook.org/content/citations.html?highlight=bibliography#bibliography) for more information.

## List

### Ordered List

``````{list-table}
:header-rows: 1
:widths: 20 20

* - Example
  - Result
* - ```md
  	1. First item
    2. Second item
    	1. First sub-item
    ```
  - 1. First item
    2. Second item
    	1. First sub-item
``````

### Unordered List

``````{list-table}
:header-rows: 1
:widths: 20 20

* - Example
  - Result
* - ```md
  	* First item
    * Second item
    	* First sub-item
    ```
  - * First item
    * Second item
    	* First sub-item
``````