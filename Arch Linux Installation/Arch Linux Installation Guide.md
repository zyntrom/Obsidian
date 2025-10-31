## Preparation:

* Install the ISO and flash it to the USB .
* [Arch Linux Download Link](https://archlinux.org/download/)

## Installation (UEFI Method)

* Plug in the USB and boot into it . (From the UEFI boot menu)
* Select Arch Linux installation from the menu of selections.

## Keyboard Layout

* If you want to change keyboard layout. (By default it is us)

```bash
#keyboard layout for it
loadkeys it

#keyboard layout for us
loadkeys us
```

## WiFi connection  

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

## Update the system clock

```bash
timedatectl
```
## Disk Partitioning 

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
  
### Formatting created Partition

To see all the created and existing partition

```bash
lsblk
```
