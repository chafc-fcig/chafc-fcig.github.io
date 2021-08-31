---
layout: page
title: Sharing data with the ALA
parent: Guides
---

## Introduction ##

The Collecting Institutions of Australia have collectively decided to
share their biological specimen data with the world through the Atlas of
Living Australia (ALA).

This document is a guide to how to select and format data from an
institution's collections management database and deliver it to the ALA.

If we describe things in as identical a manner as possible then the data
can be more useful as it will be seamlessly aggregate with the rest of
the Distributed National Faunal Collection.

## Standards

### Darwin Core

<https://dwc.tdwg.org/terms/>

How you store and structure data within your institution is a matter for
each institution, but when you send it to be aggregated it needs to be
structured and described according to the standard.

The main standard we use is Darwin Core.

The main Darwin Core (DwC) standard describes an XML standard with
multiple interrelated XML files bound up in a zip file called a Darwin
Core Archive file. If this is the route you want to go down you might be
best off with an installation of the Integrated Publishing Toolkit:
<https://www.gbif.org/ipt>. Configuration of the IPT and the intricacies
of Darwin Core Archives are an exercise left for the reader.

The most straightforward way to use Darwin Core is to send data in a CSV
file, described within the standard as a Simple Darwin Core CSV.
<https://dwc.tdwg.org/simple/>

Most Australian Institutions deliver their data to the ALA in this
manner, which is a CSV with specified column headers and the data
structured in a standardised ways.

We use the appropriate Darwin Core term as the header for the column and
structure the data as defined in the Darwin Core standard. As the DwC
standard is not very prescriptive for some fields we have decided a
standard Australian practice to allow our data to be more useful in
aggregate.

Note that there are no mandatory field in Darwin Core

### Dublin Core

Dublin Core is a metadata standard used for the description of
electronic resources. We use them within Darwin Core to describe the
electronic resource of the Darwin Core data itself. Things like when the
data was last updated and details about the rights and license assigned
to the data.

To distinguish Dublin Core terms from Darwin Core terms those fields
which contain data as proscribed by Dublin core have 'dcterms:' in front
of their header, i.e. 'dcterms:\[column name\]', e.g. dcterms:type. This
makes it immediately evident that this particular field is from a
different standard.

(In XML terms, dcterms: indicates a different name-space. When providing
XML data Darwin core terms should be proceeded with dwc: and both
name-spaces declared in the root element)

### GGBN

The Global Genome Biodiversity Network (GGBN) standard is a set of
vocabularies designed to represent tissue, DNA or RNA samples associated
to voucher specimens, tissue samples and collections.

The Council of Heads of Australian Faunal Collections (CHAFC) have
decided that GGBN can harvest tissue and related data from the Atlas of
Living Australia and individual institutions will not be providing data
on-by-one.

As with Dublin Core terms, fields which are being provided within the
GGBN standard should have their name-space included in the column
header, i.e. 'ggbn:\[column name\]', e.g ggbn:materialSampleType

The GGBN standard has a small number of mandatory fields, described
below in the appropriate, *\*MaterialSample*, section

The GGBN standard has both mandatory and optional fields

The mandatory fields are:

  - ggbn:materialSampleType
  - ggbn:preparationDate
  - ggbn:preparationType
  - ggbn:preservationType
  - ggbn:permitType
  - ggbn:permitStatus

## ALA agreed fields

While the previously mentioned standards are very comprehensive there is
also the occasional bit of information which a Museum we wants to
provide to the ALA but which is not addressed within the general
standards. The ALA can still recieve that data.

## FCIG-agreed practices

The Darwin Core standard is not very prescriptive of how data should be
delivered within individual fields.

To facilitate consistency across Australian Museums the Faunal Council
Informatics Group have converged on a shared approach for the delivery
of data. This share approach is here recorded for reference and to
assist new institutions which may want to begin sharing their data or
adjust their data practices to match those of the rest of the country

Up to this time the convergence has been reached through informal
discussion. This site is an attempt to formalise these data
practices.
