# Level 23

## 1. The problem

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## 2. Logging into the terminal

`ssh bandit22@bandit.labs.overthewire.org -p 2220`
pw: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

## 3. Overview

Like the last challenge, we ls into the cron directory, cat the job23 and see it is running a shell script at "/usr/bin/cronjob_bandit23.sh", trying to cat into it we see that it is scrypting the name of the folder it is dumping the contents of its password. We can execute it though.

## 4. The file

`#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget`

## 5. Putting it all together

`cat /tmp/8169b67bd894ddbb4412f91573b38db3` (will be different from session to session)
