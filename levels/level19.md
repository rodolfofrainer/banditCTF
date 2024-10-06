# Level 19

## 1. The problem

The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

## 2. Logging into the terminal

`ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh`
pw: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

## 3. Overview

Using `-t` and `/bin/sh` to force the terminal to run a shell terminal without running the .bashrc

## 4. The command

There's only one file in this level, so cat into it.

## 5. Putting it all together

`cat readme`
