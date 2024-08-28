# Level 11

## 1. The problem

The password for the next level is stored in the file data.txt, which contains base64 encoded data

## 2. Logging into the terminal

`ssh bandit10@bandit.labs.overthewire.org -p 2220`
password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

## 3. Overview

`cat` data.txt does not seem to do the trick for us. Encryption is afoot. We need to decode the base64 file.

## 4. The command

Using the flag `-d` for degrag on the command `base64` should give us the proper result.

## 5. Putting it all together

`base64 -d data.txt`
password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
