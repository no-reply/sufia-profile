---
title: Sufia Basic Metadata 
author: Tom Johnson
date: 2016-12-05
profile:
  organization: 
  project: Sufia Hosting
  namespaces:
    dce:    http://purl.org/dc/elements/1.1/
    dct:    http://purl.org/dc/terms/
    edm:    http://www.europeana.eu/schemas/edm/
    fcr:    info:fedora/fedora-system:
    foaf:   http://xmlns.com/foaf/0.1/
    mrel:   http://id.loc.gov/vocabulary/relators/
    pcdm:   http://pcdm.org/models#Object
    premis: http://www.loc.gov/premis/rdf/v1#
    rdfs:   http://www.w3.org/2000/01/rdf-schema#
    sufia:  http://scholarsphere.psu.edu/ns#
    sweet:  http://sweet.jpl.nasa.gov/2.2/reprDataFormat.owl#
    works:  http://pcdm.org/works#
    xsd:    http://www.w3.org/2001/XMLSchema#
    
---

# Sufia Basic Metadata (DCE)

## Model

This model is a formalization of the [PCDM Application Profile](https://github.com/duraspace/pcdm/wiki) and its [Hydra Works Extension](https://github.com/duraspace/pcdm/wiki/Works-Extension) as deployed in hosted Sufia solutions provided by _Data Curation Experts_.

![Drawing of model](https://raw.githubusercontent.com/wiki/duraspace/pcdm/images/coll-object-file.png)
![Ordering construction](https://raw.githubusercontent.com/wiki/duraspace/pcdm/images/ore-ordering-extension.png)

### `pcdm:Collection`

#### Descriptive

| Field              | Predicate                   | Recommendation | Expected Value                        | Obligation |
| ------------------ | --------------------------- | -------------- | ------------------------------------- | ---------- |
| *title*            | `dct:title`                 | MUST           | `xsd:string`                          | {1}        |

#### Provenance

| Field            | Predicate                | Recommendation | Expected Value                       | Obligation |
| ---------------- | ------------------------ | -------------- | ------------------------------------ | ---------- |
| *date modified*  | `dct:modified`           | MUST           | `xsd:dateTime`                       | {1}        |
| *date uploaded*  | `dct:dateSubmitted`      | MUST           | `xsd:dateTime`                       | {1}        |
| *depositor*      | `mrel:dpt`               | MUST           | `xsd:string` ??                      | {1}        |
| *import url*     | `sufia:importUrl`        | MUST           | `xsd:string`                         | {1}        |
| *label*          | `fcr:downloadFilename`   | MUST           | `xsd:string`                         | {1}        |
| *relative path*  | `sufia:relativePath`     | MUST           | `xsd:string`                         | {1}        |

### `works:Work < pcdm:Object`

#### Descriptive

| Field              | Predicate                   | Recommendation | Expected Value                        | Obligation |
| ------------------ | --------------------------- | -------------- | ------------------------------------- | ---------- |
| *title*            | `dct:title`                 | MUST           | `xsd:string`                          | {1}        |
| *creator*          | `dce:creator`               | SHOULD         | `xsd:string`                          | {0,n}      |
| *rights statement* | `edm:rights`                | SHOULD         | `dct:RightsStatement` (`xsd:string`?) | {0,n}      |
| *date created*     | `dct:created`               | SHOULD         | `xsd:date` or `xsd:dateTime`          | {0,n}      |
| *based near*       | `foaf:basedNear`            | MAY            | `xsd:string`                          | {0,n}      |
| *citation*         | `dct:bibliographicCitation` | MAY            | `xsd:string`                          | {0,n}      |
| *contributor*      | `dce:contributor`           | MAY            | `xsd:string`                          | {0,n}      |
| *description*      | `dce:description`           | MAY            | `xsd:string`                          | {0,n}      |
| *identifier*       | `dct:identifier`            | MAY            | `xsd:string`                          | {0,n}      |
| *keyword*          | `dce:relation`              | MAY            | `xsd:string`                          | {0,n}      |
| *language*         | `dce:language`              | MAY            | `xsd:string`                          | {0,n}      |
| *publisher*        | `dce:publisher`             | MAY            | `xsd:string`                          | {0,n}      |
| *related url*      | `rdfs:seeAlso`              | MAY            | `xsd:string` or `xsd:anyURI`          | {0,n}      |
| *rights*           | `dct:rights`                | MAY            | `dct:RightsStatement` (`xsd:string`?) | {0,n}      |
| *source*           | `dct:source`                | MAY            | `xsd:string`                          | {0,n}      |
| *subject*          | `dce:subject`               | MAY            | `xsd:string`                          | {0,n}      |


#### Provenance

| Field            | Predicate                | Recommendation | Expected Value                       | Obligation |
| ---------------- | ------------------------ | -------------- | ------------------------------------ | ---------- |
| *date modified*  | `dct:modified`           | MUST           | `xsd:dateTime`                       | {1}        |
| *date uploaded*  | `dct:dateSubmitted`      | MUST           | `xsd:dateTime`                       | {1}        |
| *depositor*      | `mrel:dpt`               | MUST           | `xsd:string` ??                      | {1}        |
| *import url*     | `sufia:importUrl`        | MUST           | `xsd:string`                         | {1}        |
| *label*          | `fcr:downloadFilename`   | MUST           | `xsd:string`                         | {1}        |
| *relative path*  | `sufia:relativePath`     | MUST           | `xsd:string`                         | {1}        |

### `works:FileSet < pcdm:Object`

| Field              | Predicate                   | Recommendation | Expected Value                        | Obligation |
| ------------------ | --------------------------- | -------------- | ------------------------------------- | ---------- |
| *title*            | `dct:title`                 | MUST           | `xsd:string`                          | {1}        |
| *creator*          | `dce:creator`               | SHOULD         | `xsd:string`                          | {0,n}      |
| *rights statement* | `edm:rights`                | SHOULD         | `dct:RightsStatement` (`xsd:string`?) | {0,n}      |
| *date created*     | `dct:created`               | SHOULD         | `xsd:date` or `xsd:dateTime`          | {0,n}      |
| *based near*       | `foaf:basedNear`            | MAY            | `xsd:string`                          | {0,n}      |
| *citation*         | `dct:bibliographicCitation` | MAY            | `xsd:string`                          | {0,n}      |
| *contributor*      | `dce:contributor`           | MAY            | `xsd:string`                          | {0,n}      |
| *description*      | `dce:description`           | MAY            | `xsd:string`                          | {0,n}      |
| *identifier*       | `dct:identifier`            | MAY            | `xsd:string`                          | {0,n}      |
| *keyword*          | `dce:relation`              | MAY            | `xsd:string`                          | {0,n}      |
| *language*         | `dce:language`              | MAY            | `xsd:string`                          | {0,n}      |
| *publisher*        | `dce:publisher`             | MAY            | `xsd:string`                          | {0,n}      |
| *related url*      | `rdfs:seeAlso`              | MAY            | `xsd:string` or `xsd:anyURI`          | {0,n}      |
| *rights*           | `dct:rights`                | MAY            | `dct:RightsStatement` (`xsd:string`?) | {0,n}      |
| *source*           | `dct:source`                | MAY            | `xsd:string`                          | {0,n}      |
| *subject*          | `dce:subject`               | MAY            | `xsd:string`                          | {0,n}      |

### `pcdm:File`

| Field            | Predicate                 | Recommendation | Expected Value                       | Obligation |
| ---------------- | ------------------------- | -------------- | ------------------------------------ | ---------- |
| *label*          | `rdfs:label`              | MUST           | `xsd:string`                         | {1}        |
| *file name*      | `ebu:filename`            | MUST           | `xsd:string`                         | {1}        |
| *file size*      | `ebu:fileSize`            | MUST           | `xsd:string` ??                      | {1}        |
| *date created*   | `ebu:dateCreated`         | MUST           | `xsd:dateTime` ??                    | {1}        |
| *date modified*  | `ebu:dateModified`        | MUST           | `xsd:dateTime` ??                    | {1}        |
| *byte order*     | `sweet:byteOrder`         | MUST           | ??                                   | {1}        |
| *file hash*      | `premis:hasMessageDigest` | MUST           | `xsd:string` ??                      | {1}        |

## Usage

...

## To Do:

  - Change *description* from DC Elements `dce:description` to DC Terms `dct:description`.
  - Use a better term for *keyword* than `dce:relation`.
  - Resolve *rights*. Should this be a `dct:RightsStatement` entity?
  - Clarify practice around edm and dct rights terms
  - For *based near*, the range of `foaf:based_near` is `foaf:SpatialThing`. Fix this!
  - Consider fixing *related url* to use `xsd:anyURI`.
  - Refactor `curation_concerns` to use `ActiveTriples::Schema` for cleaner overrides.
  
