# Level 7

## 1. The problem

The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size


## 2. Logging into the terminal

`ssh bandit6@bandit.labs.overthewire.org -p 2220`

password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

## 3. Overview

The problem here is that we don't know where in the machine this file might be located, which will probably lead us to a lot of problems with limited Permissions, and that's the name of the game.

## 4. The command

Once again, we're tasked with finding a file with specific characteristics.
With that in mind, we're going to use `find` with the option `-size 33c` and see what that brings us.

And that was nothing, because the home folder is empty, the problem says that it is somewhere, going through the root directory would be the easiest way to get it done.

That gives us a whole bunch of files with permission denied, what if we tighten our search?
Using the flags `-user` and `-group`, surely would filter our results to only one, or at least one would think, however no, we're met with several files with "Permission Denied".

Ok, how do we get rid of that then? With `2> /dev/null` appended at the end of the command, this device is a special file in Linux that discards any data written to it, effectively suppressing the output. In other words, it acts as a “black hole” for error messages.

With the command `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` we get the file "/var/lib/dpkg/info/bandit7.password", now we only have to read it.

For more information on the subject of stdout redirection check this wesite:
[What does 2>/dev/null mean?](https://askubuntu.com/questions/350208/what-does-2-dev-null-mean)

## 5. Putting it all together

`find / -user bandit7 -group bandit6 -size 33c 2>/dev/null | xargs cat`
