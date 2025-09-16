* [Página inicial](https://openplcproject.com/ "Página inicial")
* [Docs](https://autonomylogic.com/docs/ "Docs")
* [2. OpenPLC Runtime](https://autonomylogic.com/docs-category/openplc-runtime/ "2. OpenPLC Runtime")
* 2.2 Uploading Programs to OpenPLC Runtime


2.2 Uploading Programs to OpenPLC Runtime
=========================================

 

The OpenPLC runtime has a built-in webserver that allows you to configure OpenPLC and also to upload new programs for it to run. Micro implementations of the OpenPLC Runtime (i.e. versions of the runtime that go on microcontrollers and Arduino boards) do not have the built-in webserver. Instead, all runtime configurations for the micro runtime are done straight from the OpenPLC Editor upload dialog (see **[1.5 Installing OpenPLC Runtime on Microcontroller Boards](/docs/installing-openplc-runtime-on-arduino-and-other-platforms/)**).

The OpenPLC webserver can be accessed by opening a web browser on your computer and typing the IP address of your OpenPLC device at port 8080. For more information about OpenPLC Runtime Webserver, check **[2.1 OpenPLC Runtime Overview](https://autonomylogic.com//docs/2-1-openplc-runtime-overview/)**

After logging in on the webserver, you will see OpenPLC dashboard with some information about the current running program and the runtime logs.![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/reference/basics/uploading-running.png)

To upload your new program, go to the Programs section on the left menu. In there you should see a list of all your programs uploaded recently. You can revert back to a previously uploaded program by just clicking on it in the list and then confirming on the next page. To upload a new program, click on “Choose File”, select your .st file and then click on “Upload Program”.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/reference/basics/uploading-running-2.png)

On the window that appears, just fill out some information about your program so that you know what it is about next time you try to load it again. Once you’re done, click on “Upload program” to finally load your new .st file into OpenPLC.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%200%200'%3E%3C/svg%3E)![](https://openplcproject.github.io/reference/basics/uploading-running-3.png)

Once the file is uploaded, you will be directed back to the dashboard screen and the OpenPLC status will change to “compiling”. The logs about the compilation process are displayed on the runtime logs box. Once the compilation process is finished, the status will change to “running” and your new program will be run. If there was an error on your program, the status will change to “stopped” and the errors will be displayed on the runtime logs box.

##### What are your Feelings

Updated on 2022-07-06

Leave a Reply [Cancel reply](/docs/2-2-uploading-programs-to-openplc-runtime/#respond)
--------------------------------------------------------------------------------------

You must be [logged in](https://autonomylogic.com/wp-login.php?redirect_to=https%3A%2F%2Fautonomylogic.com%2Fdocs%2F2-2-uploading-programs-to-openplc-runtime%2F) to post a comment.