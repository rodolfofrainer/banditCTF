# Level 6

## 1. The problem

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable

## 2. Logging into the terminal

`ssh bandit5@bandit.labs.overthewire.org -p 2220`

password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

## 3. Overview

`ls` from the home directory we see that there's only a folder called "inhere", and `cd`ing and `ls`ing that show us several directories like so:

maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19

This is getting a bit more complicated now, we need to filter the result as much as we can, and luckily linux provides a command for just that, `find`.

## 4. The command

The documentation is as follows: "find - search for files in a directory hierarchy"
To filter it more we need to check the properties provided. One of the flags we can use is: -size.

The documentation to that tells us that we need to provide more information to it:

"-size n[cwbkMG]
              File uses less than, more than or  exactly  n  units  of  space,
              rounding up.  The following suffixes can be used:

              `b'    for  512-byte blocks (this is the default if no suffix is
                     used)

              'c'    for bytes

              `w'    for two-byte words

              `k'    for kibibytes (KiB, units of 1024 bytes)

              `M'    for mebibytes (MiB, units of 1024 * 1024 = 1048576 bytes)

              `G'    for gibibytes (GiB,  units  of  1024  *  1024  *  1024  =
                     1073741824 bytes)"

So, we're in the directory "inhere", we need to find a file with 1033 bytes, giving us the command: `find -find 1033c`. Which provides us with a single file: "./maybehere07/.file2".And so we just need to `cat` into it.

## 5. Putting it all together

`find -size 1033c | xargs cat`

password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
