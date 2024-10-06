# Level 15

## 1. The problem

From the last level: "The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14."

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## 2. Logging into the terminal

[level14](/levels/level4.md)

## 3. Overview

Now we need to use the file in "/etc/bandit_pass/bandit14" as our key.

## 4. The command

Using `nc` we can submit and listen to localhost:30000

## 5. Putting it all together

`cat /etc/bandit_pass/bandit14 | nc localhost 30000`
