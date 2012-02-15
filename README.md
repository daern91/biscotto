# Codo [![Build Status](https://secure.travis-ci.org/netzpirat/codo.png)](http://travis-ci.org/netzpirat/codo.png)

Codo is a CoffeeScript API documentation generator, similar to [YARD](http://yardoc.org/). It's generated documentation
is focused on CoffeeScript class syntax for classical inheritance and not for JavaScript's prototypal inheritance.

## Installation

Codo is not released yet. Watch this repo and follow [@netzpirat](http://twitter.com/#!/netzpirat) to get notified
when Codo is ready!

## Supported documentation tags

Codo comments are rendered as [GitHub Flavored Markdown](http://github.github.com/github-flavored-markdown/)
and can be tagged to add more structured information to class and method comments.

### Class and method tags

#### @private

Marks a method or class as private:

```CoffeeScript
 # @private
 class Renderer

   # @private
   detectEngine: ->
```

#### @abstract

Marks a class or method as abstract.

```CoffeeScript
 # @abstract
 class Listener

   # @abstract
   listen: ->
```

### @deprecated

Marks a class or method as deprecated. You can optionally describe the deprecation reason.

```CoffeeScript
 # @deprecated Use Stripe
 class PayPal

   # @deprecated
   pay: ->
```

### @version

Set the current version of a class or method:

```CoffeeScript
 # @version 1.0.9
 class Watcher

   # @version 1.0.9
   watch: ->
```

### @since

Set the version when the class or method was first added:

```CoffeeScript
 # @since 1.0.2
 class Codo

   # @since 1.0.3
   parse: ->
```

### @example

Add your open tasks to a class or method. You can provide an optional example title on the same line as the tag and
you can specify this tag multiple times.

```CoffeeScript
 # @example
 #   adapter = Adapter.detect()
 #   adapter.start()
 #
 # @example Get adapter for a specific OS
 #   adapter = Adapter.for('darwin')
 #   adapter.start()
 #
 class Adapter

   # @example
   #   adapter = Adapter.detect()
   #   adapter.stop()
   stop: ->
```

### @todo

Add your open tasks to a class or method. You can specify this tag multiple times.

```CoffeeScript
 # @todo Refactor to use the new mailer library
 # @todo Cleanup handlers
 class Mailer

   # @todo Enable TLS
   send: ->
```

### @note

Add your open tasks to a class or method. You can specify this tag multiple times.

```CoffeeScript
 # @note This class is thread safe
 class SocketPool

   # @note Make sure the backend is running
   connect: ->
```

### @author

Marks a class or method as written by a specific author. You can specify this tag multiple times.

```CoffeeScript
 # @author Mickey Mouse
 # @author Donald Duck
 class Cartoon

   # @author Mickey Mouse
   play: ->

   # @author Donald Duck
   wait: (seconds) ->
```

## Generate documentation

After the installation you will have a `codo` binary that can be used to generate the documentation recursively for all
CoffeeScript files within a directory.

```bash
$ codo --help
Usage: codo [options] [source_files [- extra_files]]

Options:
  -r, --readme      The readme file used.  [default: "README.md"]
  -q, --quiet       Show no warnings.      [boolean]  [default: false]
  -o, --output-dir  The output directory.  [default: "./doc"]
  -g, --github      The GitHub repository. [default: ""]
  -h, --help        Show the help.
  --private         Show private methods
  --title                                  [default: "CoffeeScript API Documentation"]
```

### Project defaults

You can define your project defaults by write your command line options to a `.codoopts` file:

```bash
 --readme     README.md
 --title      "Codo Documentation"
 --private
 --quiet
 --output-dir ./doc
 ./src
 -
 LICENSE
 CHANGELOG.md
```

## Development

- Source hosted at [GitHub](https://github.com/netzpirat/codo).
- Issues hosted at [GitHub Issues](https://github.com/netzpirat/codo/issues).

Pull requests are very welcome! Please try to follow these simple rules if applicable:

* Please create a topic branch for every separate change you make.
* Make sure your patches are well tested.
* Update the documentation.
* Update the README.
* Update the CHANGELOG for noteworthy changes.
* Please **do not change** the version number.

## Acknowledgment

- [Jeremy Ashkenas](https://github.com/jashkenas) for [CoffeeScript][], that little language that compiles into
JavaScript and makes me enjoy JavaScript development.
- [Loren Segal](https://github.com/lsegal) for creating YARD and giving me the perfect documentation syntax for
dynamic programming languages.

## Alternatives

* [Docco](http://jashkenas.github.com/docco/) is a quick-and-dirty, literate-programming-style documentation generator.
* [CoffeeDoc](https://github.com/omarkhan/coffeedoc) an alternative API documentation generator for CoffeeScript.
* [JsDoc](https://github.com/micmath/jsdoc) an automatic documentation generator for JavaScript.
* [Dox](https://github.com/visionmedia/dox) JavaScript documentation generator for node using markdown and jsdoc.

## Author

* [Michael Kessler](https://github.com/netzpirat) ([@netzpirat](http://twitter.com/#!/netzpirat))

Development is sponsored by [mksoft.ch](https://mksoft.ch).

## License

(The MIT License)

Copyright (c) 2012 Michael Kessler

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.