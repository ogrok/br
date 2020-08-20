# br
br (short for "brain') is an extremely simple second-brain cli tool. It is comprised of three simple scripts. The first two, `brl` and `brs`, store and search through text (respectively) using a simple working directory of text files at `$HOME/.br`. By design, there is no deletion function—why would you want to delete things from your _brain_ anyway?

The third script, `bri`, creates a rudimentary GTD inbox—see the related section below.

br follows the unix philosophy: everything is text, so you can build on this simple foundation any way you wish.

I built br for my own use as a replacement for much more complex second-brain tools like Notion, because br accomplishes 95% of what I need (everything but PDFs & images, really, although you can simply excerpt from the former) while being the simplest thing in the world.

## dependencies
* POSIX shell
* [ripgrep](https://github.com/BurntSushi/ripgrep)

## setup
1. Put these three scripts somewhere in PATH
2. Make sure they are executable

## usage
Use `brl` to make br learn a thing. It will place the thing in a file named with the current date in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format, auto-creating such a file as needed. A time (as HH:MM in 24-hour time, according to the system) is placed at the front of each entry into br.

Use `brs` to search br for a thing. It will display all instances of the thing (case-insensitively, but otherwise according to ripgrep's pattern matcher).

Using this simple foundation, you can store any sort of information and retrieve it using any keyword or phrase you know how to represent with a regular expression.

### inbox
The `bri` script creates and manipulates a file located at `$HOME/.br/.inb`. This is a special file that is designed to process incoming items in a queue. For instance, when you come across an article you would like to read later, add it to your inbox!

- Use `bri` followed by any text to add an item to your inbox.
- Use `bri -g` to retrieve the first (least recent) item from your inbox.
- Use `bri -c` to complete the first (least recent) item in your inbox. This deletes the line.

The three simple commands create a queue where you are only able to interact with the least recent thing in it, which is by design. When processing your inbox, you can therefore focus exclusively on each item in the order it was added.

**NOTE**: Quotation marks need to be escaped throughout all input.

## importing
Import into br by putting text files into your `$HOME/.br` directory. `brs` doesn't actually care how the files it's searching through are structured, and `brl` will never mess with any file except the one named with the current date as above.
