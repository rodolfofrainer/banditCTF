# Level 21

## 1. The problem

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

## 2. Logging into the terminal

`ssh bandit20@bandit.labs.overthewire.org -p 2220`
pw: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

## 3. Overview

The binary provided will send a packet to a specified port, if the answer is the password to the last level then it will output the next level's password.

## 4. The command

Using tmux we can create a new session inside the session. Doing so we cat the password for the level, and pass it into the `nc -l` command.

## 5. Putting it all together

In tmux: `cat /etc/bandit_pass/bandit20 | nc localhost 1234 -l` (1234 is the port we will be listening to)
Using Ctrl + b + d we go back into the orginal session (we can use `tmux a` to go back to the "virtual" session)
Now we only need the binary to send a packet into the port we are listening to.
`./suconnect 1234`
