# Names for Biodiversity Workshop

https://github.com/tdwg/tnc/tree/master/TDWG2018

## Introduction
 Recent work on names is fragmented into individual and isolated project efforts. There are now more terms than concepts, more definitions than terms. Many, more-or-less, similar vocabularies, alternative frameworks and non-interoperable, application systems.

 This may well be the natural process of evolution but we do need to make time now to discuss synthesis and a more collaborative approach to development of a workable standard for names. Can we work together to fill the gaps, and to resolve the competing requirements of aggregation and science, data and knowledge, product and research, Code-compliance and interoperability.

## Purpose
 To raise awareness of the importance of names to biodiversity informatics and to re-invigorate a more collaborative phase of standards development with names within the TDWG umbrella.

 This workshop will aim for consensus around the idea that we can work together within TDWG to evolve a pragmatic replacement for the existing names standards, and a map to get us there.

## Goals

1. Reconvene the [Taxonomic Names and Concepts Interest Group](https://www.tdwg.org/community/tnc/)
	- Membership
	- GitHub, [tdwg/tnc](https://github.com/tdwg/tnc)
	- Standards maintenance.
2. Agreement on a plan for a replacement of the **Taxonomic Concept Transfer Schema (TCS)** that:
	- is compliant with the TDWG [Standards Documentation Standard](https://github.com/tdwg/vocab/tree/master/sds) and [Vocabulary Maintenance Standard](https://github.com/tdwg/vocab/tree/master/vms).
	- provides for the needs of the various types of users and use cases of Taxonomic Names in the biodiversity informatics space
	- as much as possible synthesises and takes benefit of the work that has been done in the TDWG community so far.

## Uses / Stakeholders

- Simple checklists, aggregators: GBIF, ALA, CoL; agitators: @rdmpage
- Species Information Systems
- Floras, Faunas etc.
- Systems that capture historical (as well as current) name usages: NSL, APNI, AFD
- Systems that try to capture phylogenetic relationships
- Entire TDWG community: everybody needs taxa for something

## Current standards

- [**Taxonomic Concept Transfer Schema (TCS)**](https://www.tdwg.org/standards/tcs/)
  - *TCS 1.01 Schema Documentation* can be found at http://tdwg.github.io/tcs/schema/1.01
- [**Darwin Core**](https://www.tdwg.org/standards/dwc/)
  - *Darwin Core* terms can be found at http://tdwg.github.io/dwc/terms/

## Issues

Expectation reversal, but

- Taxa **change**
  - AFD = taxonomic (opinion) product, not a Nomenclator, not a taxon store.
		- @rdmpage:  WTAF
  - Taxonomic Names are **stable.**
  - Inappropriate use of taxon.

No "Names" standard.

- Darwin Core RDF Guide recommends separate vocabulary.
  - Ad hoc Darwin Core extensions.
  - Inappropriate use of the taxonomic concept

TCS

- Application Schema rather than Standard
  - Designed to exchange with systems that look like TCS; not general information exchange
  - Interchange of literature based concept definitions
- Difficult to distill, harder to extend.
  - Syntax (XML) → path to RDF … JSON.
  - Over engineered for normal usage
  - Relationship object
    - Path to RDF, JSON-LD
  - How does tcs:TaxonConcept relate to dwc:Taxon?
  - How does tcs:TaxonConcept relate to NameUsage and nsl:Instance?

Darwin Core 

- Ambiguous wrt names
- Overloaded definitions
  - Many interpretations.
- Overloaded usage.
- Classification terms.
- Hybrids
- Ranks.
- Path to RDF

Many different application profiles
  - Simple vocabulary required.

A Domain Model?
  - Agreement on definitions
  - Code compliance
  - Contract -> Ontology

Open Linked Data ++
  - **Identifiers**
  - knowledge graph
  - RDF, JSON-LD
  - schema.org
  
Services
  - [REST](https://www.w3.org/TR/2004/NOTE-ws-arch-20040211/#relwwwrest) (*and [here](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)*)
  - [SHACL](https://www.w3.org/TR/shacl/), [GraphQL](https://graphql.org/learn/)

???

## Previous Work

   * **Bisby**
   * APNI
   * Berlin Model
   * IPNI
   * ITIS, CoL
   * Flora of Australia
   * Tropicos
   * LinneanCore (**SDD**)
   * **DwC**, **ABCD**
   * **TCS**
   * TDWG ontology
   * ALA-NSL (2008)
   * txn:deVriese
   * GBIF Checklist
   * **DwC RDF**
   * Nomen
   * WFO
   * OpenBiodiv
   * BCO
   * ColPlus
   * TaxRef
   * +++

## Strategy / Way Forward?

A new standard or update/replace/extend existing standards?

Restart with ideas in [**Linnean Core**](https://github.com/tdwg/tnc/blob/master/TDWG2018/linnean-core-definitions.md) (J.Cooper)
- A Basic vocabulary for the interchange and use of Taxonomic Names and "names".
- Darwin Core  extensions    NFB  < TCS.
- Controlled vocabularies!
- Recommend classes.
- Guidelines.

**Darwin Core Taxon** 
- leave "convenience" terms and internal links.
- remove external links (id terms) ?
- Add new terms?
- [Darwin Core RDF Guide](http://rs.tdwg.org/dwc/terms/guides/rdf/index.htm#2.6_Darwin_Core_ID_terms_and_RDF)

**A Domain Model or List?**
- Normative or Guide?
- API specification for:
	- Name
	- Instance (name occurrence) according
	- Usage ( potential/taxonomic concept)
	- Tree ?
	- Arrangement

## What are we looking for in a Name standard/vocabulary?
**(Core competencies / Functional Requirements / Use cases)**

- Generic metadata model
	- Vocabularies
- Full Code support
	- ICN, ICZN, ...
	- Code maintenance
		- Domain owners?
- Interoperability
  - Every name
  - Every instance (name usage)
  - Every relationship
  - Every point of view
  - Every version
  - Every syntax
  - Every application profile
  - Common interchange format
  - Support for publication
  - Extensible
- Obey the TDWG laws for standards and vocabularies
- Independent of serialization
- Concise vocabulary
- Linked Data
  -  Shared vocabulary
  -  Application Profiles
  -  Simple enough for …. Anything

## Terminology

**Some core "concepts"** [ToDo: do we need to include "taxon" concept and "taxon"?]

A **name** is a "name", a designation, a label, a string used as a name or in place of a name: in any context.

A **scientific name** a *name* formulated (or attempted to be) according to some rules of nomenclature; uni/bi/tri.nomial_name, author, [year]  

A **taxonomic name** is a *name* used in a taxonomic context, i.e. with a reference; often a *scientific name*.

A **reference** is a citable work: a publication, a resource, ... might be local.usage.

A **taxonomic name instance** is the occurrence of a name in a *reference*. A fact.  One use of a *taxonomic name* establishing context: establishment of a name, a concept, a synonym, an assertion, a relationship; tax. nov., comb.nov., … , a misapplication, or assertion; a common name.

A **taxonomic name usage** is a collection of *taxonomic name instances*,  establishing, annotating or describing a theory of a taxonomic entity - a *taxonomic concept* or *OTU* - often linking synonymic inclusions and adding annotations, description… 

- issue#1: [taxon concept vs concept label](https://github.com/tdwg/tnc/issues/1#issue-354177308)
 
A **taxonomic tree** is a hierarchical collection of selected, unique, *taxonomic name usages* -  a *taxonomy*.

A **taxonomic arrangement** or named tree is a collection of *taxonomic trees*. A classification, checklist, Flora or Fauna.

A **taxon** :

A **taxon concept** :

> **Note:** In a Names standard ‘scientific name’ is a type of taxonomic name rather than a property of a Taxon.

## Examples [todo]

[**OpenBiodiv-O**](https://static-content.springer.com/esm/art%3A10.1186%2Fs13326-017-0174-5/MediaObjects/13326_2017_174_MOESM1_ESM.txt)

  - https://github.com/pensoft/OpenBiodiv

[**Catalogue of Life Plus (CoL+)**](https://github.com/Sp2000/colplus)

[**TAXREF**](https://inpn.mnhn.fr/programme/referentiel-taxonomique-taxref)

  - https://github.com/frmichel/taxref-ld

[**NSL**](https://biodiversity.org.au/nsl)

https://github.com/bio-org-au

Bibliographic pattern:  Where a name is found and how it is used in that place.

  - Every taxonomic name instance.
    -Just about names and taxa:
      - Authors, References detail elsewhere -  external resources

## Model (sketch)

```
* Name
  * Name Strings
  * Code
  * Type of name (scientific, vernacular, informal, cultivar…)
  * Rank !
  * Status !
  * Authorship
  * Primary reference ( incl. basionym) !
* Reference
  * Type of reference !
  * Part of Reference !
  * dc:title, dc:creator, dc:created:...
  * CitedAs
  * External resource !
* Name Instance
  * Type of instance !
  * Name !
  * Reference !
  * Page citation
  * Citing instance !
  * Cited instance !
* Taxonomic tree
  * Instance !
  * Parent node !
  * Included nodes !
    * node !
      * node !
        * ...
  * Annotations
  * Profile
* Taxonomic arrangement
  * Root node!
    * node !
* Vocabularies
  * Code of Nomenclature
  * Status of a Name
    * Code !
    * Status
  * Type of Name
  * Type of Name Instance (usage/relationship)
  * The Ranks of Names
    * Code !
    * Rank
  * Type of Reference
  * Type of external Resource
  * Type of treenode
  * Type of arrangement
```

## Changes to Darwin Core?

Appropriateness
- RDF Guide
- "Convenience terms"

Extension of Darwin Core
- New/missing terms
- "Names" guide
- RDF Guide
- GBIF Checklist?

Cull Darwin core (TaxonConceptID)
