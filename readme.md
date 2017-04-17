# Create Raspberry Pi Kiosk on Raspbian Debian Jessie #
With this tutorial you can create a 'fullscreen kiosk' which shows a webpage. This webpage will run in chromium. 
 
## Install Raspbian Debian Wheezy ##

The first step is to install Raspbian on the Raspberry Pi. There are 2 ways to do this.

- via the Raspberry Pi NOOBS image. (https://www.raspberrypi.org/downloads/raspbian/ Install the NOOBS image and install Raspbian via the NOOBS install manager

At the end you need a fresh Raspbian Debian Jessie installed on your Raspberry Pi.

## Configure Raspbian Jessie ##

Raspbian will boot the GUI automatically. Next, boot up the terminal. We need to update the respositories:

```
sudo apt-get update
sudo apt-get upgrade
```

Then we need to install unclutter, to hide the mouse;

```
sudo apt-get install unclutter
```

Then we will start the rasps-config tool by calling the command `sudo raspi-config`

- Update the Raspi config tool (Advanced Options)
- Disable overscan. This option tries to adjust the resolution for your Raspberry Pi. But it will only f**k things up :) (Advanced Options)
- Enable SSH when you want to proceed the configure process threw SSH (Advanced Options) This is optional.

When calling the update and upgrade commands chromium will also be installed. 

When booting the kiosk we want to automatically start the browser and show the kiosk page. We will do this by editing the autostart file.
This file can be found at `~/.config/lxsession/LXDE-pi/autostart`

First we ill comment out the @xscreensaver line by  adding a hashtag (#) and the beginning of the line. Add the next lines to the file:

```
@xset s off
@xset s noblank
@xset -dpms

@chromium-browser --noerrdialogs --kiosk --incognito http://www.domain.com/to/kiosk/page
or
@chromium-browser --noerrdialogs --disable-session-crashed-bubble --disable-infobars --kiosk http://www.domain.com/to/kiosk/page

```


The @xset options will disable the energy-options from the X-server so the screen won't be shut down after a x amount of time.
The @sed line will prevent errors to be shown.
And finally Chromium will be startup in kiosk mode (with no error messages). 
Change the url to the url you want it to show. Local files are also possibly.

Now Chromium will start after the raspberry pi is booted up and will show the webpage.

## Good to know ##
- default Raspbian login: user: pi pass: raspberry
- the GPU of the Pi isn't that powerful. So animations in the browser don't really run smoothly. 


## Sources ##

- http://www.raspberrypi-spy.co.uk/2014/05/how-to-autostart-apps-in-rasbian-lxde-desktop/
- http://www.danpurdy.co.uk/web-development/raspberry-pi-kiosk-screen-tutorial/
- https://blog.reboost.net/kiosk-display-on-raspbian-jessie/
- http://www.raspberrypi-spy.co.uk/2014/05/how-to-autostart-apps-in-rasbian-lxde-desktop/
