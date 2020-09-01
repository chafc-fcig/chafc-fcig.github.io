---
layout: page-with-toc
title: Sharing tissue data with the ALA
---


Introduction
============

The Museums of Australia have been delivering data relating to their
collections of biological specimens to the ALA for a number of years.
Increasingly institutions are wanting to also send data relating to
collections of tissue samples. This document is a guide on how that
should be done

This guide assumes that you are delivering your data as a simple Darwin
Core CSV. If you are in fact delivering a Darwin Core Archive or other
format the adaptation of this guide to your needs should be
straightforward.

This document will simply outline the column headings which should be
used as well as what data should be put in each column.

Standards such as Darwin Core tend not to be very proscriptive and allow
a lot of freedom around how data should be structured. This document
will be more proscriptive, outlining the decisions which Australian
Museums delivering data to the Atlas of Living Australia have reached
regarding how we should coordinate our efforts.

Basic requirements
------------------

For a tissue sample extra information is required in addition to what is
required to deliver occurrence data. This description will assume that
your institution is already delivering occurrence data for specimens,
delivered using the Darwin Core standard - most likely as a Simple
Darwin Core CSV.

The necessary data related to tissue samples is very similar to that
required for preserved specimens but with a few extra details.

The necessary things to know are:

(Voucher = the source animal from which the tissue sample was taken

-   What taxon the voucher specimen was
-   Whether the voucher is still extant
-   If the voucher *is* still extant, where it can be found
-   The collection information relating to the voucher (location, date
    and collector)
-   What type of tissue the sample is: muscle, liver etc.
-   How the tissue sample has been stored, including temperature
-   Permit information

One tissue = one record
-----------------------

When delivering data each tissue sample must be delivered as a single
record.

Permit information
------------------

Information relating to the permit has become important as a result of
the Nagoya Protocol. There is not space in this document to explain the
Protocol in detail, we will just outline what data you are required to
deliver.

GGBN standard
-------------

We draw from the Data Standard created by the Global Genome Biodiversity
Network for the representation of 'tissue, DNA or RNA samples associated
to voucher specimens, tissue samples and collections'. The [GGBN
standard](https://wiki.ggbn.org/ggbn/GGBN_Data_Standard_v1) is designed
to be used in combination with Darwin Core or ABCD.

When we deliver data to the ALA we use Darwin Core, with most
institutions delivering their data as a [Simple Darwin Core
CSV](https://dwc.tdwg.org/simple/). Data delivered relating to tissue
samples should contain the base standard columns that have been agreed
for the delivery of biological specimen data. This document outlines the
extra columns in addition to those.

To indicate that the data in a particular column is from the GGBN
standard the column header should be preceeded with 'ggbn:', for example
`ggbn:blocked`.

Unlike Darwin Core the GGBN standard does have mandatory fields. The
description will begin with them.

GGBN fields - the tissue sample
===============================

{% include fields.html mandatory="mandatory" category="Material Sample" %}


The Voucher
===========

As well as the information about the tissue sample you also need to
deliver information about the voucher specimen from which the tissue
sample was taken.

If the voucher is still extant and is held in a Museum collection
deliver, for the voucher:

-   The institutionCode
-   The collectionCode
-   The catalogNumber

There isn't an official Darwin Core standard way to deliver this
information so deliver these three fields separated with a ':' in a
single column. 

Call this column `relatedResourceCatalogNumber`

``` 
SAMA:Mammalogy:M1322
```

If you don't know any of the elements leave them out:

If you only know the institution and collection:

``` 
SAMA:Mammalogy:
```
If you only know the institution:
``` 
SAMA::
```

This field is used to construct a URL that gets inserted into the
record to provide a link back to the voucher.

Also add a column calld `relationshipOfResource` with the value `same
individual` to show that the tissue came from the specimen linked as a
voucher.
