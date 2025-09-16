* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [1. Get Started](https://autonomylogic.com/docs-category/overview/ "1. Get Started")
* 1.4 Installing OpenPLC Runtime on Linux


1.4 Installing OpenPLC Runtime on Linux
=======================================

 

Welcome! We are excited that you want to learn more about OpenPLC. This page contains step-by-step instructions on how to get OpenPLC Runtime installed in your system. The OpenPLC Runtime can run on a variety of Linux systems, but it works better on Debian-based distributions like Ubuntu and Raspbian.

The best way to get OpenPLC Runtime into your device is by using git. Usually, git comes preinstalled on most Linux distributions. If for some reason you don’t have git installed on your system, you can install it by opening terminal and typing:

> sudo apt-get install git

To install OpenPLC, type these lines on terminal:

> git clone https://github.com/thiagoralves/OpenPLC\_v3.git
>
> cd OpenPLC\_v3
>
> ./install.sh linux

If you are installing OpenPLC on a specific Linux hardware, like the Raspberry Pi for example, you must replace the ‘linux’ parameter with your platform specific argument:

> ./install.sh rpi

Below are the valid arguments for the installer:

* *win* – Install OpenPLC on Windows over Cygwin
* *linux* – Install OpenPLC on a Debian-based Linux distribution
* *docker* – Install OpenPLC in a Docker container
* *rpi* – Install OpenPLC on a Raspberry Pi
* *neuron* – Install OpenPLC on a UniPi Neuron PLC
* *custom* – Skip all specific package installation and tries to install OpenPLC assuming your system already has all dependencies met

The installation process will take a while (up to 1 hour depending on your system). Meanwhile, grab a [insert your favorite beverage here] and relax! Once OpenPLC is installed, just reboot your device and it will start automatically after boot.

Platform Specific Differences
=============================

Raspberry Pi
------------

Besides using the special ‘rpi’ command from above, you also must have the WiringPi library installed to be able to run OpenPLC. WiringPi is responsible for controlling the Raspberry Pi GPIO pins. Without it, you won’t be able to activate the Raspberry Pi driver and OpenPLC won’t be able to control the board pins. To install WiringPi, get the latest .deb version from:

> https://github.com/WiringPi/WiringPi/releases/

The -armhf.deb file should be used on 32-bit OS (Raspberry Pi 3 and under) and the -arm64.deb is meant for 64-bit OS (Raspberry Pi 4 and up). Download the appropriate file for your architecture on your Raspberry Pi and install it with the dpkg command:

> dpkg -i wiringpi-[version]-armhf.deb
>
> or
>
> dpkg -i wiringpi-[version]-arm64.deb

Test that the WiringPi installation finished successfully with the command:

> gpio -v

Neuron PLC
----------

To avoid compatibility problems, it is better to download the most recent UniPian Neuron OS from the UniPi website and make a fresh install. Also, keep in mind that when OpenPLC is installed on UniPian, it completely disables EVOK and all related services.​

UniPi Industrial Platform
-------------------------

Before starting OpenPLC runtime, you will need to load the I2C module into the kernel. This will enable OpenPLC to communicate with the I2C peripherals on your UniPi board. To load the I2C module, type:

> ​gpio load i2c

A reboot is needed after using this command. You only need to type it once.

##### What are your Feelings

Updated on 2022-10-10

Leave a Reply [Cancel reply](/docs/installing-openplc-runtime-on-linux-systems/#respond)
----------------------------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2Finstalling-openplc-runtime-on-linux-systems%2F) to post a comment.