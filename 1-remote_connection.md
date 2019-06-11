# Connection to A Remote Host via Secure Shell (SSH)

Secure Shell is a network protocol which presents you a connection through shell with security keys. The details of the connection protocol isn't in our scope for this tutorial.

To connect a remote host via SSH, you should use a SSH client. In most of the GNU/Linux systems, SSH client is installed by default. You can connect to the server by just typing,

    user@localhost:~$ ssh *remoteuser*@*remotehost*
    The authenticity of host '*remotehost* (*remotehost IP*)' can't be established.
    RSA key fingerprint is *some RSA key*
    Are you sure you want to continue connecting (yes/no)? yes
    Warning: Permanently added '*remotehost IP*' (RSA) to the list of known hosts.
    Login as: *remoteuser*
    *remoteuser*@*remotehost*'s password:
    Last login: date from localhost
    *remoteuser*@*remotehost*:~$

As you seen the messages on the line 2-5, first time connection from a localhost needs to be signed by remotehost. You can just allow a key-pair creation by typing yes at line 4.

When you work on lxplus hosts, you probably need to use Graphical User Interface for plots, histograms, etc. To enable the GUI Forwarding, you should use the previous comment with -X or -Y option.

    user@localhost:~$ ssh -Y *remoteuser*@*remotehost*

This parameters allow you to see the plots and other things.

In addition to them, you can set a SSH Key to connect to the remote server without entering password everytime. But, this method can be dangerous to use and it is not suggested. In your pc, create a SSH Key by typing,

    user@localhost:~$ ssh-keygen
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/user/.ssh/id_rsa):
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:
    Your identification has been saved in /home/user/.ssh/id_rsa.
    Your public key has been saved in /home/user/.ssh/id_rsa.pub.
    The key fingerprint is:
    b7:ac:b0:80:85:ad:6f:16:ad:1c:e3:63:2f:a0:10:15 user@localhost
    The key's randomart image is:
    +---[RSA 2048]----+
    |           . o + |
    |         = X * . |
    |      . O @ = . .|
    |     + o X O . + |
    |   . = S * = o   |
    | . ..o . . o .   |
    |     + .o. E     |
    |      + ...o.    |
    |     . . ooo+.   |
    +----[SHA256]-----+
    user@localhost:~$

After the key generation, copy the Public Key to the Remote Host,

    user@localhost:~$ ssh-copy-id *remoteuser*@*remotehost*
    *remoteuser*@*remotehost*'s password:
    user@localhost:~$

Then, you can access to the remotehost without typing your password

    user@localhost:~$ ssh *remoteuser*@*remotehost*
    Last login: date from localhost
    *remoteuser*@*remotehost*:~$

But last time, I should warn the users to not using this method. It might be dangerous for the ones which are new to work on remotehost.
