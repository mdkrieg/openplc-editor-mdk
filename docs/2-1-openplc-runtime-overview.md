* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [2. OpenPLC Runtime](https://autonomylogic.com/docs-category/openplc-runtime/ "2. OpenPLC Runtime")
* 2.1 OpenPLC Runtime Overview


2.1 OpenPLC Runtime Overview
============================

 

The OpenPLC Runtime allows you to run PLC programs created on the OpenPLC Editor. The main runtime has a built-in webserver that allows you to configure several parameters of the runtime. Micro implementations of the OpenPLC Runtime (i.e. versions of the runtime that go on microcontrollers and Arduino boards) do not have the built-in webserver. Instead, all runtime configurations for the micro runtime are done straight from the OpenPLC Editor upload dialog (see **[1.5 Installing OpenPLC Runtime on Microcontroller Boards](/docs/installing-openplc-runtime-on-arduino-and-other-platforms/)**).

The main runtime webserver is available at your target IP address on port 8080. For example, if you installed OpenPLC Runtime on a Rasberry Pi, and your Raspberry Pi IP address is 192.168.0.103, then you can access OpenPLC Runtime by opening your web browser and pointing it to http://192.168.0.103:8080.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/reference/basics/uploading-url.png)

If you are getting page errors, make sure your computer can access the Raspberry Pi on your network. If you don’t know the IP address of your board, the Raspberry Pi foundation has **[a nice guide](https://www.raspberrypi.com/documentation/computers/remote-access.html)** to help you out.

Once you access OpenPLC webserver, you should see in your browser window a login page like this:

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/runtime/img/login.png)

The default username and password is openplc (login) and openplc (password). This means that the first thing you must do after logging in for the first time is **change the default username and password!** It is very easy to do that. Just go to the Users menu on the left and click on the OpenPLC User to change the user information as you like.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/runtime/img/edituser.png)

Once you save the changes you will be prompted to login again. Just login with your new credentials and you will be good to go!

Enabling Hardware IO Access
===========================

By default OpenPLC runtime is installed with a blank driver. This means that it won’t be able to control your hardware GPIO pins straight away with OpenPLC. First, you will have to enable the correct hardware driver for your platform. On the left menu, click on “Hardware” and choose the appropriate driver from the popup menu. Make sure you pick the correct driver for your board, otherwise OpenPLC Runtime will fail to compile the runtime core.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/runtime/img/selecthw.png)

Once you’ve selected the right driver, click on “Save changes” and wait until the runtime core is rebuilt. If everything is correct, you should see a message at the end saying that the compilation ended successfully.

##### What are your Feelings

Updated on 2022-07-06

Leave a Reply [Cancel reply](/docs/2-1-openplc-runtime-overview/#respond)
-------------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2F2-1-openplc-runtime-overview%2F) to post a comment.