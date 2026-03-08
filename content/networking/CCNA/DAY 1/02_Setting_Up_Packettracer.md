---
title: "Setting Up Cisco Packet Tracer"
---







### Installation For Arch Linux

1. Download Cisco Packet Tracer from the [official Cisco website](https://www.netacad.com/cisco-packet-tracer) or [My Drive](https://drive.proton.me/urls/KGA98TKYP4#sitWOO8ikXBP)   
2. Clone the repo [Packet Tracer](https://gitlab.com/fr0stb1rd/aur-packettracer-900.git)

```bash
git clone https://gitlab.com/fr0stb1rd/aur-packettracer-900.git
cd aur-packettracer-900
makepkg -sirc
```




3. Create  A desktop file   to create icon in the menu

packettracer.desktop

```bash
[Desktop Entry]
Name=Packet Tracer
Type=Application
Exec=firejail --net=none --noprofile /usr/lib/packettracer/packettracer.AppImage
Icon=/home/prashik/.local/share/icons/packettrace.ico
GenericName=Cisco Packet Tracer
Category=Network;
```


4. Move the file to folder `/usr/share/applications` 

```bash
mv packettracer.desktop /usr/share/applications
```


5. Update the desktop menu database 



```bash

sudo update-desktop-database
```