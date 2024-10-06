# Level 20

## 1. The problem

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## 2. Logging into the terminal

`ssh bandit19@bandit.labs.overthewire.org -p 2220`
pw: cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

## 3. Overview

We have to use the binary provided `bandit20-do`; it essentially allow us to execute commands as the user "bandit20"

## 4. The command

nothing to add here

## 5. Putting it all together

`./bandit20-do cat /etc/bandit_pass/bandit20`
