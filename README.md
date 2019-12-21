# Ubuntu with GPU note
 My personal note of installing the OS on an empty machine, with GPU driver

## Pre-Preparation
* First I am lazy so I get my machine from [iBuyPower](https://www.ibuypower.com/Site/Computer/desktops) during the black friday sale
  * I'm planning on getting my tax back though, tax is high at that price
  * To have a powerful GPU you need to have a strong power support as well
  * Be sure to select a mother-board that left the space for further expansion (more GPUs) if you might add more GPUs in the future
  * In general 2080 Ti is a good choice for now
  * I want Ubuntu, so it saved me around 90 dollars not having a pre-installed Windows
* Searching online I found a few blogs sharing experiences on Ubuntu + Nvidia driver
  * [This is a tutorial](https://www.pugetsystems.com/labs/hpc/The-Best-Way-To-Install-Ubuntu-18-04-with-NVIDIA-Drivers-and-any-Desktop-Flavor-1178/) where some of the following discussions said there might be black-screen issue.
  * [This is a tutorial installing Nvidia Drivers on Ubuntu Bionic Beaver](https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-ubuntu-18-04-bionic-beaver-linux)
    * [A chinese discussion on this](https://blog.csdn.net/tjuyanming/article/details/80862290)
  * [The official Ubuntu Installation Guide](https://help.ubuntu.com/community/GraphicalInstall)
    * I downloaded an ISO from [here](http://cdimage.ubuntu.com/releases/18.04.3/release/?_ga=2.134170190.1104284630.1574932620-706300109.1574932620) (That is the 64-bit **Ubuntu 18.04.3 LTS (Bionic Beaver)** indeed)
    * And there's [instruction on how to make a USB stick for installation](https://help.ubuntu.com/community/Installation/FromUSBStick) with some [detailed information](https://ubuntuforums.org/showthread.php?t=2230389)
      * a third-party Chinese instruction from [CSDN](https://blog.csdn.net/Allyli0022/article/details/81674504) providing another option (**I used this**)
* I found the NVidia Driver I should install is probably [this](https://www.nvidia.com/download/driverResults.aspx/154997/en-us)
* I decided to get my USB installer ready (following [this CSDN blog]((https://blog.csdn.net/Allyli0022/article/details/81674504))) first, and then wait for the machine to come, the order of trying is:
  * [The tutorial installing Nvidia Drivers on Ubuntu Bionic Beaver](https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-ubuntu-18-04-bionic-beaver-linux)
    * Refer to the [Chinese discussion](https://blog.csdn.net/tjuyanming/article/details/80862290) first if any problem encountered
  * otherwise use Google
  * or turn to labmates for help

## Preparation
* Okay my desktop comes so fast, thanks to iBuyPower.
* Tried installing and found that I used the wrong version --- why am I using server version...
* The right version comes here [18.04 **Bionic Beaver**](http://releases.ubuntu.com/18.04/)
* Then [the official Ubuntu Installation Guide](https://help.ubuntu.com/community/GraphicalInstall)
* [The tutorial installing Nvidia Drivers on Ubuntu Bionic Beaver](https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-ubuntu-18-04-bionic-beaver-linux)
* Then cudnn

## Installation
* Installing Ubuntu:
  * Problem 1: my installation USB drive at least does install something, but wrong version somehow
    * Fixed by having the right version **desktop** ([18.04 **Bionic Beaver**](http://releases.ubuntu.com/18.04/))
  * Problem 2: it seems that it is not successfully installing anything? It keeps boosting from the USB drive and asking me to install, once and once again, for always.
    * Fixed by (I don't fully understand what happened there) boosting from a newly-created **partition** of the USB drive and then it is foreverly installed. No tutorial online has mentioned this.
* Installing GPU Driver:
  * Problem 1: Tried to follow the [unofficial tutorial](https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-ubuntu-18-04-bionic-beaver-linux) at first but the first step seems to be different.
    * Detailed description of the problem found: when saying ```ubuntu-drivers devices```, not showing any NVidia info.
    * Fixation from the forum [here](https://forums.linuxmint.com/viewtopic.php?t=287206): 
        ```shell
        sudo apt-add-repository ppa:graphics-drivers/ppa
        ```
    * Now it detects the NVidia GPU card and recommends drivers
      * caution: it takes longer for the detection though
  * Problem 2: while the installation runs the display suddenly went off but I hear the fan goes like crazy





