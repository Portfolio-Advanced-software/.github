# Metatrader 5 inside a docker container

## Base image
You can use a linux base to build your docker image from. I used Ubuntu as a base.

## MetaTrader 5
To install MetaTrader 5 on a linux distro you need a couple of things (to do):
- Wine (A compatibility layer that allows certain Windows application to run on Linux)
- Enable the i386 architecture (needed for 32 bit Intel x86 compatible processors)
- Software to enable the GUI of MetaTrader 5
- Copy of MetaTrader 5 setup (or the install directory to skip the setup)

### Wine
To install Wine just simply use the command ```sudo apt-get update && sudo apt-get install wine winbind```. 
Notice this also install winbind which is sometimes necessary to run MetaTrader 5.

### i386 architecture
To enable the i386 architecture use this command ```dpkg --add-architecture i386```.

### MetaTrader 5 GUI
To handle the GUI of MetaTrader 5 you can use a virtual display to do this there are lots of choices in software but the two I use are X11-server and xvfb.

#### X11-server
The X11-server is a great solution if you want to connect to the display and see what is going on. 
To use the X11-server you don't need to install anything because most Linux distros come with one pre installed, 
you do need to set the display environment variable to the host machine. 
For example you could do this inside the dockerfile like this ```DISPLAY=host.docker.internal:0.0```. 
To actually see the display when starting MetaTrader 5 you need to install the X11-server on your Windows host machine (I won't cover using X11-server on other OS). 
You could use VcXsrv for example with the default settings. When starting MetaTrader 5 using the command line inside your docker it will automatically open a window.

#### Xvfb
Xvfb creates a virtual display that is not immidiately visible so it's great to satisfy MetaTrader 5 for the GUI and to use it's functionality through the command line.
To install xvfb use this command ```sudo apt-get update && sudo apt-get install xvfb```. After the installation you need to set the environment variable like this
```
DISPLAY=:99
Xvfb :99 -screen 0 1024x768x16 &
```

### MetaTrader 5
To install MetaTrader 5 you firstly need to get the setup.exe to do this use ```sudo apt-get update && sudo apt-get install wget``` and 
```wget -q https://download.mql5.com/cdn/web/metaquotes.software.corp/mt5/mt5setup.exe```. If the url is not working look it up on the [MetaTrader website](https://www.metatrader4.com/)
Then you can run the setup using wine ```wine mt5setup.exe```. Alternatively you can copy the pre installed directory inside the docker.


## Example Dockerfile
To install MetaTrader 5 in the docker image you need to set the environment variable debian frontend to non interactive like this ```DEBIAN_FRONTEND=noninteractive```.
This ensures that the setup doesn't stop when waiting for user input and use the defaults. You also need to use ```/S``` to avoid this.

Example:
```
# Use the base image from Ubuntu
FROM ubuntu:latest

# Set the working directory to /app
WORKDIR /app

# Install Wine, wget and MetaTrader 5 setup
RUN dpkg --add-architecture i386 \
    && apt-get update \
    && apt-get install -y wine winbind wget xvfb \
    && wget -q https://download.mql5.com/cdn/web/metaquotes.software.corp/mt5/mt5setup.exe

# Set environment variable display to the host machine when using X11-server on host machine
#ENV DISPLAY=host.docker.internal:0.0

# Set up Xvfb
ENV DISPLAY=:99
RUN Xvfb :99 -screen 0 1024x768x16 &

# Run setup silently to install MT5
# CMD [ "wine mt5setup.exe /S" ]

# Copy default installation directory to docker to skip MetaTrader 5 setup 
COPY ["MetaTrader_5_32bit/MetaTrader 5", "./test"]
```
Some lines are commented out to switch the choice for the GUI display and how to install MetaTrader 5.

## Run MetaTrader 5
Finally to run MetaTrader 5 inside the docker you need to execute the following command in the docker shell at the MetaTrader 5 install directory:
```wine terminal.exe``` (with X11-server)
```xvfb-run wine terminal.exe``` (with xvfb)

