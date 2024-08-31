# Level 3

## 1. The problem

The password for the next level is stored in a file called *spaces in this filename* located in the home directory

## 2. Logging into the terminal

`ssh bandit2@bandit.labs.overthewire.org -p 2220`
password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

## 3. Overview

Using the command `ls` we can see that there's only one file inside the home directory, "spaces in this filename".

When not told otherwise the shell will read the " " character as sort of a next instructions or as an argument if the command is able to take them.

For this reason we need to need to be able to tell the terminal to use a combination of words as a single argument.

## 4. The command

There are 2 ways to go about it:

The first method is to instruct the terminal that the next " " character should be disregarded.

1. `cat spaces\ in\ this\ filename`
The function of the "\" character is essentially a set of instructions that the next character has special properties. In this case, it should be disregarded.

The second method we instruct the shell to consider everything inside the quotes as on block

2. `cat "spaces in this filename"`
This tells the shell that "spaces in this filename" should be treated as a block of text rather than several sets of instructions

## 5. Putting it all together

`cat "spaces in this filename"`

password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
