# Manual installation for Linux Raspbian Jessie in Raspberry PI Variant Boards
Manual installation can be carried after installing the operating system and establishing Internet connection.
## Pre-installation
### Basic Instruction: Upgrade Operating System
Update the software repository for the operating system and upgrade all installed packages into their latest version.
* __Software-level Instruction__
    * `sudo apt-get update && sudo apt-get upgrade`
* __Command-level Instruction__
    * `yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq update && yes | sudo DEBIAN_FRONTEND=noninteractive apt-get -yq upgrade`

## Disable Screen Saver
Raspbian Jessie default screen saver is ten minutes and then goes to soft shut-down within the next 30 minutes. Pedge, need to have the operating system to be always available unless the user turned it off. Hence, general energy saving features should not active.
### Basic Instruction: Locate or Create `/etc/xdg/lxsession/LXDE-pi/autostart` and Add These Lines
```markdown
@xset -dpms
@xset s noblank
@xset s off
```
* __Software-level Instruction__
    * `sudo nano /etc/xdg/lxsession/LXDE-pi/autostart`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\n@xset s noblank\n@xset s off\n@xset -dpms" >> /etc/xdg/lxsession/LXDE-pi/autostart'`

### Basic Instruction: Locate or Create `/etc/xdg/lxsession/LXDE-pi/autostart` and Add These Lines
```markdown
@xset -dpms
@xset s noblank
@xset s off
```
* __Software-level Instruction__
    * `sudo nano /etc/xdg/lxsession/LXDE/autostart`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\n@xset s noblank\n@xset s off\n@xset -dpms" >> /etc/xdg/lxsession/LXDE/autostart'`

### Basic Instruction: Locate or Create `/home/pi/.bashrc` and Add `setterm -blank 0 -powerdown 0`
* __Software-level Instruction__
    * `sudo nano /home/pi/.bashrc`
    * Copy-paste `setterm -blank 0 -powerdown 0`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\nsetterm -blank 0 -powerdown 0" >> /home/pi/.bashrc'`

### Basic Instruction: Locate `/etc/lightdm/lightdm.conf` and Replace `#xserver-command=X` with `xserver-command=X -s 0 -dpms`
* __Software-level Instruction__
    * `sudo nano /etc/lightdm/lightdm.conf`
    * Locate and replace `#xserver-command=X` with `xserver-command=X -s 0 -dpms`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/#xserver-command=X/xserver-command=X -s 0 -dpms/g" /etc/lightdm/lightdm.conf`

### Basic Instruction: Locate `/etc/kbd/config` and Replace `BLANK_TIME=30` with `BLANK_TIME=0`
* __Software-level Instruction__
    * `sudo nano /etc/kbd/config`
    * Locate and replace `BLANK_TIME=30` with `BLANK_TIME=0`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/BLANK_TIME=30/BLANK_TIME=0/g" /etc/kbd/config`

### Basic Instruction: Locate `/etc/kbd/config` and Replace `POWERDOWN_TIME=30` with `POWERDOWN_TIME=0`
* __Software-level Instruction__
    * `sudo nano /etc/kbd/config`
    * Locate and replace `POWERDOWN_TIME=30` with `POWERDOWN_TIME=0`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/POWERDOWN_TIME=30/POWERDOWN_TIME=0/g" /etc/kbd/config`

## Setup LIRC (Linux Infrared Remote Control)
LIRC is a library for Linux to interface general infrared devices. Although mostly related to TV infrared remote, LIRC can be used to assign infrared signals to running program. However, the infrared signals need to be assigned into constants those refer to TV infrared remote. In this setup I set to assign three infrared signals into constants (`KEY_1`, `KEY_2`, `KEY_3`).
### Basic Instruction: Locate `/etc/modules` and Add These Lines
```markdown
lirc_dev
lirc_rpi gpio_in_pin=23 gpio_out_pin=22
```
* __Software-level Instruction__
    * `sudo nano /etc/modules`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\n\nlirc_dev\nlirc_rpi gpio_in_pin=23 gpio_out_pin=22" >> /etc/modules'`

