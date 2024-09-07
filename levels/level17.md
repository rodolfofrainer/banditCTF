# Level 17

## 1. The problem

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

## 2. Logging into the terminal

`ssh bandit16@bandit.labs.overthewire.org -p 2220`
password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

## 3. Overview

We need to listen to a range of ports from 31000-32000. After we need to use `ncat` again to send a packet to the port and see if it is the correct one.

## 4. The command

`nmap --script ssl-enum-ciphers -p 31000-32000 localhost` gives us 2 valid responses, 31518, 31790.
Using trial and error we discover that 31790 is correct when we use it together with ncat.
`echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | ncat localhost 31790 --ssl`
output: `answer key`

## 5. Putting it all together
we should go to the next level from this terminal, unless we want to create a file in our own machine (or copy and paste).

`echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | ncat --ssl localhost 31790 | ssh bandit17@bandit.labs.overthewire.org -p 2220`

***The overthewire team seems to not allow one to connect ssh on top ssh anymore, altough I'm pretty sure i was able to do this before. So copy or save the result rather than trying to pass it to the next level***

***PS- If you're saving the key as a file it should have access restrictions or it WILL NOT be accepted. Make sure the permissions are set to 0700***
