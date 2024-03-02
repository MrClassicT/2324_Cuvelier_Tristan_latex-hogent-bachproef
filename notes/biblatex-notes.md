# biblatex-lint

## rules

### Errors

- BL0001 - Each BibLaTeX key should be unique
- BL0002 - All required fields should be present and not empty
- BL0003 - Author names should be written in the format "Last Name, FirstName and Last Name, FirstName and ...", or if the author is an organisation, its name should be in curly braces `{}`
- BL0004 - Dates should be written in the YYYY-MM-DD format
- BL0005 - Special characters should be replaced by the command to generate them (e.g. %, &, $, ...)
- BL0006 - Page range should be indicated with "em-dash", i.e. `--`

### Warnings

- BL1001 - BibLaTeX keys should match the author name (e.g. LastNameYear, LastNameEtAlYear) - default setting in JabRef
- BL1002 - Suggested fields (`WARN_FIELDS`) should be present and nonempty
- BL1003 - Prefer "journaltitle" over "journal"
- BL1004 - Prefer "institution" over "school"
- BL1005 - Prefer *original* types, not the aliases
- BL1006 - Prefer "date" over "year" and/or "month"

### Unsorted

- Remove text highlighting directive from URL (`#:~:text=`)
    - <https://chromestatus.com/feature/4733392803332096>
- Don't cite tertiary sources (if URL matches e.g. .google.com, .wikipedia.org, investopedia, etc.)
    - Ook: arxiv, Google books, researchgate, citeseerx?
    - Illegale dowloadsites als zLibrary
- Avoid citations without a date, e.g. date field is "n.d."  (may be superceded by BL0002 and BL0004)
- Don't cite homepage of a website (e.g. <www.microsoft.com>)
- If you use the url field, you should also use the urldate field

## Entry types

Source: <https://mirror.physik.tu-berlin.de/pub/CTAN/macros/latex/contrib/biblatex/doc/biblatex.pdf>

Must-have types:

- article
- book
- inbook
- booklet
- dataset
- manual
- misc (aliases: software)
- online (aliases: electronic, www)
- inproceedings (aliases: conference)
- report (aliases: techreport)
- thesis (aliases: mastersthesis, phdthesis)

Nice-to-have types:

- bookinbook
- collection
- custom[a-f]
- incollection
- inreference
- mvbook
- mvcollection
- mvproceedings
- mvreference
- patent
- periodical
- proceedings
- reference
- set
- suppbook
- suppcollection
- supperiodical
- unpublished
- xdata

Non-standard types: see section 2.1.3 of the biblatex manual.

## Required/recommended/optional fields

Attention: this is a rather *opinionated* list. More fields are indicated as "required" than in the biblatex manual.

- article
    - required: author, title, journaltitle, date
    - recommended: doi, volume, number, pages
- book
    - required: author|editor, title, date, publisher
    - recommended: isbn
- inbook
    - required: author|editor, title, booktitle, date, publisher
    - recommended: isbn|doi, pages
- booklet
    - required: author|editor, title, date, publisher
    - recommended: isbn|doi|url, howpublished
- dataset
    - required: author|editor, title, date, url, urldate
- manual
    - required: author|editor, title, date
    - recommended: organization|publisher, isbn|doi|url
- misc (aliases: software)
    - required: author|editor, title, date
- online (aliases: electronic, www)
    - required: author|editor, title, date, url, urldate
- inproceedings (aliases: conference)
    - required: author, title, booktitle, date
    - recommended: editor, eventtitle, isbn|doi|url
- report (aliases: techreport)
    - required: author, title, date, type, institution
    - recommended: doi|url
- thesis (aliases: mastersthesis, phdthesis)
    - required: author, title, date, type, institution
    - recommended: url