### Basic Instruction: Delete `/etc/lirc/hardware.conf`, Create`/etc/lirc/hardware.conf`, and Add These Lines
```markdown
########################################################
# /etc/lirc/hardware.conf
#
# Arguments which will be used when launching lircd
LIRCD_ARGS=\"--uinput\"
# Do not start lircmd even if there seems to be a good config file
# START_LIRCMD=false
# Do not start irexec, even if a good config file seems to exist.
# START_IREXEC=false
# Try to load appropriate kernel modules
LOAD_MODULES=true
# Run \"lircd --driver=help\" for a list of supported drivers.
DRIVER=\"default\"
# usually /dev/lirc0 is the correct setting for systems using udev
DEVICE=\"/dev/lirc0\"
MODULES=\"lirc_rpi\"
# Default configuration files for your hardware if any
LIRCD_CONF=\"\"
LIRCMD_CONF=\"\"
########################################################
```
* __Software-level Instruction__
    * `sudo rm /etc/lirc/hardware.conf`
    * `sudo nano /etc/lirc/hardware.conf`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\n########################################################\n# /etc/lirc/hardware.conf\n#\n# Arguments which will be used when launching lircd\nLIRCD_ARGS=\"--uinput\"\n\n# Do not start lircmd even if there seems to be a good config file\n# START_LIRCMD=false\n\n# Do not start irexec, even if a good config file seems to exist.\n# START_IREXEC=false\n\n# Try to load appropriate kernel modules\nLOAD_MODULES=true\n\n# Run \"lircd --driver=help\" for a list of supported drivers.\nDRIVER=\"default\"\n# usually /dev/lirc0 is the correct setting for systems using udev\nDEVICE=\"/dev/lirc0\"\nMODULES=\"lirc_rpi\"\n\n# Default configuration files for your hardware if any\nLIRCD_CONF=\"\"\nLIRCMD_CONF=\"\"\n########################################################" > /etc/lirc/hardware.conf'`

### Basic Instruction: Locate `/boot/config.txt` and Add `dtoverlay=lirc-rpi,gpio_in_pin=23,gpio_out_pin=22`
* __Software-level Instruction__
    * `sudo nano /boot/config.txt`
    * Copy-paste `dtoverlay=lirc-rpi,gpio_in_pin=23,gpio_out_pin=22`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\ndtoverlay=lirc-rpi,gpio_in_pin=23,gpio_out_pin=22" >> /boot/config.txt'`

### Basic Instruction: Delete `/etc/lirc/lircd.conf`, Create `/etc/lirc/lircd.conf`, and Add These Lines
```markdown
# Please make this file available to others
# by sending it to <lirc@bartelmus.de>
#
# this config file was automatically generated
# using lirc-0.9.0-pre1(default) on Sat Jan  7 22:45:56 2017
#
# contributed by
#
# brand:                       /home/pi/lircd.conf
# model no. of remote control:
# devices being controlled by this remote:
#
begin remote
  name  pysoc
  bits           13
  flags RC5|CONST_LENGTH
  eps            30
  aeps          100
  one           924   840
  zero          924   840
  plead         970
  gap          113287
  toggle_bit_mask 0x0
      begin codes
          KEY_1                    0x1001
          KEY_2                    0x1002
          KEY_3                    0x1003
      end codes
end remote
```
* __Software-level Instruction__
    * `sudo nano /boot/config.txt`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "# Please make this file available to others\n# by sending it to <lirc@bartelmus.de>\n#\n# this config file was automatically generated\n# using lirc-0.9.0-pre1(default) on Sat Jan  7 22:45:56 2017\n#\n# contributed by \n#\n# brand:                       /home/pi/lircd.conf\n# model no. of remote control: \n# devices being controlled by this remote:\n#\nbegin remote\n  name  pysoc\n  bits           13\n  flags RC5|CONST_LENGTH\n  eps            30\n  aeps          100\n  one           924   840\n  zero          924   840\n  plead         970\n  gap          113287\n  toggle_bit_mask 0x0\n      begin codes\n          KEY_1                    0x1001\n          KEY_2                    0x1002\n          KEY_3                    0x1003\n      end codes\nend remote" > /etc/lirc/lircd.conf'`

### Basic Instruction: Delete `/home/pi/.lircrc`, Create `/home/pi/.lircrc`, and Add These Lines
```markdown
begin
    button = KEY_1
    config = KEY_1
    prog = pysoc
end
begin
    button = KEY_2
    config = KEY_2
    prog = pysoc
end
begin
    button = KEY_3
    config = KEY_3
    prog = pysoc
end
```
* __Software-level Instruction__
    * `rm /home/pi/.lircrc`
    * `nano /home/pi/.lircrc`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\nbegin\n    button = KEY_1\n    config = KEY_1\n    prog = pysoc\nend\nbegin\n    button = KEY_2\n    config = KEY_2\n    prog = pysoc\nend\nbegin\n    button = KEY_3\n    config = KEY_3\n    prog = pysoc\nend" > /home/pi/.lircrc'`

