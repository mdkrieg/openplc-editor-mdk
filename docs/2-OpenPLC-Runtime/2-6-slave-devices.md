2.6 Slave Devices
=================

 

*Note: This section only applies to the OpenPLC Runtime running on Windows or Linux devices. Microcontrolled-based platforms (like Arduino) cannot attach Slave Devices*

You can attach Modbus slave devices to your OpenPLC Runtime to expand the number of I/O points. This is particularly useful for systems that don’t have any I/O points at all, like OpenPLC Runtime running on desktop computers or servers for example. The OpenPLC Runtime supports slave devices using either Modbus/TCP (network) or Modbus/RTU (serial). Devices with wireless capabilities that can transmit Modbus packets over TCP/IP are also supported.

Adding a Slave Device on OpenPLC
================================

Launch OpenPLC Runtime on your host, login to the web interface, go to Slave Devices on the left menu and click on “Add new device”.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201884%20954'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/06/slavedevices.png)

On the new screen that appears, fill out the name for your slave device (it can be anything, but just please avoid non-English characters like ç, é, ó, ñ), and then select “Generic Modbus TCP Device” or “Generic Modbus RTU Device” under Device Type.

TCP devices are the ones with TCP/IP support. RTU devices are only accessible through the serial network (usually RS485). The form will expand or shrink depending on the device type selected. Fill out all the information requested according to your device specifications.

The right side of the page is used to configure the Modbus registers you want to read and write. You can define the address of the first register and the range, which means how many registers after the first one you want to be read/written. These inputs, coils and registers will then be mapped to OpenPLC internal variables, located at **%IX100.0**, **%QX100.0**, and so on…

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201882%20950'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/06/adddevice.png)

Click on “Save device” and you’re good to go! Just start the PLC and your Modbus device will be communicating with OpenPLC Runtime.

Adding Arduino-compatible Boards as Slave Devices
=================================================

OpenPLC offers templates for you to easily add Arduino boards as slave devices. The only requirement is that the Arduino board must also be running the OpenPLC micro-runtime and configured to export its I/O pins through Modbus. The easiest way to install OpenPLC micro-runtime on your Arduino boards is using the OpenPLC Editor with a blank project. Download the blank project below and open it using OpenPLC Editor on your desktop.

[![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%2064%2064'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/05/imageedit_1_5872481624.png)](https://autonomylogic.com//wp-content/uploads/files/Blank%20Project.zip)

[**Blank Project.zip**](https://autonomylogic.com//wp-content/uploads/files/Blank%20Project.zip)

With the project open, click on the orange circuit icon on the top toolbar to compile the project and upload it to your Arduino board.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20800%2095'%3E%3C/svg%3E)![](https://autonomylogic.com/wp-content/uploads/2022/06/Program_arduino-1024x122.png)

Once compilation finishes, you will see a screen that will let you select which board type you want to use and configure the Modbus parameters of the OpenPLC micro-runtime.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20800%20523'%3E%3C/svg%3E)![](https://autonomylogic.com/wp-content/uploads/2022/06/arduino_upload-1024x669.png)

Select your board from the Board Type dropdown menu, and then select the correct COM Port to program it. Then click on “Communications” icon at the menu on the left side of the dialog. Make sure you have either Modbus Serial or Modbus TCP enabled and configured properly to have your board added as an OpenPLC Runtime Slave device. If you’re planning on using any of the Arduino Uno or Mega templates on the master runtime, make sure you select Modbus RTU (Serial) and **set the Slave ID to zero** on this screen.

*Note: Keep in mind that you can add any logic to this blank project, but if you do, it will supersede the commands received from the OpenPLC Runtime master. This could be useful if, for example, you want to perform fast, real-time tasks locally on the Arduino board (like counting pulses for example), and then have this information available for the bigger OpenPLC Runtime running as master somewhere else. If all you want is to just expand the number of I/O points on your master OpenPLC Runtime, then just leave the project blank.*

Pin Mapping
===========

The pin mapping for your Modbus device depends on its position on the slave devices list and the number of registers it has. OpenPLC supports multiple slave devices at the same time, and they all add up together on the address space. Below you can see a list of three ESP8266 devices added up together, and the respective address space reserved for them.

![](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201888%20638'%3E%3C/svg%3E)![](https://autonomylogic.com//wp-content/uploads/2022/06/modbusmapping.png)

From the table you can see the specific OpenPLC addresses for each device, where it starts and where it ends. For example, each ESP8266 on this list has 8 digital inputs, 8 digital outputs, 1 analog input, and 1 analog output. Therefore, the first device has the 8 digital inputs mapped on %IX100.0 to %IX100.7. All the other inputs and outputs follow the same pattern.