# Level 13

## 1. The problem

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command `mktemp -d`. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## 2. Logging into the terminal

`ssh bandit12@bandit.labs.overthewire.org -p 2220`

password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

## 3. Overview

First we create a temporary folder for our tests. Using `mktemp -d` we create a folder in the following address "/tmp/tmp.rAZ0j7rw50", yours will be different.
Now we need to move data.txt to the directory. `cp data.txt /tmp/tmp.rAZ0j7rw50/data.txt`.
Using cat we only get a jumble of characters, or a hex dump.
`cat data.txt`
00000000: 1f8b 0808 d2e9 9766 0203 6461 7461 322e  .......f..data2.
00000010: 6269 6e00 0141 02be fd42 5a68 3931 4159  bin..A...BZh91AY
00000020: 2653 59ea 2468 ae00 0017 7fff dadb b7fb  &SY.$h..........
etc...

## 4. The command

Time to unjumble this.
First we `xxd -r` the data.txt file into another file
`xxd -r data.txt > data2.txt`
now using `file data2.txt` we see that the file is a gzip, so we need to transform the .txt into a .gzip and decompress it.
`mv data2.txt data2.gz`
`gzip -d data2.gz`
Now when we list our directory we have the following output:
"data2  data.txt"
Now we `file data2`
"data2: bzip2 compressed data, block size = 900k"
Move the data2 into "data2.bz2". Decompress `bzip2 -d data2.bz2`
Now we have a "data2" which is a gzip, so we move and decompress.
Which givs us a "tar" file. Move the file to correct extention`mv data2 data2.tar`, extract `tar xf data2.tar`
Which givs us a "tar" file. Move the file to correct extention`mv data5.bin data2.tar`, extract `tar xf data2.tar`
Which givs us a "bzip2" file. Move the file to correct extention`mv data6.bin data2.bz2`, extract `bzip2 -d data2.bz2`
Which givs us a "tar" file. Move the file to correct extention`mv data2 data2.tar`, extract `tar xf data2.tar`
Which givs us a "gzip" file. Move the file to correct extention`mv data8.bin data2.gz`, extract `gzip -d data2.gz`
Giving us the final file, data2

## 5. Putting it all together

`cat data2`