### Basic Instruction: Delete `/etc/lirc/lircrc`, Create `/etc/lirc/lircrc`, and Add These Lines
```markdown
begin
    button = KEY_1
    config = KEY_1
    prog = pysoc
end
begin
    button = KEY_2
    config = KEY_2
    prog = pysoc
end
begin
    button = KEY_3
    config = KEY_3
    prog = pysoc
end
```
* __Software-level Instruction__
    * `sudo rm /etc/lirc/lircrc`
    * `sudo nano /etc/lirc/lircrc`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\nbegin\n    button = KEY_1\n    config = KEY_1\n    prog = pysoc\nend\nbegin\n    button = KEY_2\n    config = KEY_2\n    prog = pysoc\nend\nbegin\n    button = KEY_3\n    config = KEY_3\n    prog = pysoc\nend" > /etc/lirc/lircrc'`

### Basic Instruction: Restart LIRC
* __Software-level Instruction__
    * `sudo /etc/init.d/lirc stop`
    * `sudo /etc/init.d/lirc start`
* __Command-level Instruction__
    * `sudo /etc/init.d/lirc stop && sudo /etc/init.d/lirc start`

## Setup PICamera
Raspberry PI has two ways to connect camera: USB web cam and PICamera. USB web cam is the usual USB web cam you can find in general consumer electronics store. PICamera is a ribbon cabled camera that is low powered and smaller than common USB web cam. However, despite PICamera has its driver pre-installed in Raspbian Jessie, it different setup route than USB web cam.
### Basic Instruction: Locate `/boot/config.txt` and Add `gpu_mem=128`
* __Software-level Instruction__
    * `sudo nano /boot/config.txt`.
    * Copy-paste `gpu_mem=128`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\ngpu_mem=128" >> /boot/config.txt'`

### Basic Instruction: Locate `/boot/config.txt` and Replace `start_x=0` with `start_x=1`
* __Software-level Instruction__
    * `sudo nano /boot/config.txt`.
    * Locate and replace `start_x=0` with `start_x=1`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/start_x=0/start_x=1/g" /boot/config.txt`

## Setup PyAudio
PyAudio is a high level library to interface sound input and output. PyAudio works across common desktop operating system, Linux, MacOS, and Windows. However, there is a problem in one of its dependency, PortAudio. Hence, to solve this issue, you need to recompile the stable version of PortAudio.
### Basic Instruction: Download PortAudio stable version 19 with `wget` to `home/pi`
* __Software-level Instruction__
    * `wget http://www.portaudio.com/archives/pa_stable_v19_20140130.tgz`
* __Command-level Instruction__
    * `wget http://www.portaudio.com/archives/pa_stable_v19_20140130.tgz -P /home/pi`

### Basic Instruction: Extract PortAudio stable version 19 with `tar` to `home/pi`
* __Software-level Instruction__
    * `tar xf /home/pi/pa_stable_v19_20140130.tgz -C`
* __Command-level Instruction__
    * `tar xf /home/pi/pa_stable_v19_20140130.tgz -C /home/pi`

### Basic Instruction: Compile PortAudio stable version 19 Using These Commands
```markdown
cd /home/pi/portaudio
./configure
make
sudo make install
cd /home/pi
```
* __Software-level Instruction__
    * `cd /home/pi/portaudio`
    * `./configure`
    * `make`
    * `sudo make install`
    * `cd /home/pi`
* __Command-level Instruction__
    * `cd /home/pi/portaudio && ./configure && make && sudo make install && cd /home/pi`

### Basic Instruction: Locate `/home/pi/.bashrc` and Add These Lines
```markdown
LD_LIBRARY_PATH=\"/usr/local/lib\"
LD_RUN_PATH=\"/usr/local/lib\"
PATH=$PATH:/usr/local/lib/
export LD_LIBRARY_PATH
export LD_RUN_PATHexport PATH
```
* __Software-level Instruction__
    * `sudo nano /home/pi/.bashrc`
    * Copy paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\nLD_LIBRARY_PATH=\"/usr/local/lib\"\nexport LD_LIBRARY_PATH\nLD_RUN_PATH=\"/usr/local/lib\"\nexport LD_RUN_PATH\nPATH=$PATH:/usr/local/lib/\nexport PATH" >> /home/pi/.bashrc'`

