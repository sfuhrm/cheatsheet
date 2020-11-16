### LUKS Linux Unified Key Setup Cheat Sheet

#### Key management
* Creating a 512 byte (=4096 bits) binary random key<br/>
  `dd if=/dev/urandom of=$HOME/rnd bs=1 count=512`
  
* Creating a 32 byte (=256 bits) readable random key<br/>
  `openssl rand -base64 32 > $HOME/rnd`

#### Formatting and opening with disk label

* Initialize a partition with a keyfile and a label, keysize is hashed to 256 bits<br/>
  `cryptsetup luksFormat --key-file $HOME/rnd -c aes-cbc-essiv:sha256 --label MYLABEL --key-size 256 /dev/sdb1`
* Opening a volume with a keyfile<br/>
  `cryptsetup luksOpen /dev/disk/by-label/MYLABEL MYLABEL --key-file $HOME/rnd`
* Creating a file system (-m0 is the size reserved for superuser)<br/>
  `mkfs.ext4 -m0 /dev/mapper/MYLABEL`
* Mounting an opened volume<br/>
  `mount /dev/mapper/MYLABEL /mnt/mylabel`

#### Unmounting and closing with disk label

* Unmounting amounted volume<br/>
  `umount /dev/mapper/MYLABEL`
* Close a volume<br/>
  `cryptsetup luksClose /dev/disk/by-label/MYLABEL`

#### Status

* Show device mapper status<br/>
  `cryptsetup status /dev/mapper/MYLABEL`

* Show LUKS key status<br/>
  `cryptsetup luksDump /dev/disk/by-label/MYLABEL`
