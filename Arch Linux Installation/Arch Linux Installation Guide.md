## Preparation:

* Install the ISO and flash it to the USB .
* [Arch Linux Download Link](https://archlinux.org/download/)

## 1. Installation (UEFI Method)

* Plug in the USB and boot into it . (From the UEFI boot menu)
* Select Arch Linux installation from the menu of selections.

## 2. Keyboard Layout

* If you want to change keyboard layout. (By default it is us)

```bash
#keyboard layout for it
loadkeys it

#keyboard layout for us
loadkeys us
```

## 3. WiFi connection  

* By default if you have Ethernet then it will automatically connect.
* If you have WiFi then use iwctl to connect

The Commands are:

```bash
iwctl
```

```bash
device list
```

```bash
station _name_ scan
```

```bash
station _name_ get-networks
```

```bash
station name connect SSID
```

* To test Internet connection use: (Use ctrl - c to stop any command from running)

```
ping google.com
```

## 4. Update the system clock

```bash
timedatectl
```
## 5. Disk Partitioning 

* In order to install Linux you need to need to divide your disk into three parts.
* They are root (/), swap, and boot. ( Optional if you already do not  have one )
* For this we can use fdisk or cfdisk. 
* In this case we will use cfdisk as it is easy to use.

```bash
cfdisk
```

* If it ask for label type select gpt
* Delete partitions that are no longer in use and make space if it does not show free space. ( If dual booting do not delete Partitions you do not recognize if could be windows or other Linux OS )
* Then select free space  with arrows and select and enter new.

* First we need to make a boot partition when it ask for size give 100M as size
* Second we need to make a swap (Temp ram for the OS) it can be of size  2,4,8,16 or such ( Its better to give size in powers of 2 ). If you have 16 gb ram then give swap of 8G
* The last partition can  be as much as you want because it is the root (/) partition 
  eg: 100G
* Then Finally select write.
  
## 6. Formatting created Partition

* To see all the created and existing partition

```bash
lsblk
```

* First we need  to Format the root partition 

```bash
mkfs.ext4 /dev/_root_partition_
```

* Second we need to Format swap partition 

```bash
mkswap /dev/_swap_partition_
```

* At Last we need to Format boot partition (Do not do this if you already have a boot partition by other Linux OS as it will remove the entry for the other OS)

```bash
mkfs.fat -F 32 /dev/efi_system_partition
```

## 7. Mount the file systems

* Mount point for root (/) partition 

```bash
mount /dev/root_partition /mnt
```

* Mount point for boot partition

```bash
#it makes file called efi in boot in /mnt 
mount --mkdir /dev/efi_system_partition /mnt/boot/efi
```

* At last Activate the created swap partition 

```bash
swapon /dev/swap_partition
```

## 8. Installation of Main System files

* We  now need to install most of the programs need for the base OS to run 

```bash
pacstrap -K /mnt base linux linux-firmware sof-firmware base-devel grub efibootmgr nano networkmanager 
```

## 9. Generating File System and config

* Now we need to create File System for the users and basic configuration for the OS to work 

* To get info on the file system mounted  

```bash
genfstab /mnt
```

* Saving the info into a file

```bash
genfstab /mnt > /mnt/etc/fstab
```

* To confirm the file write

```bash
cat /mnt/etc/fstab
```

## 10. Chroot into the System 

```bash
arch-chroot /mnt
```

## 11.  Date, Time and Location Config

* Setting up date and location 

```bash
ln -sf /usr/share/zoneinfo/Asia/India /etc/localtime
```

* To confirm date

```bash
date
```

* To sync system clock

```bash
hwclock --systohc
```

## 12. Localization

