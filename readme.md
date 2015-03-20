#Create Raspberry Pi Kiosk on Raspbian Debian Wheezy#
## Install Raspbian Debian Wheezy ##
With this tutorial you can create a 'fullscreen kiosk' which shows a webpage. This webpage will run in chromium.

The first step is to install Raspbian on the Raspberry Pi. There are 2 ways to do this.

- via the Raspberry Pi NOOBS image. (http://www.raspberrypi.org/help/noobs-setup/) Install the NOOBS image and install Raspbian via the NOOBS install manager
- install directly the Raspbian image (http://www.raspberrypi.org/documentation/installation/installing-images/README.md)

At the end you need a fresh Raspbian Debian Wheezy installed on your Raspberry Pi.

##Configure Raspbian Debian Wheezy##

When starting Raspbian for the first time you will see the Raspi Config tool. There are a few things you need to configure.

- Update the Raspi config tool
- Enable SSH when you want to proceed the configure process threw SSH (Advanced Options)
- Disable overscan. This option tries to adjust the resolution for you Raspberry Pi. But it will only f**k things up :) (Advanced Options)
- Change your boot to desktop environment. This will start-up the GUI instead of the CLI and Automatically will login to user 'pi'. 



## good to know ##
- default Raspbian login: user: pi pass: raspberry
