---
layout: page-with-toc
title: The Fields to use
---

These are the mandatory and recommended fields to use.

**Mandatory:** You must include this piece of data. These fields
should always be populated.

**Encouraged** If there is a value that could be recorded for this
field it should be delivered if possible.

As there are a reasonably large number of them they are broken up into
the categories of the Darwin Core standard.

Click on the field name to go to it in the appropriate standard (when
it comes from a standard). 

A description is only added where further
clarity is needed over what's in the appropriate standard.

## Multiple values

Note that in fields where it might be appropriate to include multiple
entries they should be separated with a `|`. For example when a
specimen has multiple associated field numbers the recordNumber entry
should be delivered like: `A13|eob655`

{% assign categories = "Record-level,Occurrence,Organism" | split: ',' %}


## Mandatory

You must deliver this set of fields for every record.

Every field designated as mandatory must have a valid value.

{% for cat in categories %}

### {{cat}}

{% include fields.html mandatory="mandatory" category=cat %}

{% endfor %}

## Encouraged

It is strongly encouraged that you send these fields.

Every field designated as encouraged must have a valid value if one is known.

{% for cat in categories %}

### {{cat}}

{% include fields.html mandatory="encouraged" category=cat %}

{% endfor %}

