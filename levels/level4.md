# Level 4

## 1. The problem

The password for the next level is stored in a hidden file in the inhere directory.

## 2. Logging into the terminal

`ssh bandit3@bandit.labs.overthewire.org -p 2220`

password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

## 3. Overview

Up until now we've been working with files in the same directory, on this problem it says that the file we're looking for is in another directory.

To get to another directory we have to use the command "cd", change directory.

## 4. The command

With the "cd" command, we can provide a path, either relative or absotule to another directory that we want to access.

In this case the directory "inhere" is a subdirectory of "~", the home directory.

there are a few ways to solve this, even without necessarily moving to another directory, however we are going to stick with a more step by step approach.

Using `cd inhere` we're moving to the "inhere directory".

Then using "ls" we should be able to find our file.

Usually that's the case, except when the file is hidden (this is the case here)

Ok, we're in the ~/inhere, and we can't see what's inside the directory since it is hidden, how to proceed?

Looking into the "man" of "ls", which is sort of a "how to use the following command", that goes like this `man ls`, we see that the very first option of the command is `-a, --all
              do not ignore entries starting with`.

That means that we can use the following command `man ls -a` to see all files in the directory; And it shows that there's a file called "...Hiding-From-You" inside.

With that knowledge we can simply call `cat ...Hiding-From-You`

## 5. Putting it all together

commands: `cd inhere && ls -a` `cat ...Hiding-From-You` OR `ls -a inhere` `cat inhere/...Hiding-From-You`
