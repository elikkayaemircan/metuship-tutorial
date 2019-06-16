# Connection to A Remote Host via Secure Shell (SSH)

Secure Shell is a network protocol which presents you a connection through shell with security keys. The details of the connection protocol isn't in our scope for this tutorial.

To connect a remote host via SSH, you should use a SSH client. In most of the GNU/Linux systems, SSH client is installed by default. You can connect to the server by just typing,

    user@localhost:~$ ssh remoteuser@remotehost
    The authenticity of host 'remotehost (remotehost IP)' can't be established.
    RSA key fingerprint is 'some RSA key'
    Are you sure you want to continue connecting (yes/no)? yes
    Warning: Permanently added 'remotehost IP' (RSA) to the list of known hosts.
    Login as: remoteuser
    remoteuser@remotehost's password:
    Last login: date from localhost
    remoteuser@remotehost:~$

As you seen the messages on the line 2-5, first time connection from a localhost needs to be signed by remotehost. You can just allow a key-pair creation by typing yes at line 4.

An alternative to this, you can use PuTTY Software. PuTTY is a basic and lighweighted SSH client. I suggest you to use this client on Microsoft Windows systems, but explaining the details is not necessary for PuTTY since it is already easy to use with Graphical User Interface (GUI).

When you work on lxplus hosts, you probably need to use Graphical User Interface for plots, histograms, etc. To enable the GUI Forwarding, you should use the previous comment with -X or -Y option.

    user@localhost:~$ ssh -Y remoteuser@remotehost

This parameters allow you to see the plots and other things.
