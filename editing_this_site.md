---
layout: default 
title: Editing this site 
nav_order: 4 
---

# Editing this site

The files making up this site live on Github at
https://github.com/chafc-fcig/chafc-fcig.github.io

The site is made from a bunch of text files on that site that any member of
FCIG has permission to edit or delete. They also have permission to create new
files or to change any aspect of the site. 

The site is created from the plain text files using a static site generator
which turns the text files from
https://github.com/chafc-fcig/chafc-fcig.github.io into a website which then
'lives' at https://chafc-fcig.github.io/. The end result is an easy to maintain
and edit website without having to worry about web servers, HTML, hosting or
any of that stuff.

The technique is odd at first but if you just ignore all the workings it's
reasonably quick and intuitive to edit existing files or create new ones. The
technical aspects of everything are irrelevant for just writing text.

## Markdown

All the files are written using Markdown, plain text files with minimal extra
characters to denote formatting or structure. [Mastering
Markdown](https://guides.github.com/features/mastering-markdown/) gives a quick
overview of Markdown.

## Jekyll

This page has been created using [Jekyll](https://jekyllrb.com) - if you are
experienced at using Jekyll and can help out with that it would be appreciated.

## Just the docs

I'm not great at css and suchlike so to make the pages look nice I have used
the [Just the docs](https://github.com/pmarsceill/just-the-docs) Jekyll theme.
This gives a nice appearance to the site and builds a reasonable navigation on
the left-hand side.

## Github-pages

Hosting the page on github pages avoids worrying about hosting charges and
infrastructure. I also allows using Jekyll to build the site automatically from
the text so _hopefully in theory_ it's easy to edit...

# Editing on github

If you are a member of FCIG you have editing access to the repository that is
used to build this site. That means you can go to
https://github.com/chafc-fcig/chafc-fcig.github.io and edit the files there and
those changes will be propagated across to this website once you save your
edits. 

Before doing any editing it might help to compare this page you're looking at
now with [the text file used to generate
it](https://github.com/chafc-fcig/chafc-fcig.github.io/blob/master/editing_this_site.md)

## Structure of the site

If you see on the left-hand side there are a number of pagesL About and How to
edit this site (this document). Files in the main folder of the source site
will appear in the lowest level of the structure.

There are also two folders in the navigation: Guides and Discussions. They
relate to folders in the source site:
[Guides](https://github.com/chafc-fcig/chafc-fcig.github.io/tree/master/guides)
and
[discussions](https://github.com/chafc-fcig/chafc-fcig.github.io/tree/master/discussions)

There is also a file in the `_data` folder which contains the file
`fields.yaml` which contains the list of Darwin Core fields that gets used in
one or two of the guides.

You can safely ignore all the other pages and folders. They are mostly used for
Jekyll, to configure and create the website.

## To edit a page

See the [instructions on
GitHub](https://docs.github.com/en/github/managing-files-in-a-repository/managing-files-on-github/editing-files-in-your-repository)

1. Click on the little edit pencil logo 2. Edit the page as required 3. Save
the page by "Committing" your changes - you have to write in a small
description of the changes you made (that's a thing you have to do when using
git (which keeps track of file changes))

That's it :)

## To create a new page

See the [instructions on
GitHub](https://docs.github.com/en/github/managing-files-in-a-repository/managing-files-on-github/creating-new-files)

# Editing on your own computer

For most users it will be far more convenient to edit on GitHub rather than
download the site and edit it on your own computer. But if you want to it is an
option. I'm assuming that if you're looking to edit the site on your own
computer you're familiar with getting things like that to work.

In short:

1. If you want to preview the site get Ruby and Jekyll working 2. Clone the
repository to your computer 3. Edit as you want 4. Commit the edits 5. Push the
edits back to Github

## Things to watch

If you want to run Jekyll locally to confirm that the changes are working as
you want before committing and pushing them back there are a few things to
watch.

Github pages jekyll sites use the github-pages gem rather than the jekyll gem.
Consequently you need to ensure that you use ruby 2.7. Your OS will probably
have a more recent version so you should use RVM to make sure you can use 2.7

If you use RVM to install the version of Ruby you want but Jekyll still isn't
working - if your shell isn't finding the RVM version of Ruby it might help to
enter `bash --login` to get a login shell (I'm not sure what the different is
but it worked for me, I'm currently using Arch Linux)

# Editing the fields data page

Describing the different fields to use requires recording a reasonably detailed
amount of structured information.

The 'easiest' way to do this would be to use a csv file, but that brought up
problems with recording multiple examples and with being able to edit the file
in the browser.

So the information has been recorded in a YAML file which gets processed after
saving into a few tables that get built on the fields to use page.

To add another field just copy one of the existing ones and put it on the end.
I think the YAML format used is reasonably self-explanatory if you refer to the
existing records. Just be pedantic about copying the exact punctuation and
indentation and it should be fine. 

The HTML tables on that page are created using the templates on the page
[includes/fields.html](https://github.com/chafc-fcig/chafc-fcig.github.io/blob/master/_includes/fields.html).
The templates on the markdown page
[fields.md](https://github.com/chafc-fcig/chafc-fcig.github.io/blob/master/_guides/fields.md)
create a different table for each category. You can see from the templates that
the structure is simply iterating over the YAML file and so the tables can be
structured however is needed to explain things best. 


