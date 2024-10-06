# Level 16

## 1. The problem

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

## 2. Logging into the terminal

`ssh bandit15@bandit.labs.overthewire.org -p 2220`
password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

## 3. Overview

Hear the port 30001 on localhost, for that `ncat --ssl` should be used

## 4. The command

According to the manual
"Ncat is a feature-packed networking utility which reads and writes data across networks from the command
       line. Ncat was written for the Nmap Project and is the culmination of the currently splintered family of
       Netcat incarnations. It is designed to be a reliable back-end tool to instantly provide network connectivity
       to other applications and users. Ncat will not only work with IPv4 and IPv6 but provides the user with a
       virtually limitless number of potential uses."

## 5. Putting it all together

`ncat localhost 30001 --ssl`
input: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
