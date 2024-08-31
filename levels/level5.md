# Level 5

## 1. The problem

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

## 2. Logging into the terminal

`ssh bandit4@bandit.labs.overthewire.org -p 2220`

password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

## 3. Overview

Using `cd inhere` and the `ls` we see that there are a few files in this directory.
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09

## 4. The command

The command we will be using is `cat`, which allows us to read a file, we can go one at a time, with `cat -file00`, `cat -file01`, etc. Or we can brute force it and see if we can get an answer more easily with `cat -file0*`, which will read all files that match "-file0" and the "*" is a wild card.

## 5. Putting it all together

`cat -file0*` -> cat ./-file0*
N�.����9������F��p�������tk���%�������n�Qy�y͍�{+R�bZ�k�F�*	
l�����]�a߯-@gQ�÷�wz�P�ߠy��pӻT9�F��3ˤ����)
T�՜F�ǭ��QĹ�M���p4�-�8��=��!#g���4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
�$}P�cL���s��@�2%Y�(|�^��J
                   ы�Ϣ��

Therefore we can assume that the password is the only human-readable part

password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
