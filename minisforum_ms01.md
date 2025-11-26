# Minisforum MS-01 Intel i9-12900H
- 32GB RAM
- 3x M.2 slots

## Updating BIOS
From [here](https://forums.servethehome.com/index.php?threads/minisforum-ms-01-bios.43328/page-5#post-445485)

Oct 23, 2024
#87
If anyone is reading this and the previous posts have not fully helped with regards to updating the MS-01 BIOS, here is what did the trick for me:
- Formatted USB Drive as FAT32 (using Rufus on Windows, using MS-DOS bootable option and selecting UEFI - this will land some un-necessary files on your USB drive like autorun, etc. but they won't hurt anything)
- Copied over the 1.26 BIOS files to the root of the USB Drive
- ***Downloaded shell.zip from the bottom of this site, extracted and copied shell.efi to the root of the USB Drive (prior to doing this, I could not boot off of the USB and nothing would happen when I selected the UEFI Shell from the BIOS menu, it would just flash briefly and do nothing. I'm sure you can get shell.efi from elsewhere but this worked for me). 10/26 EDIT: Official/Clean build of shell.efi here (courtesy of @Avamander)
- Either boot using F7 at MS-01 power-on or select the UEFI shell from the BIOS
- Change into your USB directory (you cannot use 'cd', 'dir' or 'ls' commands, simply type the drive letter designation and press enter (for me it was FS0: ) <-that's a zero at the end and not an O as in oscar.
- Type this file name and press enter to start the BIOS update: AfuEfiFlash.nsh
- Hope this helps.

## Adding a graphics card for offloading GPU / AI tasks
- Could use this one - https://yestonstore.com/products/yeston-rtx-3050-6gb-gddr6-gaming-graphics-card
- Ultimate guide to GPU passthrough - https://www.reddit.com/r/homelab/comments/b5xpua/the_ultimate_beginners_guide_to_gpu_passthrough/ with futher details - https://pve.proxmox.com/wiki/PCI_Passthrough

## Changing the network after adding / removing harware
- https://www.reddit.com/r/homelab/comments/1k2uck1/minisforum_ms01_rj45_ports_stopped_working_after/
