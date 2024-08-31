# Level 9

## 1. The problem

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

## 2. Logging into the terminal

`ssh bandit8@bandit.labs.overthewire.org -p 2220`

password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

## 3. Overview

When `ls` into the home directory, we only see 1 file, "data.txt". However when `cat`ing it we're met with an enormous quantity of text, again and presumably repeated. We need to filter it by uniqueness.

The easiest way to do so is using the command `uniq` however, it essentially only works from one line to the next, and using it by itself won't help.
Sorting the output first would do the trick.

## 4. The command

`sort` Is used to sort the file output, allowing us to compare if a line is the same as the next;

`uniq` is the command to do this comparison, however, if we don't specify that we want to disregard all output that exists more than once, it will essentially only remove the repetitions, not necessarilly display only unique items.

`-u` will allow us to do just that.

And to use them all together, at the same time we use `|` which allow us to get the output from the left-side command, and use it on the right-side command.

## 5. Putting it all together

`sort data.txt | uniq -u`

password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
