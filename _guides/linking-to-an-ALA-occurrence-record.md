---
title: Linking to an ALA occurrence record
layout: page-with-toc
---

# ALA Occurrence Records #

When we are delivering data to the ALA we are delivering occurrence
records, indicating the occurrence of a particular organism in a
particular location at a particular time. 

On occasion you may wish for a record to include a relationship with
another occurrence record. You can do this by inserting the URL for
the related occurrence record in an appropriate field.

As you are constructing an actual URL you can test that you are
structuring it correctly by opening it in a browser. When followed the
URL should bring you directly to the specified occurrence record.

In the following replace the bits with [square brackets] with the
appropriate piece of data. Do not include the square brackets.

## Occurrence record URL ##

The URL to a resource on the ALA has the following structure:

```
<a href="https://biocache.ala.org.au/occurrences/search?q=institution_code:"[institutionCode]" AND collection_code:"[collectionCode]" AND catalogue_number:"catalogue_number">[institutionCode]:[collectionCode]:[catalogueNumber]</a>
```


Broken up to make it easier to read:

`<a href="https://biocache.ala.org.au/occurrences/search?q=`

`institution_code:"[institutionCode]"`

` AND collection_code:"[collectionCode]"`

` AND catalogue_number:"[catalogueNumber]">`

`[institutionCode]:[collectionCode]:[catalogNumber]`

`</a>`

Broken up and HTML encoded like you'd probably use for building the
string:

```
<a href="https://biocache.ala.org.au/occurrences/search?q=institution_code:%22[institutionCode]%22%20AND%20collection_code:%22[collectionCode]%22%20AND%20catalogue_number:%22[CatalogueNumber]%22">source specimen: [institutionCode]:[collectionCode]:[catalogNumber]</a>
```

So you would construct the string with something like:

```
var baseUrl = "<a href=\"https://biocache.ala.org.au/occurrences/search?q=";

var institution = "institution_code:%22" + institutionCode + "%22"
var collection = "collection_code:%22" + collectionCode + "%22"
var catalogue = "%20catalogue_number:%22" + catalogueNumber + "%22"

var voucherUrl = baseUrl 
	+ institution
	+ "%20AND%20"
	+ collection
	+ "%20AND%20"
	+ catalogue
	+ "%22\">source specimen " 
	+ institutionCode + ":" + collectionCode + ":" + catalogueNumber 
	+ "</a>";


```



### Collection or institution URL ###

If you need to create a link that is broader - if the information you
have about the associated occurrence is incomplete - truncate the URL
so that it only contains the information that you are sure of.

If you open the URL in a browser when testing you should be brought to
all of the records for the indicated collection or institution.

If you only know the Collection:


```
<a href="https://biocache.ala.org.au/occurrences/search?q=institution_code:%22[institutionCode]%22%20AND%20collection_code:%22[collectionCode]%22">[institutionCode]:[collectionCode]</a>
```


If you only know the Institution:

```
<a href="https://biocache.ala.org.au/occurrences/search?q=institution_code:%22[institutionCode]%22">[institutionCode]</a>
```

{% highlight shell %}

institutionCode = # Get the institution code from your data
collectionCode = # Get the collection code from your data
catalogueNumber = # Get the catalogue number from your data

baseUrl = "<a href=\"https://biocache.ala.org.au/occurrences/search?q="

institution = "institution_code:%22$institutionCode%22"
collection = "collection_code:%22$collectionCode%22"
catalogue = "catalogue_number:%22$catalogueNumber%22"

if [collectionCode != ''] 
then
	voucherUrl += "%20AND%20$collection"
fi
if [catalogueNumber != ''] 
then
	voucherUrl += "%20AND%20$catalogue"
fi

end_of_Url = "\">source specimen $institutionCode:$collectionCode:$catalogueNumber</a>"

voucherUrl += end_of_Url;
{% endhighlight %}
