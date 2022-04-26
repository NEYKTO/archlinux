# ArchLinux STEP by STEP

- check keyboard keys are correct. can load type keyboard with `loadkeys us` or `loadkeys es` or `loadkeys fr` 
- check internet connection with `ping -c 1 google.com`


Star service to network connection. Can check connection with `ping -c 1 google.com`

```
  systemctl start NetworkManager
  systemctl enable NetworkManager
```

- check TYPE of BIOS or UEFI
```
  ls /sys/firmware/efi/efivars
```
<img src="https://github.com/NEYKTO/archlinux/blob/main/.images/cap_1.png" width="512"/>
