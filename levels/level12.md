# Level 12

## 1. The problem

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## 2. Logging into the terminal

`ssh bandit11@bandit.labs.overthewire.org -p 2220`
password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

## 3. Overview

`cat` into data.txt gives a jumble of characters, seems like the file is encrypted, again. We need to translate it this time.

## 4. The command

`tr` can be used to tranlate,or shift, a set of characters to the side.

## 5. Putting it all together

`cat data.txt | tr '[a-zA-Z]' '[n-za-mN-ZA-M]'`
password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
