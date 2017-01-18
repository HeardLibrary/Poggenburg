# Raymond Poggenburg's _Charles Baudelaire: Une Micro-histoire_

## The First Edition

In 1987, Raymond Poggenburg (1926-2004), a professor of French literature at Vanderbilt University, published the first edition of _Charles Baudelaire: Une Micro-histoire_. The aim of the project was to provide a detailed chronology of the life of Charles Baudelaire (1821-1867), the esteemed French poet and essayist.

The first edition of the _Micro-histoire_ is divided into four parts: the chronology, references, bibliography, and chronological index. The chronology, comprised of dated entries, constitutes the majority of the tome. It begins with the birth of Baudelaire's paternal grandfather, Claude Baudelaire, in 1711 and ends shortly after Baudelaire's death in 1867. Subsequently, the references are presented much like an endnote section, with up to 10 citations for each entry. The bibliography is an additional resource unto itself, encompassing primary source documents and critical studies up to the date of publication. Finally, the chronological index allows readers to look up individuals, places, or other relevant entities and find the chronology entries in which they are referenced.

It should be noted that Poggenburg distinguished his _Micro-histoire_ from a traditional biography of Baudelaire in a number of ways. While acknowledging that absolute objectivity was unattainable, Poggenburg insisted that the _Micro-histoire_ "ne s'offre pas comme exprimant le point de vue personnel de son auteur" (1987, 1). To emphasize the 'factual' nature of the work, Poggenburg did not write his _Micro-histoire_ as a single narrative but, rather, crafted 4,155 entries and organized them chronologically in order to document specific occurrences related to the life and work of Baudelaire. Furthermore, Poggenburg substantiated nearly every entry with at least one reference, drawn from a rich bibliography of primary and secondary sources. Even when the date of an event was derived from other information or research, Poggenburg identified the resources by which he extrapolated the information. The success of Poggenburg's effort to provide minimal supposition about the events he documented is reflected in the criticism leveled against the _Micro-histoire_: namely, that the title "Chronologie" would have sufficed, since there is no unifying narrative to earn the volume the title "Histoire" (Zeigler 1989, 310).

## The Second Edition

