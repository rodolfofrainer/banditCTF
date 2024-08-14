# Level 1

## 1. The problem

`The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.`

## 2. Logging into the terminal

connection: `ssh bandit0@bandit.labs.overthewire.org -p 2220`
password: bandit0

## 3. Overview

Using the command ls we can see that only 1 file is present in this machine, and it is called readme. For that we will use the 'cat' command.

Upon doing so we recieve the following text from the file

`Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!
The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

## 4. The command

The 'cat' command in linux is used to "concatenate files and print on the standard output", in simpler terms it is used to read a file and display its contents on the terminal.

## 5. Putting it all together

`cat readme`
Password for the next level: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
