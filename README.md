# Thecus-N7700-Pro-Mod
Hi,

I decided to sell this machine and thought I'd share my modifications to make this old NAS a usable fileserver or backup target in 2024

* [Thecus N770 Pro specs](https://www.thecus.com/product?cat=linux_nas&cat_type=smbTower&PROD_ID=27&language_num=1)

# Make the VGA port usable

1. Disassemble the NAS, get the mainboard out
2. There are soldering connections for a VGA Port
   1. Get a VGA Port e.g. from a broken mainboard
   2. Solder the VGA port to the board
3. Assemble and test
4. Display Mode 9 worked for me
5. Start and **Hold** Del-Key for BIOS

# Boot drive
At this point you could sacrifice one of the 7 3.5" Bays for a boot drive
**OR** you get an adapter to connect a SATA SSD to the IDE port of the DOM
be careful, my first order was an Adapter with the wrong direction
1. Search for SATA 22pin to 44pin IDE (**not!** 44pin IDE to SATA)
   * [This Adapter](https://www.ebay.de/itm/333395176710) worked for me
2. You need a 44pin IDE cable, around 30cm long
3.  You can clamp the SSD in the case. No mount needed (see image)

# Infos about the NICs
(Web)[https://www.thecus.com/product?cat=linux_nas&cat_type=smbTower&PROD_ID=74&language_num=1]
The NAS has two Intel 82574L 10/100/1000 Mbit/s NICs
```bash
root@nas:~# lspci | egrep -i --color 'network|ethernet'
01:00.0 Ethernet controller: Intel Corporation 82574L Gigabit Network Connection
02:00.0 Ethernet controller: Intel Corporation 82574L Gigabit Network Connection
``
