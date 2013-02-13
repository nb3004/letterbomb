# Letterbomb.

An easy to use static blog generator that wants to get out
of the way. Leveraging the awesomeness of
[Pandoc](http://johnmacfarlane.net/pandoc/README.html),
posts can be written in your favorite document markup style,
including [Markdown](http://daringfireball.net/projects/markdown/syntax),
[Textile](http://redcloth.org/textile), and [LaTeX](http://www.latex-project.org/).
These posts are inserted into templates which are customized
using plain old HTML and CSS. Metadata and template
selection can be set per post using a specially formatted
header. With content, templates, and styles kept separate,
writing new creating new posts and maintaining your site is
designed to be easy.

## Usage

First, install [Pandoc](http://johnmacfarlane.net/pandoc/)
to generate the HTML.

Given a input directory containing posts written in
Markdown, output the generated site to the `./html` directory:

~~~
$ letterbomb -i ./posts -o ./html
~~~

Letterbomb includes a collection of default templates, or,
if you'd like, add additional ones to override the
defaults. Just specify a directory containing user
templates:

~~~
$ letterbomb -i ./posts -o ./html -t ./mytemplates
~~~

If a template is not found among these, Letterbomb will
check the default templates next. If it still can't find it,
you'll get an error message.

*Note:* When Letterbomb looks in your posts directory, readme
files and any files/directories that start with a period or
underscore are ignored and not copied to the destination folder.

## Metadata

Metadata and template selection are specified in the header
of an entry which is used to generate the appropriate
HTML. Any line that starts with `%%` will be striped, and
metadata can be added to an HTML document by including
key/value pairs in your file:

~~~
%% title: This is a Title
%% date: Feb. 7, 2013
%% template: photo
~~~

Here, the `title` property sets the `<title>` element of
the document, and `template` chooses which HTML template to
use. If a template is not specified, then the post will be
inserted into the `default.html` template.

Additional key/value pairs are inserted into the generated
document as `<meta>` tags.

## TODO

* Lots!
* Better index
* Non-test templates
* Generate rss feed

## Notes

If you're looking for a good (and free) web hosting for
static pages, checkout the
[GitHub Pages](http://pages.github.com/) feature.
