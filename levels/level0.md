# Level 0

On Level 0, the main objective is for the user to establish a connection to the terminal, which will allow the real game to begin. To do this, we will use the ssh command, which enables us to create a secure connection with another machine.

Secure Shell or SSH was created as a solution to Telnet's lack of security, as all text being sent over the connection are in plain text, which means that if any one can tap into the connection they're able to see everything being sent easily.

According to wikipedia:

`The Secure Shell Protocol (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network.[1] Its most notable applications are remote login and command-line execution. SSH was designed for Unix-like operating systems as a replacement for Telnet and unsecured remote Unix shell protocols, such as the Berkeley Remote Shell (rsh) and the related rlogin and rexec protocols, which all use insecure, plaintext methods of authentication, like passwords.`

## The problem

`The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.`

## 2. Logging into the terminal

The initial os the aim of this level, which is bandit0 (as well as the user), this is a very straight forward connection.

## 3. The command

The ssh command usually defaults to the port 22, because that is the standart for this technology.

The '-p' or '-port' is used to specify an explicity port to be used, in our case, 2220.

## 4. Putting it all together

`ssh bandit0@bandit.labs.overthewire.org -p 2220`
