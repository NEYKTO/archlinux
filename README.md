# ArchLinux STEP by STEP

- check keyboard keys are correct. can load type keyboard with `loadkeys us` or `loadkeys es` or `loadkeys fr` 
- check internet connection with `ping -c 1 google.com`


Star service to network connection. Can check connection with `ping -c 1 google.com`

```
  systemctl start NetworkManager
  systemctl enable NetworkManager
```

- check TYPE of [BIOS](#disk-partitions-bios) or [UEFI](#disk-partitions-uefi)


```
  ls /sys/firmware/efi/efivars
```
<img src="https://github.com/NEYKTO/archlinux/blob/main/.images/cap_1.png" width="512"/>


 Disk partitions UEFI
 -
 type:
 ```
  cfdisk
  ```
  
<img src="https://github.com/NEYKTO/archlinux/blob/main/.images/cap_2.png" width="512"/>


Exemple for HardDrive 20Gb size

Select `gpt` after this, create first boot drive `New` -> `512M` -> `Enter`-> `Type` -> `EFI System` -> `Enter`

Select Free space, create file system drive `New` -> `15.5G`-> `Enter` -> `Type` -> `Linux filesystem` -> `Enter`

Select Free space, create SWAP file `New` -> just press enter, default is the rest of free size, go to `Type` -> `Linux swap`

Go to `Write` and `yes` to confirm with `Enter`

To finish just `Quit`

- Formating partitions
```
  mkfs.vfat -F32 /dev/sda1
  mkfs.ext4 /dev/sda2
  mkswap /dev/sda3
  swapon
```

- Mounting

```
  mount /dev/sda2 /mnt
```
where SDA2 drive is Linux filesystem base
creating folder for boot 
```
mkdir /mnt/boot
mkdir /mnt/boot/efi

mount /dev/sda1/ /mtn/boot/efi
```

Disk partitions BIOS
-

<img src="https://github.com/NEYKTO/archlinux/blob/main/.images/cap_3.png" width="512"/>



