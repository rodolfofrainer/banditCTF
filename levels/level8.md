# Level 8

## 1. The problem

The password for the next level is stored in the file data.txt next to the word millionth

## 2. Logging into the terminal

`ssh bandit7@bandit.labs.overthewire.org -p 2220`

password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

## 3. Overview

When `ls` into the home directory, we only see 1 file, "data.txt". However when `cat`ing it we're met with an enormous quantity of text. We need to filter it.

## 4. The command

Knowing that the word "millionth" is close to it we can then `grep` it.

DESCRIPTION
       grep  searches  for  PATTERNS  in  each FILE.  PATTERNS is one or more patterns separated by newline characters, and grep prints each line that
       matches a pattern.  Typically PATTERNS should be quoted when grep is used in a shell command.

       A FILE of “-” stands for standard input.  If no FILE is given, recursive searches examine the working directory, and nonrecursive searches read
       standard input.

       Debian also includes the variant programs egrep, fgrep and rgrep.  These programs are the same as grep -E, grep -F, and grep -r,  respectively.
       These variants are deprecated upstream, but Debian provides for backward compatibility. For portability reasons, it is recommended to avoid the
       variant programs, and use grep with the related option instead.

Essentially we can filter the output with an input.

## 5. Putting it all together

`grep millionth data.txt`
