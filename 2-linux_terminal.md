# Basics of GNU/Linux Terminal

GNU/Linux Terminal is the easiest way to do the project work on lxplus hosts. In the easiest manner, it is defined as your session on the host. You can manage your session at the host by using Bourne Again Shell (Bash) commands.

Some of the basic commands are listed below,

    ~$ ls
    test.txt  main.py  clean_log.sh  logs
    # List the files and folders in the path you are at
    ~$
    ~$ pwd
    /home/user
    # Prints Working Directory you are at
    ~$
    ~$ cd /home/user/logs
    ~/logs$
    # Change Directory
    ~$
    ~$ touch test2.txt
    # Creates a file with name test2.txt
    ~$
    ~$ mkdir test2
    # Make (creates) a Directory with name test2
    ~$
    ~$ rm test2.txt
    # Removes the file test2.txt
    ~$
    ~$ rmdir test2
    # Removes the directory test2

In GNU/Linux environment, one of the most helpful command is man (manual). Some of Bash commands might be complicated when they are used with OPTIONS (parameters). Parameters give you the extra abilities of that Bash command and you can get the manual of any command and its parameters by using man command.

    ~$ man man
    # Gives the manual of man command
    ~$
    ~$ man pwd
    # Gives the manual of pwd command
    ~$
    ~$ man ps
    # Gives the manual of ps command

An example to using OPTIONS is the following,

    ~$ mkdir -p /home/user/MCdata/run001/particle
    # Creates the directory given with all the sub-directories necessary.
    ~$
    ~$ python -i test.py
    # Runs python in interactive mode with -i option.
