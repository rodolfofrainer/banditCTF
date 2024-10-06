# Level 18

## 1. The problem

There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

## 2. Logging into the terminal

[level17](/levels/level17.md)

## 3. Overview

Need to check what changed between one version and the next.

## 4. The command

`diff` is used to output the difference of one file to another, line by line.

## 5. Putting it all together

`diff passwords.old passwords.new`
