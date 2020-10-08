* erase beginning of SD card
```
$ sudo dd if=/dev/zero of=<dev> bs=1M count=16

# create partitions with gui
$ sudo cfdisk <dev>

# parted (cmd line)
$ sudo parted -l

$ parted <dev>

# example for beaglebone (in parted)
mklabel msdos
mkpart primary fat16 0 128MB
mkpart primary ext4 128MB SIZEMB
set 1 boot on
quit
```

* format partitions
```
sudo mkfs.vfat -F 32 -n boot <dev>

sudo mkfs.ext4 -L rootfs -E nodiscard <dev>
# -L assigns volume name to partition
# -E nodiscard disables bad block blocking
```

##### Links:
* [TecMint](https://www.tecmint.com/create-disk-partitions-in-linux/)