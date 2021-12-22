- First run `sudo blkid` to get the UUID of the device you want to mount.
- Create a mount point for your device.
- Add the following line to `/etc/fstab`:
  - `UUID=<uuid-of-your-drive>  <mount-point>  <file-system-type>  <mount-option>  <dump>  <pass>`

For example:
  - `UUID=eb67c479-962f-4bcc-b3fe-cefaf908f01e  /mnt/sdb9  ext4  defaults  0  2`

Run `sudo mount -a` to see if it works.
