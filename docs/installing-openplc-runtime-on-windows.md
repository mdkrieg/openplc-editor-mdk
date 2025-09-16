* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [1. Get Started](https://autonomylogic.com/docs-category/overview/ "1. Get Started")
* 1.3 Installing OpenPLC Runtime on Windows


1.3 Installing OpenPLC Runtime on Windows
=========================================

 

Welcome! We are excited that you want to learn more about OpenPLC. This page contains step-by-step instructions on how to get OpenPLC Runtime installed in your system. The OpenPLC Runtime core was written with POSIX compatibility. Therefore, to be able to run on Windows, OpenPLC Runtime needs a special software called MSYS2. MSYS2 is a fork of Cygwin which provides substantial POSIX API functionality on Windows, and also has a large collection of GNU and Open Source tools which provide functionality similar to a Linux distribution.

Install OpenPLC Runtime Using Windows Installer
===============================================

The easiest way to install OpenPLC Runtime on Windows is through the Windows installer.

[![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%2064%2064'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/05/imageedit_1_5872481624.png)](https://autonomylogic.com//wp-content/uploads/files/OpenPLC%20Runtime%20for%20Windows.exe)

**[OpenPLC Runtime for Windows.exe](https://autonomylogic.com//wp-content/uploads/files/OpenPLC%20Runtime%20for%20Windows.exe)**

The installer above is a compilation of scripts that will automatically download and install MSYS2 and all required dependencies, followed by OpenPLC Runtime. Just download and run the installer to have OpenPLC Runtime installed in your system.

Install OpenPLC Runtime Manually
================================

If for any reason you are not able to run the installer above, then you can install OpenPLC Runtime manually on Windows following the steps below:

1. Download MSYS2 installer from <https://www.msys2.org/>
2. Open file explorer and go to the folder where you downloaded MSYS2 setup (for example Downloads).
3. Double-click on the MSYS2 installer and follow the screen prompts to get MSYS2 installed in your system

Once MSYS2 is installed, installing OpenPLC Runtime is simple and straightforward. Just open “MSYS2 MSYS” from the Windows menu and type:

```
pacman -Suy --noconfirm
pacman -S git --noconfirm
git clone https://github.com/thiagoralves/OpenPLC_v3.git
cd OpenPLC_v3
./install.sh win_msys2
```

After typing these commands, OpenPLC Runtime installation will start inside MSYS2. It may take a while (up to 15 minutes depending on your computer and internet speed). Once the installation finishes, you can start OpenPLC Runtime by typing the following commands on MSYS2 Terminal:

> cd OpenPLC\_v3
>
> ./start\_openplc.sh

##### What are your Feelings

Updated on 2024-09-03

Leave a Reply [Cancel reply](/docs/installing-openplc-runtime-on-windows/#respond)
----------------------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2Finstalling-openplc-runtime-on-windows%2F) to post a comment.