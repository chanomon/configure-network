#Configure your network in ubuntu

If you dont have wlan or ethernet connection in your ubuntu even when you have your ethernet cable connected, you may want to follow these steps:

1.  edit the file ```/etc/netplan/50-cloud-init.yaml``` the name of the file may vary a llitle but its located in that path.
   You'll need to end up with something like this:
```
network:
  ethernets:
    eth0:
      dhcp4: true
  
  version: 2
wifis:
        wlan0:
            dhcp4: true
            optional: true
            access-points:
                "SSID_name":
                    password: "WiFi_password"
```
save the file and then in terminal run:
```
sudo netplan generate
```
then 
```
sudo netplan apply
```
