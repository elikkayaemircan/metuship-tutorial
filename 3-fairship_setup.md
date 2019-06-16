# FairShip Installation on Lxplus Hosts

Before starting this section, I should mention that the instructions on https://github.com/ShipSoft/FairShip would be more reliable and up-to-date. So, I advise you to check the link, too. This instructions are actually based on that document and some further settings.

On Github link of FairShip, you can track the changes on code and version notes. Again, by using the Github repository, you can setup the framework on your local system. Please notice that these steps are explanations for the installation on lxplus.

In your home directory on lxplus, start to clone the source code of the framework.

    ~$ cd $HOME
    ~$ git clone https://github.com/ShipSoft/FairShip.git

After the cloning ends, enter inside the directory you have just installed and make the necessary changes if exists any. At this step, probably you do not need make any changes on default settings. Only thing you should be careful about is setting the environmental variable SHIPBUILD to the path mentioned below. This will allow you to use pre-compiled libraries for FairShip Framework. And then, run the script localBuild.sh which is created for installation on lxplus.

    ~$ cd FairShip
    ~/FairShip$ export SHIPBUILD=/cvmfs/ship.cern.ch/SHiPBuild
    ~/FairShip$ ./localBuild.sh

With this step, installation finishes. Before starting the FairShip, you should install the remaning environmental variables from lxplus by running the command,

    ~$ cd $HOME
    ~$ FairShipRun/config.sh
    setup aliBuild environment
    setup lcg environment
    # This command will setup your environment to use FairShip

Every time you want to use FairShip Framework, you should start with installing the environmental variables at the last step. To avoid this and make the things easier, you can use alias. alias is nothing but let you set some shortcuts on your environment. Let's check the .bashrc file under your home directory.

    ~$ cat .bashrc
    # .bashrc

    # Source global definitions
    if [ -f /etc/bashrc]; then
      . /etc/bashrc
    fi

    # User specific aliases and functions

You can get a different kind of output after the command, but it should be seem more or less the same. Under the section "# User specific aliases and functions", you can set your variables like the following.

    ~$ echo "alias FairSetup='source $HOME/FairShipRun/config.sh'" >> $HOME/.bashrc
    ~$ echo "export EOS=/eos/experiment/ship/user/your-user-name" >> $HOME/.bashrc
    
By running the command in first line above, you should set the alias that each time you type FairSetup on your screen, you install the FairShip environment. And running the command in second line above, set the variable $EOS to your eos folder path. By this method, you can set any variable with your needs.

    ~$ FairSetup
    setup aliBuild environment
    setup lcg environment
    ~$
    ~$ cd $EOS
    ~/eos/experiment/ship/user/your-user-name$
