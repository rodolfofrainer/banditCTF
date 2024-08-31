# Level 14

## 1. The problem

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

## 2. Logging into the terminal

`ssh bandit13@bandit.labs.overthewire.org -p 2220`
password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

## 3. Overview

We need to connect to ssh with bandit14`s credentials using the key present in the home directory

## 4. The command

Using `ssh -i` which allow us to use a key file to login, rather than credentials

## 5. Putting it all together

`ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey.private`
password: N/A