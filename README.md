# OS-provisioning
>Create and provision desired OS using Vagrant and Virtualbox
>This can be used for cross platform testing like on Windows, Linux (Ubuntu, Centos, RHEL etc.). Build your environment quickly then deploy and test.

Vagrant is a tool to help create and provision VirtualBox machines.Few of the reasons for using it would be:
* The development environment can be isolated from all the other junk that accumulates on primary computer.
* The development environment can be tuned to match a production server environment as closely as possible.
* Provisioning scripts define the machine configuration in code. This means the configuration is repeatable and versionable.

## Platforms
Everything has been tested on Ubuntu 14.04 LTS.
All below installation instructions are from Ubuntu. Instructions will change for different OS version. Feel free to create pull request (PR) for that or ask me.

## Installation
1. First we need to install Vagrant
    ```sh
    sudo apt-get install vagrant
    ```
    This will install virtual box 4.2 and other dependencies like ruby (in case you don’t have already)
    We can verify the installation using command :
    ```
    $vagrant -v
    ```
2. Now that we have Vagrant,VirtualBox,Ruby installed. Lets try and provision a vm. We would try and install Ubuntu 12.04 32 bit on virtual box using vagrant. Choose a location where you need to put your Vagrant file, I made a folder myVMs in home
The command :
    ```
    $ vagrant init precise64 http://files.vagrantup.com/precise64.box
    ```

3. Now the main part about configuring Vagrantfile
You can change following two lines as per the required OS (be careful)
    ```
     ........
    .......
    # Every Vagrant virtual environment requires a box to build off of.
        config.vm.box = "precise32"

    # The url from where the 'config.vm.box' box will be fetched if it
    # doesn't already exist on the user's system.
        config.vm.box_url = "http://files.vagrantup.com/precise32.box"
    ........
    ........
    ```
    >Use this _[VAGRANT_BOX_URL](http://www.vagrantbox.es/)_ for getting ready to run vagrant boxes.

    Example:

    |OS  (name)     | URL|
    |-------------  |:---:|
    | Windows 7     |   http://vagrantboxes.devopslive.org/windows-7-enterprise-i386.box|
    | OpenSuse      |   https://s3.amazonaws.com/circlejtp/OpenSuseVagrant/OpenSuse12_1x64_July14.box  |


## Usage
Following commands are very handy to play with Vagrantfile
  1.    ```$vagrant box add name url```
  2. ```$vagrant box list```
  3. ```vagrant up```
  4. ```vagrant destroy```


## Contributing
1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D


## License
 A psinc.jp product