## Setup USB Audio Driver
### Basic Instruction: Delete `/etc/asound.conf`, Create `/etc/asound.conf`, and Add These Lines
```markdown
pcm.!default{
    type hw card 1
}
ctl.!default{
    type hw card 1
}
```
* __Software-level Instruction__
    * `sudo rm /etc/asound.conf`
    * `sudo nano /etc/asound.conf`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\npcm.!default{\n    type hw card 1\n}\nctl.!default{\n    type hw card 1\n}" > /etc/asound.conf'`

### Basic Instruction: Delete `/home/pi/.asoundrc`, Create `/home/pi/.asoundrc`, and Add These Lines
```markdown
pcm.!default{
    type hw card 1
}
ctl.!default{
    type hw card 1
}
```
* __Software-level Instruction__
    * `rm /home/pi/.asoundrc`
    * `nano /home/pi/.asoundrc`
    * Copy-paste the lines.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo /bin/sh -c 'printf "\npcm.!default{\n    type hw card 1\n}\nctl.!default{\n    type hw card 1\n}" > /home/pi/.asoundrc'`

### Basic Instruction: Locate `/usr/share/alsa/alsa.conf` and Replace `defaults.ctl.card 0` with `defaults.ctl.card 1`
* __Software-level Instruction__
    * `sudo nano /usr/share/alsa/alsa.conf`
    * Locate and replace `defaults.ctl.card 0` with `defaults.ctl.card 1`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/defaults.ctl.card 0/defaults.ctl.card 1/g" /usr/share/alsa/alsa.conf`

### Basic Instruction: Locate `/usr/share/alsa/alsa.conf` and Replace `defaults.pcm.card 0` with `defaults.pcm.card 1`
* __Software-level Instruction__
    * `sudo nano /usr/share/alsa/alsa.conf`
    * Locate and replace `defaults.pcm.card 0` with `defaults.pcm.card 1`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/defaults.pcm.card 0/defaults.pcm.card 1/g" /usr/share/alsa/alsa.conf`

### Basic Instruction: Locate `/usr/share/alsa/alsa.conf` and Replace `defaults.pcm.device 0` with `defaults.pcm.device 1`
* __Software-level Instruction__
    * `sudo nano /usr/share/alsa/alsa.conf`
    * Locate and replace `defaults.pcm.device 0` with `defaults.pcm.device 1`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/defaults.pcm.device 0/defaults.pcm.device 1/g" /usr/share/alsa/alsa.conf`

### Basic Instruction: Locate `/usr/share/alsa/alsa.conf` and Replace `defaults.pcm.subdevice 0` with `defaults.pcm.subdevice 1`
* __Software-level Instruction__
    * `sudo nano /usr/share/alsa/alsa.conf`
    * Locate and replace `defaults.pcm.subdevice 0` with `defaults.pcm.subdevice 1`.
    * CTRL + X, then Y, then ENTER.
* __Command-level Instruction__
    * `sudo sed -ie "s/defaults.pcm.subdevice 0/defaults.pcm.subdevice -1/g" /usr/share/alsa/alsa.conf`

## Post-installation
### Basic Instruction: Download Source Codes from [https://github.com/notalentgeek/pedge](https://github.com/notalentgeek/pedge) to `/home/pi`
* __Software-level Instruction__
    * `git clone https://github.com/notalentgeek/pedge`
* __Command-level Instruction__
    * `cd /home/pi && git clone https://github.com/notalentgeek/pedge --depth 1`

### Basic Instruction: Download All Python 3 Packages from `pip3`
* __Software-level Instruction__
    * `sudo pip3 install aubio`
    * `sudo pip3 install docopt`
    * `sudo pip3 install flask`
    * `sudo pip3 install flask-socketio`
    * `sudo pip3 install numpy`
    * `sudo pip3 install pyaudio`
    * `sudo pip3 install pyinstaller`
    * `sudo pip3 install python-lirc`
    * `sudo pip3 install rethinkdb`
    * `sudo pip3 install tzlocal`
    * `sudo pip3 install virtualenv`
* __Command-level Instruction__
* `sudo pip3 install -r /home/pi/pedge/req/req_raspbian_jessie.txt`txt`