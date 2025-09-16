1.2 Installing OpenPLC Editor
=============================

 

OpenPLC Editor can run on any platform that has support for Python. Currently there are official installers for:

* Windows
* Linux (Debian, Ubuntu, Fedora and variants)
* macOS (currently in beta)

For the officially supported platforms, just download the provided installer for your Operating System from the [**OpenPLC website**](https://www.autonomylogic.com/), and follow the instructions on the screen to have it installed in your system.

Installing on Unsupported Operating Systems
-------------------------------------------

For other Operating Systems, you can still install and run OpenPLC Editor provided you meet the dependencies:

1. Clone the official source code repository on Github:

> git clone https://github.com/thiagoralves/OpenPLC\_Editor

2. Install Dependencies:

– GCC and G++ (or any other C / C++ compiler)

– Bison

– Flex

– Autoconf

– Automake

– Make

– Python 2.7 (including pip)

– wxPython 3.0

3. Install Python libraries using pip:

> pip2 install future zeroconf==0.19.1 numpy==1.16.5 matplotlib==2.0.2 lxml pyro sslpsk pyserial

4. Compile matiec

> cd matiec
>
> autoreconf -i
>
> ./configure
>
> make -s
>
> cp ./iec2c ../editor/arduino/bin/ #keeps a copy of the iec2c compiler inside the arduino folder

Once OpenPLC Editor is installed you can run it with:

> python2.7 ./editor/Beremiz.py

Installing the Python 3 / wxPython Phoenix development branch
-------------------------------------------------------------

As Python 2.7 and wxPython 3.0 are now deprecated, we have put ongoing efforts to port OpenPLC Editor to Python 3 and wxPython Phoenix. If your system is not compatible with Python 2 anymore, you can try running the development branch based on Python 3. Beware that since this is a development branch, things can suddenly break and stop working. Use it at your own risk.

1. Clone the official source code repository on Github:

> git clone –branch dev-python3 https://github.com/thiagoralves/OpenPLC\_Editor

2. Install Dependencies:

– GCC and G++ (or any other C / C++ compiler)

– Bison

– Flex

– Autoconf

– Automake

– Make

– Python 3 (including pip)

3. Install Python libraries using pip:

> pip3 install wxPython lxml future matplotlib zeroconf pyserial

4. Compile matiec

> cd matiec
>
> autoreconf -i
>
> ./configure
>
> make -s
>
> cp ./iec2c ../editor/arduino/bin/ #keeps a copy of the iec2c compiler inside the arduino folder

Once OpenPLC Editor is installed you can run it with:

> python3 ./editor/Beremiz.py