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
    wpa-conf /etc/wpa_supplicant/wpa_supplicant_wlanX.conf
```
where "wlanX" is your adapter, then
```
sudo systemctl enable wpa_supplicant.service
```
then reboot.

## For each different interface (adapter)

``` 
sudo nano /etc/wpa_supplicant/wpa_supplicant_wlanX.conf
```
where "wlanX" is your adapter, add content like this:
```
country=GB
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="my_wireless_network"
    psk="my_wireless_password"
}
```


