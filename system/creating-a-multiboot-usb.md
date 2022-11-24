You can prepare multiboot usb with `ventoy`. On arch, install `ventoy-bin`.

Then install ventoy to your usb with
```
sudo /opt/ventoy/Ventoy2Disk.sh -i /dev/sdc
```
By default it will format /dev/sdc1 with ext4. You can change it if you like:
```
sudo mkntfs --fast --label Ventoy /dev/sdc1
```
From now on, you can basically copy iso files to your usb stick.
