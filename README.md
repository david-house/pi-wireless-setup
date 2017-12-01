# pi-wireless-setup for Raspian Stretch

## Fix wifi not starting on boot
https://www.raspberrypi.org/forums/viewtopic.php?t=191061

```
sudo nano /etc/network/interfaces
```
then
```
allow-hotplug wlan0
iface wlan0 inet manual
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```
then
```
sudo systemctl enable wpa_supplicant.service
```
then reboot.
