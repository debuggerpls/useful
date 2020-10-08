#### Mounting commands

* user needs to be in `dialout` group
```
usermod -a -G examplegroup exampleusername
```

* mount
```
$ sudo mount <device> <dir>
```

* unmount
```
$ sudo umount <dir>

# lazy unmount (clean references when not busy)
$ usod umount -l <device|dir>
```

* list partitions with filesystems
```
$ lsblk -f

# list usb drive names
$ fdisk -l
$ lsusb

# no mountpoints
$ blkid 

# find mountpoints and filesystems
$ findmnt <device/mountpoint> 
```

* use `fstad` file to permanently mount drives
```
$ cat /etc/fstab

# grep partition using UUID
$ blkid | grep <UUID>

# get partition UUID
$ blkid /dev/sda1
```
*

##### Links
[DevConnected mounting](https://devconnected.com/how-to-mount-and-unmount-drives-on-linux/)