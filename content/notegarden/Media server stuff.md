Raspberry Pi 4 running Raspbian

ssh roscoe@192.168.4.55 p]fJ4QRM

```
sudo mount /dev/sda1 /media/usb-drive/
sudo mount | grep sda1
```

sda1 is a NTFS fstype

***

file management: other hard drives as backup for libraries, keeping tidy with sonarr/radarr

graceful shutdown of pi + manually moving things onto hard drive for organization + plugging blue hard drive back in before booting pi back up

***

to do:

* ~~install servarr stack for file organization~~ tinymediamanager + manual instead
* move new files from general purpose hard drive to the blue hard drive
* organize media vault for server – fix missing/ugly cover art etc
* ~~set up permanent mounting for blue hard drive~~ done
* ~~reboot pi, make sure everything working correctly for desktop streaming – weird issue where Jellyfin works on phone but not desktop PC?~~ done
* set up static ip?

***

## useful commands for media server maintenance 

execute the following systemctl command to start GUI: ``$ sudo systemctl isolate graphical``

graceful shutdown: ``$ shutdown -h now``

***

static ip setup (per [this tutorial](https://www.freecodecamp.org/news/setting-a-static-ip-in-ubuntu-linux-ip-address-tutorial/)):

current adapter name – wlan0

current ip: inet 192.168.4.55/22 brd 192.168.7.255

subnet mask 255.255.252.0

***

windows command to view all computers connected to the network: `arp -a`