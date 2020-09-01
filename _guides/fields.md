---
layout: page
title: The Fields to use
---

These are the mandatory and recommended fields to use.

**Mandatory:** You must include this piece of data. These fields
should always be able to be populated.

**Encouraged** If there is a value that could be recorded for this
field it should be delivered if possible.

As there are a reasonably large number of them they are broken up into
the categories of the Darwin Core standard.

There is a link to the appropriate standard beside each field (when it
comes from a standard). A description is only added where further
clarity is needed over what's in the appropriate standard.

Note that in fields where it might be appropriate to include multiple
entries they should be separated with a `|`. For example when a
specimen has multiple associated field numbers the recordNumber entry
should be delivered like: `A13|eob655`

## Record-level

### Mandatory

{% include fields.html mandatory="mandatory" category="Record-level" %}

### Encouraged

{% include fields.html mandatory="optional" category="Record-level" %}

## Occurrence

### Mandatory

{% include fields.html mandatory="mandatory" category="Occurrence" %}

### Encouraged

{% include fields.html mandatory="encouraged" category="Occurrence" %}

## Organism

### Mandatory

{% include fields.html mandatory="mandatory" category="Organism" %}

### Encouraged

{% include fields.html mandatory="encouraged" category="Organism" %}