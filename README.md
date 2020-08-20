# br
br (short for "brain') is an extremely simple second-brain cli tool.

## dependencies
* POSIX shell
* [ripgrep](https://github.com/BurntSushi/ripgrep)

## setup
1. choose a directory to store notes in
2. edit the $WORK_DIR in both files to this directory

**NOTE**: You should choose a directory that is otherwise empty as we will be searching it with ripgrep.

## usage
use `brl` to make br learn a thing. It will place the thing in a file named with the current date in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601). It will place a time (as HH:MM in 24-hour time, according to system time) at the front of each entry.

use `brs` to search br for a thing. It will display all instances of the thing (case-insensitively, but otherwise according to ripgrep's pattern matcher).
