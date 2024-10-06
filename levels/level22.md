# Level 22

## 1. The problem

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

## 2. Logging into the terminal

`ssh bandit21@bandit.labs.overthewire.org -p 2220`
pw: EeoULMCra2q0dSkYj561DX7s1CpBuOBt

## 3. Overview

We `ls` into /etc/cron.d/, and get an output stating that there's a file called "cronjob_bandit22", cat into it we see that it runs "/usr/bin/cronjob_bandit22.sh", cat into it we notice that it dumps the password content into a temp file, and we just need to cat into it.

## 4. The command

--------

## 5. Putting it all together

`cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` (temp file will be different at each session).
