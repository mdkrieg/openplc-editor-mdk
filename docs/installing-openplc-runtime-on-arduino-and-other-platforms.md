* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [1. Get Started](https://autonomylogic.com/docs-category/overview/ "1. Get Started")
* 1.5 Installing OpenPLC Runtime on Microcontrollers


1.5 Installing OpenPLC Runtime on Microcontrollers
==================================================

 

The OpenPLC Runtime was designed with portability in mind. Its core was written in pure C, allowing it to be ported to many different hardware platforms. For the most common operating systems, like Windows and Linux, there is a ready to use installer that deploys the runtime as an application that you can run. For embedded systems without a full blown OS, the runtime must be deployed as part of the PLC program itself. The OpenPLC Editor makes this task very easy for all officially supported boards. Once you’re ready to deploy your PLC program on your Arduino-compatible board, all you have to do is click on the orange circuit icon at the toolbar on the top:

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20800%2095'%3E%3C/svg%3E)![](https://autonomylogic.com/wp-content/uploads/2022/06/Program_arduino-1024x122.png)

This will bring an upload dialog which allows you to select which hardware platform you’re deploying OpenPLC Runtime to:

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20800%20523'%3E%3C/svg%3E)![](https://autonomylogic.com/wp-content/uploads/2022/06/arduino_upload-1024x669.png)

The upload dialog allows you to configure a couple things on the micro-runtime, such as if Modbus should be enabled and on which interface it must listen to requests. Once you’re done configuring the options you want, just hit the ‘Transfer to PLC’ button. If you see a [NOT INSTALLED] in front of the platform name you want to use, just hit the “Transfer to PLC” once and the supporting files for that platform will be installed in your system on the first upload. A version of the OpenPLC micro-runtime especially crafted for the selected hardware platform will be merged with the PLC program and uploaded to your board at the end of the process. The upload process is finished when you see the message “Done uploading!” at the end of the console output.

##### What are your Feelings

Updated on 2024-02-08

Leave a Reply [Cancel reply](/docs/installing-openplc-runtime-on-arduino-and-other-platforms/#respond)
------------------------------------------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2Finstalling-openplc-runtime-on-arduino-and-other-platforms%2F) to post a comment.