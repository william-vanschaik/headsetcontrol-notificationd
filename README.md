# headsetcontrol-notificationd

![screenshot](https://screenshot.tbspace.de/jpcefkgwhvy.png)

headsetcontrol-notificationd is a small daemon that polls headsetcontrol to display notifications about the charge status of several headsets.  
For a list of supported devices please check [Sapd/HeadsetControl](https://github.com/Sapd/HeadsetControl).  

**Simon Ingelsson rewrote this daemon in pure bash:**  
https://gitlab.com/devnore/headsetcontrol-notificationd

This bash implementation is also very good I probably didn't need to be a goof and redo it in Python. 

### "Design"
Thanks to https://github.com/Manawyrm/headsetcontrol-notificationd for original design.

headsetcontrol-notificationd was hacked together in Python and polls the headsetcontrol executable at a configurable interval. 
This isn't an elegant solution at all, but it works (pretty well).  

### Requirements
Python3, HeadsetControl and notify-send  

You will also need a notification daemon if you are not using a desktop environment.

### Installation
```
git clone https://github.com/manawyrm/headsetcontrol-notificationd
cd headsetcontrol-notificationd

sudo cp headsetcontrol-notificationd.service /etc/systemd/user/headsetcontrol-notificationd.service
sudo cp headsetcontrol-notificationd /usr/local/bin/headsetcontrol-notificationd
sudo chmod +x /usr/local/bin/headsetcontrol-notificationd

sudo systemctl daemon-reload
systemctl --user enable --now headsetcontrol-notificationd
```
