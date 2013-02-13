# Letterbomb.

An easy to use static blog generator that wants to get out
of the way. Posts are written in [Markdown](http://daringfireball.net/projects/markdown/syntax) 
and inserted into HTML templates. Use the defaults or create
your own. Metadata and template selection are handled
within the entry using a specially formatted header. With
styles and templates kept separate, writing new posts is
designed to be easy.

## Usage

Requires [Pandoc](http://johnmacfarlane.net/pandoc/) to
convert Markdown to HTML.

Given a input directory containing posts written in
Markdown, output the generated site to the `./html` directory:

~~~
$ letterbomb -i ./posts -o ./html
~~~

Letterbomb includes a collection of default templates, or,
if you'd like, use additional ones or override the
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

OSX requires a more recent version of bash
(associative-array support). If using [Homebrew](http://mxcl.github.com/homebrew/),
you can upgrade like so:

~~~
$ brew install bash
$ sudo bash -c "echo /usr/local/bin/bash" >> /etc/shells
$ chsh -s /usr/local/bin/bash
~~~

If you're looking for a good (and free) web hosting for
static pages, checkout the
[GitHub Pages](http://pages.github.com/) feature.
