## Prelude

The goal of this guide is to present a set of best practices and coding style idioms for bash shell scripting. The style guide is inspired by [Eloquent Ruby](http://amzn.to/1ZLu9PE), the [The Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide) and the elegant syntax of the ruby programming language.

> Nobody really knows what the Bourne shell's grammar is.  
> Even examination of the source code is little help.  
> -- Tom Duff

## The AJAlabs Bash Scripting Style Guide

The AJAlabs bash scripting style guide recommends best practices so that real-world IT professionals and bash programmers can write code that can be maintained by other real-world professionals and programmers. A style guide that reflects real-world usage gets used, and a style guide that holds to an ideal that has been rejected by the people it is supposed to help risks not getting used at all – no matter how good it is.

The guide is separated into several sections of related rules. I've tried to add the rationale behind the rules (if it's omitted I've assumed it's pretty obvious).


### Table of Contents

* [Source Code Layout](#source-code-layout)
* [Syntax](#syntax)
* [Naming](#naming)
* [Comments](#comments)
* [Resources](#resources)

### Source Code Layout

> Nearly everybody is convinced that every style but their own is
> ugly and unreadable. Leave out the "but their own" and they're
> probably right... <br>
> -- Jerry Coffin (on indentation)

* <a name="utf-8"></a>
  Use `UTF-8` as the source file encoding.
<sup>[[link](#utf-8)]</sup>

* <a name="shebang"></a>
  Always use a [portable](https://en.wikipedia.org/wiki/Shebang_%28Unix%29#Portability) shebang on the first line of your script.
<sup>[[link](#shebang)]</sup>

  ```bash
  # bad - absolute path
  #!/bin/bash

  # good
  #!/usr/bin/env bash

  ```

* <a name="spaces-indentation"></a>
  Use two **spaces** per indentation level (aka soft tabs). No hard tabs.
<sup>[[link](#spaces-indentation)]</sup>

  ```bash
  # bad - four spaces
  if [ "foo" = "foo" ]; then
      do_something
  else
      do_something_else
  fi

  # good
  if [ "foo" = "foo" ]; then
    do_something
  else
    do_something_else
  fi
  ```

* <a name="crlf"></a>
  Use LF Unix-style line endings. (*BSD/Solaris/Linux/OS X users are covered by default, Windows users have to be extra careful.)
<sup>[[link](#crlf)]</sup>

  * If you're using Git you might want to add the following
    configuration setting to protect your project from Windows line
    endings creeping in:

    ```bash
    $ git config --global core.autocrlf true
    ```

* <a name="no-semicolon"></a>
  Don't use `;` to separate statements and expressions. As a corollary - use one
  expression per line.
<sup>[[link](#no-semicolon)]</sup>

  ```bash
  # bad
  echo 'foobar'; # superfluous semicolon

  echo 'foo'; echo 'bar' # two expressions on the same line

  # good
  echo 'foobar'

  echo 'foo'
  echo 'bar'
  ```


### Syntax


### Naming


### Comments

> Good code is its own best documentation. As you're about to add a
> comment, ask yourself, "How can I improve the code so that this
> comment isn't needed?" Improve the code and then document it to make
> it even clearer. <br>
> -- Steve McConnell

* <a name="no-comments"></a>
  Write self-documenting code and ignore the rest of this section. Seriously!
<sup>[[link](#no-comments)]</sup>

* <a name="english-comments"></a>
  Write comments in English.
<sup>[[link](#english-comments)]</sup>

* <a name="hash-space"></a>
  Use one space between the leading `#` character of the comment and the text
  of the comment.
<sup>[[link](#hash-space)]</sup>

* <a name="english-syntax"></a>
  Comments longer than a word are capitalized and use punctuation. Use [one
  space](https://en.wikipedia.org/wiki/Sentence_spacing) after periods.
<sup>[[link](#english-syntax)]</sup>

* <a name="no-superfluous-comments"></a>
  Avoid superfluous comments.
<sup>[[link](#no-superfluous-comments)]</sup>

  ```bash
  # bad
  counter=$((counter+1)) # Increments counter by one.
  ```

* <a name="comment-upkeep"></a>
  Keep existing comments up-to-date. An outdated comment is worse than no
  comment at all.
<sup>[[link](#comment-upkeep)]</sup>

> Good code is like a good joke - it needs no explanation. <br>
> -- Russ Olsen

* <a name="refactor-dont-comment"></a>
  Avoid writing comments to explain bad code. Refactor the code to make it
  self-explanatory. (Do or do not - there is no try. --Yoda)
<sup>[[link](#refactor-dont-comment)]</sup>


### How to Contribute?

It's easy, just follow the [contribution guidelines](https://github.com/AJAlabs/bash-style-guide/blob/master/CONTRIBUTING.md).


### License

This work is licensed under the [MIT License](https://github.com/AJAlabs/bash-style-guide/blob/master/LICENSE.md)


### Spread the Word

The hope is that this guide becomes a community-driven style guide. A
community-driven style guide is of little use to a community that
doesn't know about its existence. Tweet about the guide, share it with
your friends and colleagues. Every comment, suggestion or opinion we
get makes the guide just a little bit better. And we want to have the
best possible guide, don't we?


### Resources

* Bash Guide for Beginners: [HTML](http://www.tldp.org/LDP/Bash-Beginners-Guide/html/) [PDF](http://www.tldp.org/LDP/Bash-Beginners-Guide/Bash-Beginners-Guide.pdf)
* Advanced Bash-Scripting Guide: [HTML](http://www.tldp.org/LDP/abs/html/index.html) [PDF](http://www.tldp.org/LDP/abs/abs-guide.pdf)
* Bash Reference Manual: [HTML](https://www.gnu.org/software/bash/manual/bashref.html) [PDF](https://www.gnu.org/software/bash/manual/bash.pdf)

* [bash Cookbook](http://amzn.to/1nhKgbf)
* [Classic Shell Scripting](http://amzn.to/1nhKpvm)
* [bash Pocket Reference](http://amzn.to/1lI77eY)