In the early 2000s, a second, [e-edition](http://diglib.library.vanderbilt.edu/baud-search.pl) of the _Micro-histoire_ was published jointly by the Vanderbilt University Press and Jean and Alexander Heard Libraries. The number of entries was expanded to 4,519, and the bibliography was extended to 475 items. The switch from a physical to digital medium for the _Micro-histoire_ was radical in many ways, but it aligned fundamentally with one of Poggenburg's key wishes for the work. By enabling more frequent updates and additions to the chronology and the bibliography, the new digital platform offered a means to make the _Micro-histoire_ "une sorte de chantier, un projet en développement, et non...un monument seulement" (1987, 1).

While Poggenburg's vision to have researchers regularly correct and augment the _Micro-histoire_ has yet to come to fruition, the online publication of the volume has greatly facilitated its use by students, researchers, and the interested public. The increased accessibility of the e-edition is due, in large part, to how the materials were digitized. Rather than preserve the layout of the first edition in an e-book format or scan and OCR a copy of the physical volume, it was decided that the contents of the _Micro-histoire_ would be loaded into a SQL database. Using a web portal built on the perl framework, the database could be queried by users from around the world, either with a keyword or date range.

There are, of course, a number of issues which arise in the translation of the _Micro-histoire_ from analogue to digital formats. One particularly intractable problem is the recording of dates. Though many of Poggenburg's entries have specific dates attached to them, the formatting is inconsistent and many are not absolute. Some entries, for example, date to "Spring" or "between October and November" of a specific year, whereas others may extend across multiple years. Even when the date is in the 'standard' first edition format of day (one- or two-digit arabic numeral), month (capital roman numeral), and year (two- or four-digit arabic numeral) separated by a space, a one- or two-letter abbreviation indicating the day of the week may be inserted between the month and year. The date issue was partially resolved in the e-edition by translating all dates into a mm/dd/yyyy format, and additional modifications (discussed below) have been made in order to optimize discovery of relevant information for date-based queries.

The structure of the first edition presents another problem for the production of an e-edition of the _Micro-histoire_. As outlined in the preceding section, the original _Micro-histoire_ had four distinct parts: chronology, references, bibliography, and chronological index. By appending the references to the appropriate entry for the chronology and replacing the chronological index with a keyword search, the e-edition preserves much of the functionality of the original _Micro-histoire_. The bibliographical database, however, remains hidden to the end-user of the second edition.

It may be argued that the _Micro-histoire_ bibliography has been supplanted by other bibliographical resources. Indeed, between 1965 and 2005, the [W.T. Bandy Center for French and Modern Studies](http://www.library.vanderbilt.edu/bandy/) at the Jean and Alexander Heard Libraries published an annual review of publications related to Baudelaire in the [Bulletin Baudelairien](http://discoverarchive.vanderbilt.edu/handle/1803/4125). Additionally, between 2006 and 2012, the Bandy Center published a separate Baudelairian [Recensement Bibliographique](http://www.library.vanderbilt.edu/bandy/publications.shtml) online. Nevertheless, not every publication on Baudelaire contains information relevant to the _Micro-histoire_, and the inability to programmatically access Poggenburg's bibliography hinders continued development of the dataset by not permitting scholars to easily identify whether a resource has been reviewed for information or not. 

## Digital Data Preservation in MODSXML

In August 2016, due (in part) to the deterioration of the perl framework on which the e-edition was built, the _Micro-histoire_ data preservation project was initiated. First, the e-edition entry and bibliography databases were flattened and exported to CSV files. Subsequently, [OpenRefine](http://openrefine.org/) and an assortment of customized VBA macros were used to clean and standardize the data. In addition to basic data cleaning such as proofreading, the removal of duplicate entries, and the standardization of names and references, some of the substantive changes to the data were as follows:
  * Dates were restructured and standardized to more accurately and consistently represent the original Poggenburg entries.
  * Unfinished bibliographical references (e.g. missing page numbers, publication information, titles) were completed, where information was available.
  * Bibliographical information (e.g. volume and issue numbers, article page numbers, etc.) was checked against the original publications or worldcat records and corrected.

After consideration of the [Dublin Core](http://dublincore.org/documents/dces/) and [CIDOC Conceptual Reference Model](http://www.cidoc-crm.org/) schemata, the Library of Congress [Metadata Object Description Schema (MODS) version 3.6](http://www.loc.gov/standards/mods/) was selected for structuring and marking up the _Micro-histoire_ data and metadata in XML. Some of the applicable benefits of MODS for the project include:
  * Appropriate granularity for different types and formats of dates.
  * Well-developed syntax and vocabularies for relating items and objects to one another.
  * Adaptability for describing physical and digital objects.
  * Integration with LOC subject headings.
  * Flexibility in the definition of top-level elements for non-bibliographic information.

Despite the appropriateness of MODS to the data and metadata of the _Micro-histoire_, several adaptations were made in order to fully and acurately describe the records. An explication of the instantiation of MODS 3.6 used in the _Micro-histoire_ XML files follows in the form of an annotated sample record and a brief reference guide.

## An Annotated _Micro-histoire_ Entry

Following is a sample entry from the _Micro-histoire_, as it appears in the present github repository, with a description of its basic structure and syntax.

```XML
<?xml version= "1.0" encoding="UTF-8"?>
<mods xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.loc.gov/mods/v3" version="3.6" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-6.xsd">
```
The header for every record is the same. It identifies the version of XML, character encoding, and version of MODS utilized.
```XML
    <identifier displayLabel = "record number" type = "local">
        6115
    </identifier>
```
The `identifier` is a unique number assigned to each entry of the _Micro-histoire_. It was generated when the entries were loaded into the database for the e-edition.
```XML
    <originInfo>
        <dateCaptured>
            08/16/1999
        </dateCaptured>
        <dateModified>
            03/08/2002
        </dateModified>
    </originInfo>
```
The `originInfo` for the Poggenburg entries includes the `dateCaptured` (formatted as `MM/DD/YYYY`, the date on which the digital entry was first created) and the `dateModified` (formatted as `MM/DD/YYYY`, the date on which the entry was last modified for the e-edition).
```XML
    <subject>
        <temporal point = "start">
            04/09/1821
        </temporal>
        <temporal point = "end">
            04/09/1821
        </temporal>
    </subject>
```
The `subject` field corresponds to Library of Congress subject headings. Its contents, as indicated by the 'temporal' subelements, define the date(s) for which Poggenburg recorded the events of the _Micro-histoire_ entry. To more accurately reflect the different types of dates and date ranges Poggenburg used, `start` and `end` points were incorporated (formatted as `MM/DD/YYYY`). In the case of this entry, since the exact date of the event is known, both the `start` and `end` dates are the same.
```XML
    <note type = "poggenburg date">
        9 IV 21
    </note>
```
In order to preserve the first and second edition entry headings, `note type = "poggenburg date"` has been used to record the contents of Poggenburg's dates.
```XML
    <note type = "journal content">
        Naissance de Charles Baudelaire au 13, rue Hautefeuille {1}.
    </note>
```
`note type = "journal content"` records the contents of Poggenburg's entry in the _Micro-histoire_.
```XML
    <relatedItem type = "references">
```
As has been stated above, the content of each of the _Micro-histoire_ entries is substantiated by at least one reference. The bibliographical information about each reference is included in its own `relatedItem type = "references"` element.
```XML
        <identifier displayLabel = "bibliographic abbreviation" type = "local">
            P-Z
        </indentifier>
```
The `identifier` within each `relatedItem` is a unique bibliographical abbreviation derived from the e-edition bibliographical database.
```XML
        <titleInfo>
            <title>
                Baudelaire
            </title>
        </titleInfo>
```
As prescribed by MODS 3.6, the `title` of each reference item is placed inside the `titleInfo` container.
```XML
        <name type = "personal">
            <namePart>
                Pichois, Claude
            </namePart>
            <role>
                <roleTerm type = "text">author</roleTerm>
            </role>
        </name>
        <name type = "personal">
            <namePart>
                Ziegler, Jean
            </namePart>
            <role>
                <roleTerm type = "text">author</roleTerm>
            </role>
        </name>
```
Authors and editors (up to three each) are listed after the `titleInfo`, with their exact role in creating the work defined in the `roleTerm` field.
```XML
        <originInfo>
            <place>
                <placeTerm type = "text">Paris</placeTerm>
            </place>
            <publisher>
                Julliard
            </publisher>
            <dateIssued>
                1987
            </dateIssued>
            <dateCaptured>
                03/07/2002
            </dateCaptured>
            <dateModified>
                03/07/2002
            </dateModified>
        </originInfo>
```
The `originInfo` subelement of `relatedItem` describes two types of data: the publication information of the work (`place`, `publisher`, and `dateIssued` formatted as `YYYY`) and the dates (formatted as `MM/DD/YYYY`) when the citation was first added to (`dateCaptured`) or updated in (`dateModified`) the e-edition.
```XML
        <part>
            <extent unit = "pages">
                <start>
                    51
                </start>
                <end>
                    51
                </end>
            </extent>
        </part>
```
The `part` subelement is applied in the _Micro-histoire_ in order to record the specific pages of the work which Poggenburg cited. In order to accommodate multi-page citations, the `extent` of the `part` cited includes both a `start` and an `end` page number. If only one page is cited, the `start` and `end` numbers will be the same, as here.
```XML
        <genre>
            Book
        </genre>
```
For the e-edition of the _Micro-histoire_, the genre (book, article, catalog, etc.) of every work cited was recorded. In order to remain compliant with MODS standards, the `genre` is recorded and appropriate standards followed for each type of work.
```XML
    </relatedItem>
```
As noted above, if there is more than one work cited in the _Micro-histoire_ entry, each citation will appear in its own `relatedItem` container.
```XML
</mods>
```
Each record ends with a closing `mods` tag.

## A Note on File Names

The file names have been constructed by linking two data points with an underscore (_): the identifier assigned to the record in the e-edition of the _Micro-histoire_ and the start date of the Poggenburg entry, formatted as YYYY-MM-DD. The inclusion of the e-edition identifier, though arbitrarily assigned, is to ensure that each record has a unique filename. The file name for the example annotated above, therefore, is 6115_1821-04-09.xml.

## MODS 3.6 Elements and Attributes in the _Micro-histoire_

While users of the _Micro-histoire_ XML files in the present repository are directed to the [MODS 3.6 Outline of Elements and Attributes](http://www.loc.gov/standards/mods/mods-outline-3-6.html) page for a full, human-readable description of the schema, a brief guide to relevant elements and attributes is provided here for reference. The list is organized alphabetically by top-level element, and the following format is used:

#### [top-level element name]\* ([type of data recorded, blank if only a container])
[general description, if applicable]
* Attributes:
   * [attribute name] \([content])
* Subelements:
   * [subelement name] \([type of data recorded])
      * [attribute name] \([content])

\* As seen in the annotated record above, `relatedItem` has been used to link bibliographical information to each of Poggenburg's _Micro-histoire_ entries. As is noted in the documentation for MODS 3.6, the top-level element [`relatedItem`](http://www.loc.gov/standards/mods/mods-outline-3-6.html#relatedItem) may accept any of the other top-level elements as a subelement. In lieu of creating an expansive and recursive list of subelements in the description of how the `relatedItem` element has been applied to the _Micro-histoire_, an asterisk (\*) will be added to any elements, attributes, subelements, or data types used exclusively within the relatedItem container, while a carat (^) will be appended to indicate use within _Micro-histoire_ chronology entries. No notation will indicate common usage between the chronology entry and relateItem container.

#### `genre`\* (string)
In accordance with the [MARC Genre Term List](http://www.loc.gov/standards/valuelist/marcgt.html), a MODS-compliant controlled vocabulary, the genre of the work cited.

#### `identifier` (integer^ or string\*)
A unique identifier of the _Micro-histoire_ chronology or bibliography entry, based on the e-edition.
   * Attributes:
      * displayLabel ("record number"^ or "bibliographic abbreviation"\*)
      * type ("local" or "lccn"\*)

#### `name`\*
The `name` container includes information about the author or editor of the work cited.
   * Attributes:
      * type ("personal")
   * Subelements:
      * namePart (string)
      * role (string)
         * type ("text")

#### `note` (string)
Notes are used to contain non-bibliographical information which cannot be standardized. The content of the _Micro-histoire_ entries, the Poggenburg-formatted entry dates, and comments intended for current and future curators of the dataset (as included in the e-edition) are recorded within different notes.
   * Attributes:
      * type ("poggenburg date"^ or "journal content"^ or "researcher notes"^ or "source note"\*)

#### `originInfo`
The subelements are used to describe when the entry was added to (`dateCaptured`), or modified in (`dateModified`), the e-edition databases. `originInfo` also includes publication information for works cited, including place of publication, year of publication, and publisher.
   * Subelements:
      * dateCaptured (MM/DD/YYYY)
      * dateIssued\* (YYYY)
      * dateModified (MM/DD/YYYY)
      * place\*
         * placeTerm (string)
            * type ("text")
      * publisher\* (string)

#### `part`\*
The `part` element is used in the `relatedItem` bibliographical information for two purposes. The first is to provide additional publication information for works which are part of series, such as the enumerations of journals and newspapers. This includes use of the `extent` sub-element to designate the page numbers for articles and chapters of larger works (nested under the `related Item type = "host"` element). The second use is to define the specific pages cited by Poggenburg in each entry, which is denoted by the `extent` subelement of the `related Item type = "references" element.
   * Subelements:
      * detail
         * type ("volume" or "issue" or "number")
         * number (integer)
         * caption (string)
      * extent
         * unit ("pages")
         * start (integer)
         * end (integer)
      * date (MM/DD/YYYY)

#### `relatedItem`\*
As indicated above, `relatedItem` is the only top-level element in MODS which may take every other top-level element (including itself) as a subelement. The user of the _Micro-histoire_ XML files is directed to the [extended documentation](http://www.loc.gov/standards/mods/v3/mods-userguide-elements.html) for the schema, specifically the section on `relatedItem`, for further explication of its use in constructing bibliographical references.
   * Attributes:
      * type ("references" or "host" or "series")

#### `subject`^
Corresponding to Library of Congress subject headings, this element is used to define the date(s) on which the _Micro-histoire_ events occurred.
   * Subelements:
      * temporal (MM/DD/YYYY)
         * point ("start" and "end")

#### `titleInfo`\*
The container element for the title of works cited in the _Micro-histoire_.
   * Subelement:
      * title (string)

## Next Steps

We encourage you to download the _Micro-histoire_ dataset (available as a zip file in this repository) and experiment with it. Perhaps you are curious about Baudelaire's translations of Poe? See if you can write a query to find all mentions of Edgar Allan Poe and follow where the results take you. (You may be surprised to find that a very basic query will bring up a number of bibliographical references, too.) Are you interested in Baudelaire-related events during a specific period of the 19th century? Then write a query to gather all of the entries from a specific year or date range and determine how you would like to organize and search the information returned. Does the _Micro-histoire_ bibliography interest you as a starting point for your own research? Write a query to return all unique works cited.

If you encounter any issues with the _Micro-histoire_ dataset as you play with and ply it for information, please submit an issue with details to help us improve the dataset for the future.

[CC BY-NC 2.0](https://creativecommons.org/licenses/by-nc/2.0/)