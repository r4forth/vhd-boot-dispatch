# msys2-windows-utils
Windows utilities under MSYS2

## Boot
- bootmgr
- BOOTNXT
- Boot\
- grub4dos\

## VHD
```
$ modprobe loop
$ losetup /dev/loop0 disk.vhd
$ partprobe /dev/loop0
$ mount /dev/loop0p1 /mnt/images

$ losetup -d /dev/loop0
```

```
$ VBoxManage clonehd dynamicd_disk.vhd fixed_disk.vhd --format vhd --variant dynamic
```

## External Reference
- [Tiny Core Linux](http://distro.ibiblio.org/tinycorelinux/)
  * ntfs-3g
  * ntfsprogs
  * rsync
  * grub4dos
  
  ```
  $ tce-load -wi ntfs-3g
  ```
  
- [Tiny Core Linux Customizations for Remastering](http://www.canbike.org/off-topic/aggregate/tiny-core-linux-customizations-for-remastering.html)

  ```
  $ zcat core.gz | sudo cpio -i -H newc -d
  $ sudo find | sudo cpio -o -H newc | gzip -2 > core.gz
  ```
  
- [Udpcast](https://www.udpcast.linux.lu/)

  ```
  $ udp-sender --full-duplex -f source.vhd
  $ udp-receiver -f saved.vhd
  ```

- [Parallel SSH](https://pypi.python.org/pypi/pssh)
- [MSYS2](http://www.msys2.org/)
- [ConEmu](https://conemu.github.io/)
- [Booting Windows to a Differencing Virtual Hard Disk](https://blogs.msdn.microsoft.com/heaths/2009/10/13/booting-windows-to-a-differencing-virtual-hard-disk/)
- [Native VHD Boot on unsupported versions of Windows 7](http://agnipulse.com/2016/12/native-vhd-boot-unsupported-versions-windows-7/)
- [WakeMeOnLan](http://www.nirsoft.net/utils/wake_on_lan.html)
  * [HowTo: Wake Up Computers Using Linux Command [ Wake-on-LAN ( WOL ) ]](https://www.cyberciti.biz/tips/linux-send-wake-on-lan-wol-magic-packets.html)
- [UEFI support for PXE booting](http://projects.theforeman.org/projects/foreman/wiki/PXE_Booting_UEFI/8)
- [PXELINUX](http://www.syslinux.org/wiki/index.php?title=PXELINUX)

  ```
  LABEL tiny-core-linux
  TITLE Tiny Core Linux
  LINUX /corelinux/vmlinuz
  INITRD /corelinux/core.gz,/corelinux/tce.gz,/corelinux/cde.gz
  APPEND loglevel=3,next-server=163.26.68.15
  ```

- [chntpw](https://en.wikipedia.org/wiki/Chntpw)
  * [Reset Windows 7 Admin Password with Ubuntu Live CD/USB](http://www.chntpw.com/reset-windows-7-admin-password-with-ubuntu/)
  * [How to Hack a Windows 7/8/2008/10 Admin Account Password with Windows Magnifier](https://cx2h.wordpress.com/2015/04/02/how-to-hack-a-windows-782008-admin-account-password-with-windows-magnifier/)
- [憶傑科技 - VHD 無硬碟系統](https://sites.google.com/a/vhdsoft.com/web/)
- [[網路工具] 如何使用透過網路(LAN)喚醒功能(Wake on LAN)](https://www.asus.com/tw/support/FAQ/1009775)
- [ATA over Ethernet](https://en.wikipedia.org/wiki/ATA_over_Ethernet)
  * [WinAoE - AoE Windows Driver](https://winaoe.org/)

## About
HSIEH, Li-Yi @進學國小資訊組