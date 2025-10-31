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

## Disk Partitioning 

* In order to install Linux you need to need to divide your disk into  