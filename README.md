# br
br (short for "brain') is an extremely simple second-brain cli tool. It is comprised of two simple scripts, `brl` and `brs`, that store and search through text (respectively) using a simple working directory of text files at `$HOME/.br`. By design, there is no deletion function—why would you want to delete things from your _brain_ anyway?

br follows the unix philosophy: everything is text, so you can build on this simple foundation any way you wish.

I built br for my own use as a replacement for much more complex second-brain tools like Notion, because br accomplishes 95% of what I need (everything but PDFs & images, really, although you can simply excerpt from the former) while being the simplest thing in the world.

## dependencies
* POSIX shell
* [ripgrep](https://github.com/BurntSushi/ripgrep)

## setup
1. Put these two scripts somewhere in PATH

## usage
Use `brl` to make br learn a thing. It will place the thing in a file named with the current date in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format, auto-creating such a file as needed. A time (as HH:MM in 24-hour time, according to the system) is placed at the front of each entry into br.

Use `brs` to search br for a thing. It will display all instances of the thing (case-insensitively, but otherwise according to ripgrep's pattern matcher).

Using this simple foundation, you can store any sort of information and retrieve it using any keyword or phrase you know how to represent with a regular expression.

**NOTE**: Quotation marks need to be escaped.

## importing
Import into br by putting text files into your `$HOME/.br` directory. `brs` doesn't actually care how the files it's searching through are structured.
