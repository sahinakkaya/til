If you want to connect to a device via bluetooth:
```
sudo systemctl enable bluetooth.service
bluetoothctl power on
bluetoothctl devices # to find the mac address of your device
bluetoothctl connect <MAC Address>
```
