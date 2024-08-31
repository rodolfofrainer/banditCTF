# Level 2

## 1. The problem

The password for the next level is stored in a file called - located in the home directory

## 2. Logging into the terminal

connection: `ssh bandit1@bandit.labs.overthewire.org -p 2220`

password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

## 3. Overview

On this level we need to read from a file called "-"; If you try to read it the same way we did in the last level you won't be able to as `cat -` won't read it.

Instead we need to be a bit more specific with the command's destination. What is needed is to tell the shell to specifically look into the home directory (which we log in as a default) and then look for the file "-".

## 4. The command

There are 2 ways to go about it, one is to use the variable for the home directory: ~
Which would produce the following command line: `cat ~/-`

The other option, which I find a bit more practical, is using the variable for the directory that we are currently working: .
That would produce the following command line: `cat ./-`

Both options work, however the first is only viable if the file is located in the home directory (which in this case it happens to be), the second I find a bit more practical as one would usually be working from inside the directory that they want to modify a file from.

## 5. Putting it all together

`cat ./-`

password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
