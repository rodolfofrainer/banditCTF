# Level 10

## 1. The problem

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

## 2. Logging into the terminal

`ssh bandit9@bandit.labs.overthewire.org -p 2220`
password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

## 3. Overview

`cat` into the data.txt provides a an unreadable output.
Filter, once again, is the solution. The catch is, what should we filter for? We start filtering for human-readable characters.

## 4. The command

`man strings`
strings - print the sequences of printable characters in files

Using `strings` we recieve an output, with only human-readable characters.
Now using the `grep` command we should look for "=".

## 5. Putting it all together

`strings data.txt | grep ==`
the output is: "\a!;========== the \a========== passwordf\a========== isc\a========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey"
password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
